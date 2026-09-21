# The Memory Hierarchy and Why Caches Exist

Write a loop that sums every element of a large two-dimensional array, walking across
each row in turn. Then write the identical loop with the two index variables swapped,
so it walks down each column instead. Same arithmetic, same number of additions, same
data. On any machine built in the last thirty years the second version will run
several times slower, sometimes more than ten times slower. Nothing about the
computation changed. What changed is whether the memory system was asked for things
it had already gone and fetched.

That gap is the single most important fact about the performance of real programs,
and the entire structure of a modern memory system is an attempt to paper over it.

## Two Technologies That Diverged

The problem is not that memory is slow in absolute terms. It is that memory has
improved along a different axis than logic did.

Storage bits come in two practical flavors. A static RAM cell holds its value in a
cross-coupled pair of inverters — typically six transistors — and will hold it
indefinitely as long as power is applied. It can be read in a fraction of a
nanosecond. It is also large, and six transistors per bit gets expensive fast. A
dynamic RAM cell, by contrast, is one transistor and one tiny capacitor. The charge
on the capacitor leaks away in milliseconds, so every row must be read out and
rewritten thousands of times a second just to stand still. Reading it destroys the
stored charge and requires sense amplifiers to detect a very small voltage swing on a
long, heavily loaded bit line. But a DRAM bit occupies a fraction of the area of an
SRAM bit, which is why main memory is DRAM and why it comes in gigabytes rather than
megabytes.

Over several decades, DRAM capacity grew enormously and DRAM bandwidth grew
respectably. DRAM *latency* barely moved. The time to open a row, sense it, and
deliver the first word has stayed in the neighborhood of tens of nanoseconds across
generations, because it is governed by the physics of small capacitors driving long
wires rather than by transistor speed. Processor clocks, meanwhile, went from
megahertz to gigahertz. A memory access that once cost a handful of cycles now costs
a couple of hundred. The hardware did not get slower; the yardstick got much finer.

Two hundred cycles is enough time for a modern core to execute several hundred
instructions. Left unaddressed, a program touching memory every few instructions
would spend almost all of its time waiting, and the processor's pipelines, predictors,
and functional units would be decorative.

## Locality Is What Makes the Trick Possible

Caching works only because programs do not access memory at random. They exhibit two
kinds of regularity, and both are empirical facts about how people write code rather
than theorems about computation.

Temporal locality: an address used recently is likely to be used again soon. Loop
counters, stack frames, hot data structures, the top of the call stack — a small
working set absorbs the overwhelming majority of accesses in most programs.

Spatial locality: an address near one just used is likely to be used soon. Arrays are
traversed in order. Structure fields are read together. Instructions are fetched
sequentially except at branches.

A cache exploits the first by keeping recently used data in fast storage, and the
second by never fetching a single byte. It fetches a whole aligned block — sixty-four
bytes is the common size — on the bet that the neighbors will be wanted too. That bet
is exactly what the row-major loop wins and the column-major loop loses. Walking a row
touches every byte of each line it pulls in. Walking a column pulls in a full line,
uses a handful of bytes of it, and moves on, so the machine pays full latency and full
bandwidth for a small fraction of the data.

## How the Box Is Organized

A cache has to answer one question very quickly: do I have the block containing this
address? Searching every entry is out of the question at these speeds, so the address
itself decides where to look.

Split the address into three fields. The low bits are the offset within a block. The
middle bits are the index, which selects one set of entries. The remaining high bits
are the tag, which is stored alongside the data and compared against the incoming
address to confirm a hit.

If each set holds exactly one block, the cache is direct-mapped: lookup is a single
comparison and very fast, but any two hot addresses whose index bits collide will
evict each other repeatedly, even if the cache is mostly empty. If each set holds
several blocks — eight or sixteen ways is common today — the cache is set-associative,
and collisions only hurt once more than that many hot addresses land in the same set.
Associativity costs comparators, power, and a little latency, which is why first-level
caches are usually less associative than the levels behind them.

Misses come in recognizable kinds. Compulsory misses are unavoidable: the first
reference to a block has to come from somewhere. Capacity misses happen because the
working set is simply larger than the cache. Conflict misses are the avoidable
tragedy, where data was evicted despite room existing elsewhere in the cache, purely
because of how addresses mapped to sets. In a multiprocessor there is a fourth kind,
where a block is invalidated because another core wrote to it.

Writes add their own complications. A write-through cache sends every store onward
immediately, which keeps the next level consistent and burns bandwidth. A write-back
cache marks the line dirty and defers, writing it out only on eviction, which is what
nearly everything does today because most stores are to lines that will be written
again shortly. Either way, stores go through a buffer so the core does not stall
waiting for them to land.

None of these caches sit alone. A core typically has a small, extremely fast
first-level cache split into separate instruction and data halves; a larger
second-level cache private to the core; and a large last-level cache shared across
cores. Each step outward is roughly an order of magnitude larger and several times
slower. The hierarchy exists because you cannot have size and speed in one structure:
a cache big enough to hold a real working set is physically large, and a signal takes
time to cross a large structure.

## Address Translation, Prefetching, and Coherence

Three more mechanisms live in the same neighborhood, and all three follow the same
caching logic.

Programs use virtual addresses; hardware needs physical ones. The translation lives in
page tables in memory, and walking them would itself cost several memory accesses per
access. So the translations are cached, in a small associative structure called a
translation lookaside buffer. A TLB miss triggers a page walk, and on a program whose
data is scattered across thousands of pages, TLB pressure can dominate runtime even
when the data caches are behaving. Large pages exist mainly to relieve it.

Prefetchers turn observed patterns into speculative fetches. A hardware prefetcher
watches the stream of misses, detects that accesses are marching through memory at a
constant stride, and starts requesting blocks ahead of the program. Sequential access
is therefore far better than its raw miss count suggests: the misses are still there,
but the latency has been overlapped with useful work. Random access defeats
prefetching entirely, which is the deeper reason pointer-chasing code performs so
badly — each load's address is unknown until the previous load returns, so the misses
serialize instead of overlapping.

Coherence is the multicore problem. If two cores cache the same line and one writes
it, the other must not keep reading stale data. Hardware protocols track each line's
state — roughly: modified by this core, exclusively held, shared with others, or
invalid — and coordinate transitions by broadcasting on a bus or consulting a
directory. Correctness is preserved automatically, but not performance. Two threads
writing to different variables that happen to share a cache line will bounce that line
between cores on every write, each invalidating the other, with no logical conflict
whatsoever. This is false sharing, and padding two hot counters apart so they land on
separate lines has rescued more than one parallel program from running slower than its
serial version.

## Writing for the Hierarchy

You cannot control the cache directly, but you can decide what it sees.

Traverse arrays in the order they are laid out. Keep data that is used together
adjacent in memory, and consider splitting a structure so that a loop reading one
field of a million records is not dragging in eleven unused fields with each line.
Block large matrix computations into tiles that fit in the second-level cache, so each
tile is loaded once and reused many times rather than streamed through repeatedly.
Prefer flat arrays to linked structures when the access pattern permits, since a
vector of objects and a list of pointers to objects can differ by an order of
magnitude on the same traversal.

The unifying idea is that the hierarchy rewards predictability. The hardware is
running a continuous, fairly sophisticated bet that what you did a moment ago
resembles what you are about to do. Programs that make the bet easy to win run at the
speed of the cache. Programs that make it hard run at the speed of DRAM, and the
distance between those two speeds is most of the machine.
