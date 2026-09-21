# How Railway Signalling Keeps Trains Apart

A car driver stops inside the distance they can see. Headlights, sightlines
and braking distance are matched closely enough that the whole arrangement
works on that single assumption, and a driver who outruns their visibility is
considered to be at fault. A train has no such luxury. A loaded freight
consist rolling at sixty miles an hour may need well over a mile of track to
come to a stand, and nobody can see a mile down a line that curves, drops
into a cutting, or fills with fog at four in the morning. The train also has
nowhere to swerve. Two rails fix the path, and the only variable left to the
person at the front is speed.

Everything that gets called signalling follows from the gap between stopping
distance and sighting distance. The job is to hand the driver information
about track they cannot yet see, early enough to act on it, and to keep that
information truthful even when the equipment providing it has broken.

## From Time to Space

The earliest railways tried to manage the problem with a pocket watch. A
train left a station, and the policeman at the end of the platform held the
next one for a fixed interval — five minutes, then ten — on the theory that
a constant gap in time implied a safe gap in distance. The theory is only as
good as its assumption that the first train keeps moving. When it stopped,
which in the era of unreliable locomotives it frequently did, the interval
decayed to nothing and the second train arrived at whatever speed it happened
to be making.

The electric telegraph broke the deadlock. Once two signal boxes could talk
to each other in seconds, the line between them could be treated as a section
holding exactly one train at a time. A box would not accept a train from the
box behind until the previous one had been seen to pass, in one piece, with
its tail lamp still burning. This is absolute block working, and the tail
lamp mattered more than it sounds: the point of the check was to prove that
nothing had been left behind in the section.

Britain made block working compulsory after a disaster at Armagh in 1889. An
excursion train stalled on a gradient, the crew uncoupled the rear portion
intending to take the front half forward and come back for it, and the
detached carriages — with nothing but a handbrake between them and gravity —
ran back down the hill into a following train. Close to eighty people died,
many of them children on a Sunday school outing. The Act that followed within
months required three things: block working, the interlocking of points and
signals, and continuous automatic brakes on passenger trains. Those three
requirements sit underneath almost everything built since.

## Interlocking

A signal box controls two kinds of thing. Signals tell drivers whether they
may proceed; points decide where they go. Left independent of each other they
are a trap. A signalman can clear a signal for a route whose points are lying
towards the flank of another train, and the mistake stays invisible until it
is no longer a mistake but a collision.

Interlocking is the mechanical refusal to allow that. In the lever frames
that John Saxby and his contemporaries developed in the middle of the
nineteenth century, the levers in a box are tied together beneath the floor
by a lattice of sliding bars and notched tappets. Pulling the lever for a
route physically locks the point levers into the positions that route
requires, and locks every signal lever that would give a conflicting move.
The signalman is not asked to remember. The frame simply will not move.

The logic long outlived the mechanism. Relay interlockings replaced tappets
with racks of safety relays whose contacts were arranged so that gravity
dropped them into the restrictive state the instant a coil lost power.
Solid-state interlockings replaced the relays with processors, usually two or
three of them running the same logic and comparing answers, because a single
computer cannot be trusted to notice its own failure. What is being enforced
has not changed since Saxby: no signal shows a proceed aspect unless every
set of points in the route is detected in the correct position and locked
there, and every conflicting move is barred for as long as the route is set.

## Knowing Where the Train Is

Block working proved a section clear by having a human watch a train go by.
The track circuit lets the track prove it for itself. An American engineer,
William Robinson, worked out the essential trick in the 1870s: feed a small
current into the rails at one end of a section, put a relay across them at
the other, and hold that relay energised for as long as nothing is in the
way. A wheelset entering the section short-circuits the two rails through its
steel axle, the relay drops out, and the section reports itself occupied.

The elegance is in the failure modes rather than the successes. A broken
feed, a flat battery, a cracked rail, a corroded bond — every one of them
interrupts the current and drops the relay, and a dropped relay means
occupied. The system's default answer is the cautious one. Signal engineers
call this a right-side failure, and they spend their careers hunting the
opposite: the wrong-side failure, the fault that shows a line clear while a
train is standing on it.

Track circuits have limits. They leak through wet ballast, they sulk on
lightly used sidings where rust insulates the railhead, and they consume a
great deal of copper. Newer installations often use axle counters instead: a
sensor head at each end of a section counts wheels in and wheels out, and the
section is declared clear when the two totals agree. Axle counters do not
detect a broken rail, which a track circuit does almost as a by-product, and
that trade-off gets argued over every time a route is resignalled.

## Telling the Driver

A stop signal is useless if the driver meets it at the last moment, so every
stop signal needs a warning placed far enough back to brake from line speed.
On a two-aspect railway that warning is a separate distant signal — yellow
for caution, green for clear. Pack the trains closer together and the distant
for one stop signal ends up behind the previous one, so the aspects get
stacked into the same heads: green for a clear road, double yellow for two
sections to go, single yellow for one, red for stop. A four-aspect layout
lets trains run at roughly half the spacing of a two-aspect one at the same
speed, which is why the approaches to busy termini look like Christmas trees.

Drivers being human, the industry stopped relying on them seeing the light.
British lines carry a magnet between the rails at each distant position: a
clear aspect gives the cab a bell, anything else gives a horn that must be
acknowledged within a couple of seconds or the brakes go on by themselves.
That warns without enforcing, so it was later supplemented with speed traps
at the worst signals — paired loops that time a train over a short distance
and apply the brakes if it is approaching too fast, or has already passed a
red. Elsewhere the enforcement was designed in from the beginning. The German
continuous system, the various national protection systems across Europe, and
the coded cab signals injected into the rails in North America all supervise
the speed rather than merely nagging about it.

Above roughly two hundred kilometres per hour, lineside signals stop working
altogether, because a driver cannot reliably read a coloured light that is in
view for a second and a half. The Japanese saw this before the first
Shinkansen ran and built the line with no lineside signals at all, putting
the movement authority on a display in front of the driver. Every high-speed
railway since has done the same.

## Shrinking the Block

Fixed blocks waste track. A section is either occupied or it is not, so a
train sterilises the whole of it whether it is at the near end or the far
end, and capacity ends up set by the length of the sections rather than the
length of the trains. Cutting the sections shorter helps, up to the point
where the cost of the equipment and the number of things that can fail
overtake the benefit.

The alternative is to stop dividing the line into sections at all. If a train
can measure its own position accurately, report it continuously by radio, and
receive in return an authority that reaches to a point just short of the
train ahead, then safe separation becomes a moving envelope rather than a
queue of boxes. That is what the higher levels of the European train control
system aim at, and what the communications-based systems now standard on new
metros already deliver. The catch is the rear of the train. A radio link
cannot tell you that a coupling has failed and left four wagons standing in
the dark, so proving train integrity becomes the hard part — which is why
moving block arrived first on metros running fixed formations, and has taken
far longer to reach mixed-traffic railways where trains are assembled from
whatever wagons turned up.

None of it alters the arithmetic underneath. Steel on steel gives up very
little friction, brakes propagate slowly down a long train, and the distance
needed to stop stays stubbornly longer than the distance anyone can see.
Every layer added over a century and a half — the telegraph, the tappet lock,
the relay, the radio — exists to close that gap with information, because it
cannot be closed with brakes.
