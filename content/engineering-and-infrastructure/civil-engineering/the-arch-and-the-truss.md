# The Arch and the Truss

The most dangerous moment in building a masonry arch comes at the end, when the
work looks finished. Until the last wedge of stone goes into the crown, the arch
is not an arch at all — it is a pile of blocks resting on a timber framework
called the centering, and the centering is carrying everything. Only when the
ring is closed can the stones press against each other hard enough to hold
themselves in place. Then the carpenters knock out the wedges beneath the
centering and lower it away, and the arch settles by a few millimetres onto its
own compression, and either it stands or it does not. Roman builders called this
striking the centering, and there is a long tradition of the man who designed
the arch being made to stand underneath it while it happens.

An arch works because it converts a downward load into compression running
around the curve. Stone and brick and concrete are enormously strong when
squeezed and almost useless when pulled — a granite block will take tens of
megapascals of compression and split under a fraction of that in tension. The
arch is the geometry that lets a material with that lopsided personality span a
gap. Each voussoir leans on its neighbours, the load runs down through the ring
as a chain of thrusts, and no stone is ever asked to do the thing stone is bad
at.

## Where the Thrust Goes

The internal force in an arch can be pictured as a line — the thrust line —
tracing the path the compression takes from crown to springing. An arch does not
have a single thrust line; it has a family of them, because a masonry arch is
statically indeterminate and can redistribute force as it cracks and settles.
This is the basis of the way engineers now assess old masonry, usually credited
to Jacques Heyman, who formalised the idea that an arch is safe if you can find
any equilibrium thrust line that stays inside the masonry. It does not have to
be the real one. If one exists, the arch will find it. That is why a medieval
bridge with visible cracks in its vaults can be entirely sound: the cracks are
how the structure moved to a thrust line it liked better.

What the thrust line will not do is arrive at the ground pointing straight down.
It leaves the springing at an angle, and the horizontal part of it has to be
resisted by whatever the arch stands on. Everything heavy and expensive about
arched architecture follows from that horizontal push. The Roman answer was
mass: piers thick enough that the combined weight of pier and thrust stayed
comfortably inside the base. Where arches are built in a row, as in an aqueduct
or a viaduct, the thrusts from neighbouring spans cancel at every intermediate
pier, and only the end piers or abutments have to take the full push — which is
why arcades are cheap per span and why a collapse in one span of an old viaduct
tends to bring down its neighbours.

Gothic builders attacked the same problem from a different direction. A pointed
arch of a given span can be made as steep as you like, which means the thrust
comes down at a steeper angle and there is less of it to push sideways. It also
decouples span from height: semicircular arches of different spans meeting at
one vault rise to different heights, while pointed arches of different spans can
all be brought to the same crown. Ribbed vaulting then concentrated the load
into identifiable lines of thrust, which could be met by buttresses. And when
the buttresses grew so deep that they would have swallowed the aisles, the
builders leapt the thrust outward over the aisle roofs on a flying buttress and
caught it on a free-standing pier outside. The stone pinnacles stacked on top of
those piers are not only ornament. Adding vertical weight to a buttress steepens
the combined force inside it and pulls the thrust line back toward the middle of
the masonry, which is exactly what keeps the pier from hinging open.

Nobody in the thirteenth century wrote any of this down as mechanics. It was
learned by proportion, by apprenticeship and by watching things fall. The
physics arrived much later. Robert Hooke stated it in the 1670s in a Latin
anagram whose solution translates roughly as: as hangs the flexible line, so but
inverted will stand the rigid arch. A hanging chain finds a shape in pure
tension for whatever loads hang on it; turn that shape upside down and you have
a shape in pure compression for the same loads. In the 1740s Poleni used
precisely this idea to assess the cracked dome of St Peter's, loading a chain
with weights in proportion to the dome's own and checking that the inverted
curve fitted within the masonry. A century and a half after that, Gaudí built
hanging models of strings and small bags of lead shot for the Colònia Güell
chapel, photographed them, and turned the photographs upside down to draw the
building.

## The Triangle, and Why Iron Changed the Question

An arch demands abutments that can take a horizontal shove. If you are bridging
a rocky gorge that is a gift. If you are building a railway across a soft valley
floor on a tight schedule, it is a serious problem, and the problem gets worse
as the span grows.

Iron removed the reason to avoid tension in the first place. Wrought iron, and
later steel, is roughly as strong pulled as pushed. A structure made from it
does not need to be shaped so that every member is in compression, which opens
up a completely different family of solutions — ones that can be built to
deliver their load to the abutments straight down, with no sideways thrust at
all.

The device that does this is the truss, and its whole logic rests on one
geometric fact. Take four bars and pin them at the corners into a quadrilateral:
the shape collapses into a parallelogram at the slightest push. Do the same with
three bars and it cannot move at all without changing the length of a bar. The
triangle is the only polygon that is rigid at its joints without relying on the
joints being stiff. Assemble triangles into a chain and you get a beam whose
members, because the joints are effectively hinges and loads arrive only at
those joints, carry force along their own length and nothing else. No bending,
no shear inside a member — just push or pull.

Read a simple truss and it decodes quickly. Under a downward load the top chord
is in compression and the bottom chord in tension, exactly as the top and bottom
of a solid beam would be; the difference is that the material in between, which
in a solid beam is mostly along for the ride, has been removed and replaced by a
sparse web of diagonals and verticals whose job is to carry shear from the load
out to the supports. That is why a truss is so much lighter than a plate girder
of the same depth, and why deep trusses are so much more efficient than shallow
ones.

The named patterns are variations on how to arrange that web. In a Howe truss
the diagonals slope toward the centre and end up in compression while the
verticals take tension; in a Pratt truss the diagonals slope the other way and
the arrangement flips. For timber-and-iron construction the Howe made sense,
because the long diagonals could be wood in compression and the short verticals
iron rods in tension. For all-metal construction the Pratt won decisively, since
a long member in compression buckles and a long member in tension does not, and
the Pratt keeps the long members pulling. A Warren truss dispenses with
verticals altogether and alternates diagonals in tension and compression, which
is elegant and economical and slightly awkward to load at arbitrary points.

Nineteenth-century America built trusses faster than it could analyse them,
patenting a new configuration every few years, and it took people like Squire
Whipple, who published a treatise on bridge building in the 1840s, to establish
that the forces in a truss could be calculated rather than guessed. Once the
joints are treated as pins and the members as two-force bars, the whole
structure yields to simple statics: isolate a joint, resolve horizontally and
vertically, move to the next. Suddenly a bridge could be sized rather than
proportioned by precedent, and the size of members could be checked against the
tested strength of the iron.

What calculation did not immediately fix was everything in a truss that is not a
bar. Trusses fail at their connections and in their compression members far more
often than they fail by a tension member reaching its strength. The Quebec
Bridge collapse of 1907 was a buckling failure of a built-up compression chord
whose latticing was inadequate for its size — a member that had been calculated
as if compressive strength scaled the way tensile strength does. When a highway
truss in Minneapolis dropped into the Mississippi in 2007, investigators traced
it to gusset plates that had been made too thin at the design stage and had
spent decades quietly accumulating extra deck weight. In both cases the members
were fine. It was the places where forces changed direction that gave way.

The arch and the truss are answers to the same question asked of different
materials, and the answers keep converging. A steel arch bridge is a truss bent
into a curve and told to thrust. A concrete arch has steel in it precisely where
the thrust line threatens to wander out of the section. What has not changed
since the Romans is that the last block still has to go in before the thing will
stand up.
