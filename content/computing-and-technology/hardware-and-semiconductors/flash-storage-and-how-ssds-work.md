# Flash Storage and How SSDs Work

A solid-state drive cannot change a single bit from zero back to one. To flip that
bit, the drive must erase a region containing perhaps a million other bits, most of
which it will then have to rewrite. Nothing in the interface hints at this. The
operating system sends a request to overwrite four kilobytes at a particular address,
the drive says it is done, and underneath, a small dedicated computer has just made a
series of decisions about where to actually put the data, what to eventually reclaim,
and how to hide the mismatch. Almost every surprising behavior of flash storage — why
a full drive slows down, why benchmarks look different after an hour of use, why
drives wear out at all — comes from that gap between the interface and the medium.

## A Transistor That Remembers

The storage element is a modified version of the same field-effect transistor that
does logic. In a normal transistor, a voltage on the gate creates a conducting channel
between source and drain. In a flash cell, a second gate is buried inside the
insulating oxide beneath the control gate, electrically isolated on every side.

Put electrons onto that isolated gate and they have nowhere to go. Their negative
charge partially cancels the field from the control gate above, so the cell now needs
a higher control-gate voltage before it will conduct. That shift in threshold voltage
is the stored bit. Read it by applying an intermediate voltage and observing whether
the cell turns on. Because the trapped charge sits inside an insulator, it stays put
with the power off, for years.

Getting electrons in and out requires persuading them through an insulator that exists
precisely to stop them. The usual mechanism is quantum tunneling: apply a strong
enough field across a thin enough oxide and a fraction of the electrons appear on the
other side. That works, and every time it happens it does a little damage. Charge gets
stranded in the oxide, defects accumulate, and the voltage window between the states
gradually narrows. Flash wears out because writing to it is mildly destructive by
construction. Newer designs substitute a nitride layer that traps charge in discrete
sites rather than a conductive floating gate, which is more tolerant of a defect
punching through the oxide, but the basic bargain is unchanged.

## Pages, Blocks, and the Asymmetry

The cells are wired into long series strings, an arrangement called NAND flash, which
gives the highest density at the cost of random access. You cannot address one cell
independently; you work with whole rows.

The read and program unit is a page, historically a few kilobytes, now often sixteen
kilobytes or larger. The erase unit is a block, which gathers hundreds or thousands of
pages together — several megabytes at least. Erasing sets every cell in the block to
the same state, conventionally read as all ones. Programming then selectively pushes
cells the other way, turning ones into zeros. It cannot go backward. Once a page is
programmed, the only route to a different value runs through erasing the entire block
it lives in.

Erase is also slow, by orders of magnitude. A read takes tens of microseconds. A
program takes hundreds. An erase takes milliseconds. Any design that made the host
wait on erases would be unusable, so the drive never erases on the critical path if it
can avoid it.

Density is pushed further by storing more than one bit per cell. Instead of two
threshold levels, use four, eight, or sixteen, and read out two, three, or four bits.
Each additional bit halves the voltage margin between adjacent states, which makes
everything harder: programming requires a careful sequence of small pulses with
verification between them, reading requires more sensing steps, and the cell tolerates
far less wear before its states start to overlap. Single-level cells endure on the
order of tens of thousands of program-erase cycles. Three-bit cells endure a few
thousand at best, four-bit cells fewer still. The industry took that trade anyway,
because capacity per dollar is what sells drives, and it compensated in the controller.

## The Translation Layer Is the Real Product

Because pages cannot be updated in place, the drive maintains a moving map. Every
logical address the host uses is translated to some physical page, and that mapping
changes constantly. This flash translation layer, running on the controller, is where
most of a drive's engineering effort goes.

When the host overwrites a logical block, the drive does not touch the old physical
page at all. It writes the new data to a fresh, already-erased page somewhere
convenient, updates the map, and marks the old page invalid. Writes therefore land
sequentially into erased blocks regardless of how random the host's access pattern
was, which suits the medium well.

The consequence is that invalid pages accumulate, scattered through blocks that also
contain valid data. Reclaiming them is garbage collection: pick a block, copy its
still-valid pages elsewhere, erase it, return it to the free pool. Those copies are
writes the host never asked for. The ratio of physical writes to host writes is called
write amplification, and it is the number that governs both how fast a drive feels and
how long it lasts.

Write amplification depends almost entirely on how much free space the drive has to
work with. If most blocks are nearly all invalid, a garbage collection pass copies
little and frees a lot. If most blocks are nearly all valid, the same pass copies
almost a full block's worth of data to free one block. This is why drives slow down as
they fill, why every drive reserves capacity the host can never see — over-provisioning
— and why leaving a drive somewhat empty measurably improves both throughput and
lifespan.

It is also why the TRIM command matters. Without it, a drive has no idea that a file
was deleted; from its perspective those logical blocks still hold data it is obliged
to preserve. TRIM lets the filesystem tell the drive which blocks are dead, converting
them instantly into garbage-collection slack.

Wear leveling runs alongside. Since blocks fail after a limited number of cycles, the
controller spreads erases evenly, tracking cycle counts and steering writes toward
less-used blocks. It also periodically relocates cold data that has been sitting
untouched in a low-wear block, since a block full of static data would otherwise be
excused from wear-leveling duty entirely while its neighbors burned out.

## Keeping the Bits Readable

Raw NAND is not reliable storage. It is barely reliable at all, and the controller's
error correction is what makes it usable.

Charge leaks. Retention degrades with wear and accelerates with heat, so a heavily
cycled drive left unpowered in a warm place is the worst case for data survival.
Reading also disturbs: sensing one page requires driving the other cells in the string
into conduction with a pass voltage, which nudges their charge slightly. A block read
many thousands of times without being rewritten will eventually accumulate enough
disturbance to need refreshing, which the controller does on its own.

Against all of this, every page carries substantial spare area for error-correcting
codes. Early drives used algebraic codes that corrected a fixed number of bit errors
per page. Modern ones use low-density parity-check codes, which do better and, more
importantly, can use soft information: if a page fails at the normal read threshold,
the controller re-reads it at several shifted voltages to learn not just what each bit
probably is but how confident that reading is, and feeds those likelihoods to the
decoder. It is slower, which is why a drive nearing end of life often shows read
latency climbing before it shows outright failures.

## Where the Speed Comes From

An individual flash die is not fast. A drive gets its performance from doing many
things at once: several independent channels between controller and flash, several
dies per channel, and multiple planes per die that can operate in parallel. A large
sequential read is striped across all of them. This is also why small-capacity models
in a product line are often slower than large ones — fewer dies, less parallelism.

Two more tricks shape everyday behavior. Most consumer drives run part of their flash
in single-bit mode as a fast write cache, absorbing bursts at high speed and folding
the data down into denser cells later during idle time. That is why a large file copy
often starts quickly and then drops to a much lower sustained rate once the cache is
exhausted. And the mapping table itself is large — roughly a gigabyte of DRAM per
terabyte of capacity for fine-grained maps — so drives either include DRAM or borrow a
slice of host memory through the storage protocol, with performance on random access
differing noticeably between the two approaches.

Stacking the cells vertically, in strings that run up through hundreds of deposited
layers rather than across the wafer surface, changed the economics again. It let the
industry stop shrinking individual cells — which had been making retention and
endurance steadily worse — and add capacity by adding layers instead. The cell got
roomier and better behaved even as the drive got denser, which is an unusual direction
for semiconductor progress to run.
