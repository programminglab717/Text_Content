# CPU Pipelines and Instruction-Level Parallelism

A program, read on the page, is a queue. One instruction, then the next, each
finishing before its successor begins. That mental model is a promise the hardware
makes to the programmer and then breaks in private, thoroughly, at every opportunity.
Inside a modern processor core, a couple of hundred instructions may be in flight at
once, executed in whatever order their dependencies permit, with results held back
and retired in program order only so the illusion survives inspection. Nearly all the
performance a single core delivers comes from how aggressively it breaks that
promise while getting away with it.

The reason is arithmetic. A processor's throughput is instructions per cycle times
cycles per second, and the second term has been roughly flat for two decades. The
only place left to look is the first.

## Cutting the Work into Stages

Executing one instruction involves several unrelated kinds of work: fetching the
bytes from memory, figuring out what they mean, reading the operands, doing the
arithmetic, touching memory if required, and writing the answer into a register. A
naive machine does all of it inside one long clock cycle, and the clock must be slow
enough to accommodate the worst case. Almost all of the hardware sits idle almost
all of the time.

Pipelining fixes the idleness the way an assembly line does. Split the work into
stages separated by latches, and let each stage hold a different instruction. The
canonical textbook arrangement has five: fetch, decode, execute, memory, writeback.
Each instruction still takes five cycles to traverse the pipe, so latency is
unchanged or slightly worse, but a finished instruction now emerges every cycle
instead of every fifth cycle. Throughput multiplies. Better, the clock period is now
set by the slowest single stage rather than by the whole chain, so the clock itself
can run faster.

The catch is that instructions are not independent items on a conveyor. They talk to
each other, and a pipeline surfaces three ways that conversation can go wrong.

Structural hazards happen when two instructions need the same piece of hardware in
the same cycle — a single memory port serving both instruction fetch and data access,
for example. The usual answer is to build more hardware, which is why caches for
instructions and data are separate at the first level.

Data hazards are more interesting. If one instruction computes a value and the next
one reads it, the reader arrives at the register file before the writer has written.
The brute-force fix is to stall. The better fix is forwarding: notice that the result
already exists at the output of the execute stage, one cycle before it reaches the
register file, and route it backward along a bypass path directly into the waiting
instruction's operand latch. A tangle of bypass wiring eliminates most data stalls
outright. It cannot eliminate all of them — a value loaded from memory is not
available until after the memory stage, so an instruction that consumes a load result
immediately must wait at least a cycle regardless.

Control hazards are the worst of the three. A branch is not resolved until it has
been decoded and its condition evaluated, by which point the fetch unit has already
pulled in several instructions from an address that may be wrong. On a five-stage
pipeline, throwing away two or three cycles per branch is painful but survivable.
Deepen the pipeline to twenty stages — which is what chasing clock frequency
requires, since each stage does less work and can therefore be clocked faster — and
the penalty for guessing wrong becomes catastrophic. Roughly one instruction in five
or six is a branch.

## Guessing, and Getting Very Good at It

The answer was to guess, and then to make the guessing extraordinarily accurate.

The earliest predictors were static: assume backward branches are taken, since they
are usually loop bottoms, and forward branches are not. Then came dynamic
predictors — a table of small saturating counters indexed by branch address, each
counter nudged toward "taken" or "not taken" by the outcome, requiring two wrong
guesses in a row to flip its prediction and so riding out the single mispredict at
the end of a loop.

Counters alone miss correlated behavior. A branch that alternates taken and not-taken
defeats them; so does a branch whose outcome depends on an earlier branch's outcome.
Two-level predictors fixed this by recording a shift register of recent branch
outcomes and using that history, hashed together with the branch address, to select
which counter to consult. The same static branch then gets different predictions
depending on the path taken to reach it. Later designs run several predictors with
different history lengths in parallel and arbitrate among them, so a branch that
needs only short history is not polluted by long-history noise, and one that needs
fifty branches of context can get it.

Alongside them sit a branch target buffer, which caches where a taken branch went so
the fetcher can redirect before decoding anything, and a small hardware stack that
pairs calls with returns, since a return's target is otherwise unpredictable but
almost perfectly determined by the call that preceded it. On ordinary code, modern
predictors are wrong on the order of a few branches per thousand. That accuracy is
what makes deep pipelines and wide issue affordable at all.

## Widening the Machine, Then Reordering It

Pipelining overlaps instructions; it does not execute more than one per cycle.
Superscalar designs do, by duplicating the functional units and fetching, decoding,
and issuing several instructions per cycle. Immediately you need to know whether any
of the instructions issued together depend on each other, and the dependence-checking
logic grows roughly with the square of the issue width. This is one reason cores stop
getting wider at some point rather than growing indefinitely.

The deeper problem with in-order superscalar execution is that a single stalled
instruction blocks everything behind it, including instructions that are perfectly
ready. A cache miss taking a couple of hundred cycles will drain the machine even if
the next fifty instructions have nothing to do with the missing data.

Out-of-order execution dissolves that blockage. Instructions are decoded in order and
deposited into a pool; each one waits there until its operands are available and a
suitable functional unit is free, then executes whenever that happens, regardless of
its position in the program. The architectural ideas came out of work Robert Tomasulo
did on an IBM mainframe's floating-point unit in the 1960s, and they became
mainstream in commercial microprocessors in the mid-1990s.

Two mechanisms make it safe. The first is register renaming. Much of the apparent
dependence between nearby instructions is false — two unrelated computations reusing
the same architectural register name because the compiler ran out of names. The
hardware maintains a much larger pool of physical registers and assigns a fresh one
to every result it produces, so the only dependences that survive are the real ones,
where a value genuinely flows from producer to consumer.

The second is the reorder buffer. Results computed out of order are held there and
written to architectural state only when every older instruction has also completed,
in strict program order. That in-order retirement is what preserves the illusion. If
an instruction faults, or a branch is discovered to have been mispredicted, every
speculative instruction younger than it is simply discarded, its physical registers
reclaimed, and fetch restarted down the correct path. The machine can be wrong at
high speed as long as it is never wrong in public.

## Where the Free Lunch Ended

For about fifteen years this approach delivered compounding gains, and then it
stopped. Several walls arrived at once.

There is only so much parallelism in real programs. Studies of the available
instruction-level parallelism in ordinary integer code, with perfect prediction and
unlimited hardware, tend to find that it runs out well below what a very wide machine
could consume. Pointer-chasing code — traversing a linked structure, where each
address depends on the value just loaded — is close to purely serial no matter how
much hardware you point at it.

The structures that extract parallelism also scale badly. Doubling the instruction
window means larger schedulers, more comparators, longer wires, more energy per
instruction. Each additional increment of performance costs more transistors and
considerably more power than the one before, and by the early 2000s the power budget
had become the binding constraint. That is what ended the frequency race and sent
the industry toward multiple cores, which pushes the parallelism problem out of the
hardware and onto the programmer.

An explicit alternative had been tried and had mostly failed: very long instruction
word designs, which ask the compiler to find the parallelism ahead of time and bundle
independent operations together, dispensing with expensive dynamic scheduling
hardware. It works beautifully on code whose behavior is statically predictable, and
poorly on code where a cache miss can make the right schedule depend on a runtime
outcome the compiler could never have known.

And then there is the bill that came due in 2018, when researchers showed that
speculation leaves fingerprints. Instructions executed down a mispredicted path are
architecturally erased, but their effects on the cache are not, and a carefully
constructed program can time its own memory accesses to read those traces. The
illusion, it turned out, was never quite complete. Fixing it has meant partitioning
predictors, flushing buffers at privilege boundaries, and in some cases simply
declining to speculate — paying back, in performance, some of what speculation had
been quietly borrowing all along.
