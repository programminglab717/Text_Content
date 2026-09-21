# Buildings Designed to Be Damaged

An earthquake does not push on a building. This sounds like a quibble and it is
the whole basis of the discipline. The ground moves sideways out from under the
structure, and the structure, having mass and therefore inertia, declines to
follow. The forces that tear a building apart in an earthquake are the forces the
building generates on itself while being dragged along — mass times acceleration,
distributed floor by floor, with the heaviest and highest floors contributing
most.

That distinction has a practical consequence that runs counter to intuition.
Making a building heavier and stronger does not straightforwardly make it safer,
because the extra mass generates extra force. And making it stiffer can be worse
still, because stiffness determines how the building answers the particular
frequencies the ground is delivering. A great deal of seismic engineering is
about arranging for the building to be the wrong shape for the shaking, and then
about choosing, in advance and on paper, exactly where it will break.

## Period, and the Problem of Matching

Every structure has a natural period — the time it takes to sway out and back
once if you pull it sideways and let go. A stiff, squat shear-wall building might
have a period of a couple of tenths of a second. A tall steel frame might take
four or five seconds to complete a cycle. A rough field approximation used for
decades puts the fundamental period of a regular frame building at around a tenth
of a second per storey, which is close enough to be useful in a first
conversation.

Ground shaking is not a single frequency. It is a broadband mess, but it has
character: the amplitude at each period depends on the size of the earthquake,
the distance, and — decisively — the soil the site sits on. Soft deep sediment
amplifies long-period motion enormously while damping out the short-period
content that rock transmits happily. Engineers summarise all this in a response
spectrum, a curve showing the peak response that a simple oscillator of each
period would experience at that site, and they read their design forces off it.

The catastrophic case is resonance, and the clearest demonstration of it remains
Mexico City in 1985. The earthquake originated hundreds of kilometres away on the
Pacific coast. By the time the waves reached the city they had lost most of their
high-frequency content, but the central districts sit on the soft clay of a
drained lakebed, and that basin amplified motion at a period of roughly two
seconds by an extraordinary factor. Buildings of six to twenty storeys — the ones
whose natural period happened to sit near two seconds — were hit hardest. Shorter
and taller buildings in the same streets, subject to the same ground motion, came
through comparatively intact. The damage map was sorted by height.

## Strength Is the Wrong Target

If a building were required to remain elastic through a severe earthquake — no
yielding, no cracking, everything springing back exactly as it was — the member
sizes would be absurd and the cost prohibitive. Codes do not ask for this, except
for a narrow set of structures like nuclear plants and critical hospitals, and
even then not entirely.

Instead, design forces are reduced substantially below the true elastic demand,
in exchange for a promise that the structure will deform well past yield without
losing its ability to carry gravity load. That promise is ductility, and it is
the central bargain of seismic design. A ductile frame absorbs energy by
deforming inelastically — steel yielding, reinforcement stretching, concrete
cracking in a controlled way — and each cycle of that deformation dissipates
energy that would otherwise have to be resisted by sheer strength. The building
is expected to be damaged. It is expected to be damaged badly enough, in a rare
large event, that it may not be worth repairing. What it is not expected to do is
fall down while people are inside it.

The consequence is that seismic detailing matters more than seismic
calculation. Two buildings can have identical member sizes and identical
computed capacities and behave completely differently, because one has
reinforcement detailed to hold the concrete together after it cracks and the
other does not.

## Choosing the Failure

Capacity design is the formal name for deciding where the damage goes. The
logic: identify the places you want to yield, design them deliberately for the
reduced force level, and then make everything else in the load path strong enough
to deliver that yielding element's full overstrength capacity without failing
itself.

In a concrete or steel frame this means plastic hinges in the beams, not the
columns. A beam hinge is local damage; the floor sags, the frame survives. A
column hinge is the beginning of a storey collapse, because columns carry
gravity and a failed column has nothing above it to redistribute to. So the
columns at every joint are proportioned to be meaningfully stronger in bending
than the beams framing into them — strong column, weak beam, the phrase engineers
recite. Then the beams themselves must be made to yield in flexure rather than
shear, because flexural yielding is gradual and ductile while shear failure in
concrete is sudden and complete. That means transverse reinforcement sized not
for the beam's design shear but for the shear that develops when both ends have
hinged and are delivering everything they have.

The same thinking governs confinement. Concrete crushes at a modest strain when
unrestrained, but concrete held inside a tight cage of closely spaced hoops is
prevented from expanding laterally, and its usable strain increases several-fold.
Those hoops must be spaced closely through the hinge regions, and their hooks
must be bent back into the core of the member rather than into the cover, because
cover concrete spalls off early in a severe shake and takes any hook anchored in
it along.

Steel has its own version of the lesson, learned expensively. Welded moment
frames were considered the gold standard of ductile construction until the
Northridge earthquake in 1994, when inspectors opening up fireproofing found
brittle fractures running through the welded connections between beam flanges and
column faces in buildings that showed no external distress at all. The
connections had been assumed to develop the beam's full plastic capacity; instead
a combination of weld metal toughness, backing bar details, and severe stress
concentration at the joint produced cracks instead of yielding. The industry's
answer was, among other things, to move the hinge away from the weld — trimming
the beam flanges a short distance from the column face so that the reduced
section yields first and protects the connection. Engineers call it the dogbone.

## Shapes That Fail

Beyond detailing, some configurations are simply bad, and inspectors can pick
them off a street frontage.

The soft storey is the classic. A building with open parking or retail glazing at
ground level and stiff infilled walls above concentrates almost all of its lateral
deformation into that one flexible level. The upper floors translate more or less
as a rigid block, and the ground-floor columns take the entire drift demand. When
they fail, the building drops a storey. Northridge and many earthquakes since
produced photographs of apartment blocks sitting intact on the crushed remains of
their own carports.

Torsional irregularity is the other common one. If a building's lateral
resistance is not distributed symmetrically about its mass — a corner site with
solid party walls on two sides and glass on the other two is the standard example
— the structure twists as it sways, and the elements furthest from the centre of
rigidity are driven through far larger displacements than an analysis assuming
pure translation would predict. Re-entrant corners in L- and T-shaped plans
concentrate stress at the inside angle. Adjacent buildings with different periods,
built to the property line, batter each other as they sway out of phase, a
phenomenon called pounding that has knocked floors off buildings that were
otherwise performing well.

And none of the structural work matters if the ground stops behaving like ground.
Loose saturated sand shaken hard enough loses contact between its grains as pore
water pressure rises to meet the overburden, and briefly behaves as a heavy
liquid. Buildings on shallow foundations in liquefied soil tip, sink, or float
up, sometimes without cracking at all — Niigata in 1964 produced images of
apartment blocks lying on their sides essentially undamaged, and the Christchurch
sequence in 2010 and 2011 buried whole suburbs in ejected silt.

## Taking the Building Off the Ground

The most elegant answer to inertial loading is to stop transmitting it. A base-
isolated building sits on bearings — laminated rubber with a lead core, or
curved sliding surfaces — that are stiff vertically and deliberately flexible
horizontally. The isolators push the structure's period out to three seconds or
more, far away from the energetic short-period content of most strong shaking,
and the superstructure above rides along nearly rigidly while the isolation layer
absorbs the relative movement.

The cost is displacement. The building may need to move half a metre relative to
the ground, which means a moat around the perimeter, flexible joints on every
pipe and cable crossing the isolation plane, and stairs and lift shafts that can
tolerate the offset. It is expensive, and it is applied where continued function
after an earthquake is worth paying for: hospitals, emergency operations centres,
data facilities, and historic buildings too valuable to strengthen conventionally.

Supplemental damping does something related. Viscous or friction devices
installed in braced bays dissipate energy in the damper rather than in the frame,
reducing the inelastic demand on the structure itself. A tuned mass at the top of
a tall building — a suspended weight arranged to swing out of phase with the
structure — does something similar, though those are usually installed to make
upper floors comfortable in wind rather than to save the building from an
earthquake.

Which leaves the buildings nobody is retrofitting. Unreinforced masonry — brick
or stone walls with no steel in them, floors simply resting in pockets — has
killed more people in earthquakes than every other construction type combined,
because the walls have no tensile capacity and the floors are not tied to them.
Shake such a building and the walls peel away from the floors, the floors lose
their bearing, and the whole thing comes down as a pile of individual bricks. The
engineering to fix this has been understood for a long time. The obstacle has
never been technical.
