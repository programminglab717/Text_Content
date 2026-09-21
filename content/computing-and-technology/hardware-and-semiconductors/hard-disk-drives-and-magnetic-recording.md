# Hard Disk Drives and Magnetic Recording

Pick up a three-and-a-half-inch hard drive and the first thing you notice is the
weight. It is heavier than it looks, most of that mass in a cast aluminum housing
machined to hold a spindle in place under load, and when you tilt it quickly in your
hand you can feel the platters resist, a small gyroscopic shove against the motion.
It is a piece of precision rotating machinery that happens to be sold as a computer
component. Inside, a read head the size of a dust mote skims a few nanometers above a
surface moving past it at highway speed, close enough that a smoke particle in the
gap would be a boulder, and it does this continuously for years.

Every other component in a computer became solid state. This one never did, and the
reason is not nostalgia. Per bit stored, nothing else is as cheap.

## From a Refrigerator to a Pocket

The first commercial disk drive shipped from IBM in 1956 as part of a system called
RAMAC. It was a cabinet the size of a couple of large appliances, containing fifty
platters two feet across, spinning together, with a single head assembly that moved
in and out and up and down to reach any one of them. Total capacity was around five
million characters. What made it remarkable was not the amount but the access: unlike
tape, which had to be wound past the head to reach anything, a disk could reach any
record in a fraction of a second. The word "random" in random-access memory describes
exactly this property, and disks gave computing its first cheap version of it.

Two changes turned that cabinet into the object in your hand. The first was the air
bearing. A head does not touch the disk; it rides on a thin cushion of air dragged
along by the spinning surface, and the slider is shaped so that the lift from that
cushion balances against a spring pressing it down. Equilibrium sets the flying
height. Early drives needed the head to be unloaded onto a ramp or parked before
stopping; the designs that emerged in the 1970s made heads light enough to take off
and land on the disk itself, and sealed the whole head-disk assembly in a filtered
enclosure so that the gap could shrink without dust destroying it. The lower the head
flies, the smaller a magnetized region it can read, and flying height has fallen from
micrometers to a few nanometers since.

The second was positioning. Early actuators used stepper motors, which move in fixed
increments and drift with temperature. Modern drives use a voice coil — the same
motor principle as a loudspeaker — driven by a feedback loop that reads position
information written into the disk surface itself at the factory. Thin wedges of servo
data, interleaved between the data sectors, tell the electronics thousands of times
per revolution exactly where the head sits relative to track center. The arm is
therefore never simply commanded to a position; it is continuously corrected, riding a
track that wobbles slightly as the platter warms, flexes, and ages.

## What the Head Actually Does

Recording works by orienting small regions of a magnetic film. The film is a granular
cobalt-platinum alloy, deposited so that it forms tiny crystalline grains separated by
a non-magnetic material that keeps each grain from dragging its neighbors along. A
recorded bit is not one grain. It is a cluster of many, and the read signal is
essentially an average over them, which matters because the randomness of grain
boundaries is the dominant noise source in the channel.

Writing is done by an electromagnet: a coil wrapped around a tiny magnetic yoke with
a gap at the tip. Current through the coil produces a fringing field at the gap strong
enough to flip the grains passing beneath it. Reverse the current and you flip them
the other way. This part has not changed in principle since magnetic recording was
invented.

Reading changed completely. The original heads were inductive — a moving magnetic
field induces a voltage in a coil — but induced voltage depends on how fast the field
changes, and as bits got smaller the signal got hopeless. The replacement was a sensor
whose *resistance* changes in a magnetic field, so it can be read with a steady
current and does not care about speed. The breakthrough version came from giant
magnetoresistance, discovered independently in the late 1980s by Albert Fert and Peter
Grünberg, who shared a Nobel Prize for it. A stack of alternating magnetic and
non-magnetic layers only a few atoms thick shows a large resistance change depending on
whether adjacent magnetic layers are aligned, and if one layer is pinned while the
other is free to follow the field from the disk, the stack becomes an exquisitely
sensitive field sensor. Later heads use a thin insulating barrier and read the
tunneling current instead, which is more sensitive still. The industry's density curve
bends visibly upward when these sensors arrived.

For decades the recorded magnetization lay in the plane of the disk, with bits
arranged head-to-head and tail-to-tail along the track. Packed tightly, neighboring
regions oppose each other and push toward demagnetizing. The fix, adopted across the
industry in the mid-2000s, was to stand the magnetization on end. In perpendicular
recording, each bit points up or down through the film, adjacent bits sit alongside
each other in a more stable arrangement, and a soft magnetic underlayer beneath the
recording film acts as a mirror that concentrates the write field and gives it a
return path. It bought a large jump in density from what was, geometrically, a
ninety-degree rotation.

## The Wall Everything Runs Into

Shrinking a bit means using fewer grains, and fewer grains means a noisier signal. The
obvious answer is to make the grains smaller so you can still fit a decent number into
a bit. But a grain's magnetic stability depends on its volume multiplied by the
material's resistance to being reoriented. Shrink the volume and, at some point,
ordinary thermal energy at room temperature is enough to flip a grain on its own. The
stored data slowly randomizes. This is the superparamagnetic limit, and it has been
the field's looming obstacle for a long time.

You can compensate by choosing a material that resists reorientation more strongly.
Then you run into the other side of the problem: the write head has to be able to flip
those grains, and the field a head can produce is capped by the saturation
magnetization of the materials available to build it. Small grains, stable grains,
writable grains — you can have any two.

Two routes around it are in production or near it. Shingled recording gives up on the
write head's width. Since a write head lays down a wider track than a read head needs,
tracks are written overlapping like roof shingles, with each new track trimming the
previous one. Density rises with no change to the physics. The cost is that you can no
longer rewrite a single track without destroying the ones downstream of it, so the
surface is divided into bands and updates within a band require reading and rewriting
the rest of it. Shingled drives are excellent for data written once and read often,
and can behave erratically under random overwrite unless the host understands what it
is holding.

The other route is heat. In heat-assisted recording, a laser is routed down the head
through a plasmonic antenna that focuses light into a spot far smaller than the
wavelength, heating a tiny region of the disk to near its Curie temperature for a few
nanoseconds. Hot, the material briefly loses most of its resistance to reorientation
and an ordinary head field can write it; cooling in nanoseconds, it becomes extremely
stable again. This permits a material stable enough for grains far smaller than
anything conventional recording can use. Making it survive is the hard part, since it
means firing a laser into a component flying nanometers off a surface, billions of
times, without degrading the head or the lubricant on the disk.

## The Other Half of the Engineering

A drive is also a fluid-dynamics problem. Platters spinning at five to fifteen
thousand revolutions per minute drag air around with them, and that airflow buffets
the arm and makes the platters themselves flutter. Filling the enclosure with helium
instead of air, and sealing it permanently, cuts the drag substantially — less
turbulence, less power, cooler running, and enough mechanical calm to stack more
platters into the same height. High-capacity drives have been built this way for years.

And it is a signal-processing problem. What comes off the head is not a clean sequence
of ones and zeros but a smeared analog waveform with grain noise on top. The
electronics sample it, equalize it, and run a sequence detector that finds the most
likely recorded pattern rather than deciding bit by bit, then hand the result to an
error-correcting decoder powerful enough to fix errors that are frequent by design.
The raw channel is intentionally run at an error rate that would be unusable without
correction, because that is where the density is.

What remains, after all of it, is a spinning platter and a coil. The access time is
still governed by how fast an arm can swing and a disk can turn — a few milliseconds,
a figure that has improved only modestly in decades while everything electronic around
it improved by orders of magnitude. Flash won the argument about latency long ago.
Disks kept the argument about cost, and they keep it by continuing to squeeze more
bits onto a surface whose physics has been declared exhausted several times already.
