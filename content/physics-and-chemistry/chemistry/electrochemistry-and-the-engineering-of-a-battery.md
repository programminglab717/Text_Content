# Electrochemistry and the Engineering of a Battery

Drop a strip of zinc into a solution of copper sulfate and something visible
happens within a minute. The bright zinc dulls and pits. A dark, spongy deposit
of copper builds on its surface. The blue of the solution fades. What has
occurred is an electron transfer: zinc atoms have given up two electrons each
and dissolved as ions, and copper ions in solution have accepted those electrons
and plated out as metal. Energy is released, and in this arrangement all of it
appears as heat, warming the beaker by a degree or two and accomplishing nothing
else.

A battery is what you get when you refuse to let that happen in one place. Split
the reaction in two, put the halves in separate compartments, and force the
electrons to travel between them through an external wire. They will still go —
the chemistry still wants to happen — but now they must go the long way, and
along that route they can spin a motor or light a filament. The entire
discipline of electrochemistry follows from this one trick of separating a
reaction's two halves and making the electrons commute.

## Half-Reactions and the Pressure Behind Them

Every electron transfer can be written as two half-reactions: an oxidation,
where a species loses electrons, and a reduction, where a species gains them.
Zinc oxidises. Copper ion reduces. Neither half can proceed alone, because
electrons do not accumulate in bulk anywhere, but the two together balance.

Different species have different appetites for electrons, and that appetite can
be measured and tabulated as a standard electrode potential. Fluorine sits at
one extreme, seizing electrons from nearly anything. Lithium sits near the
other, shedding them almost eagerly. The voltage a cell can produce is the
difference between the two half-reaction potentials, and this is why battery
chemistry has always gravitated toward pairing something from the top of the
table against something from the bottom. Lithium's position explains its
dominance in modern cells more than any other single fact: no other practical
material gives up an electron so readily, and none is so light per electron
given.

Voltage, though, is only half of what makes a battery useful. Voltage is a
measure of how hard each electron is pushed — the energy carried per unit of
charge. Capacity is a count of how many electrons are available before the
reactants run out. Energy is the product of the two. A cell can have an
impressive voltage and be useless because it holds a thimble of active material,
or an enormous capacity at a voltage too low to run anything. Designers trade
between them constantly, and the weight of everything that is not active
material — casing, separator, electrolyte, current collectors — sets a hard
ceiling on what any chemistry can deliver in practice.

## What the Electrolyte Is For

Between the two electrodes sits the electrolyte, and its job is the one most
often misunderstood. It must conduct ions and refuse to conduct electrons. If
electrons could cross it directly the cell would short internally, the reaction
would run to completion inside the case, and the energy would come out as heat —
which is exactly the beaker of copper sulfate again, and exactly what happens
when a lithium cell fails catastrophically.

Ions must cross, however, because charge has to balance. When zinc dissolves it
leaves its electrode with a net positive charge in solution; when copper plates
out it leaves the other compartment with an excess of negative sulfate. Within
a few microseconds that charge imbalance would build up enough opposing voltage
to stop the reaction dead. Ion flow through the electrolyte neutralises it
continuously. In the classic demonstration cell this is done with a salt bridge,
a tube of inert electrolyte connecting the two beakers. In a commercial cell it
is done by a separator: a thin porous membrane soaked in electrolyte, keeping
the electrodes physically apart while letting ions through. Separator failure —
a puncture, a dendrite of metal growing through a pore — is the proximate cause
of most battery fires.

## Primary, Secondary, and the Question of Reversibility

A primary cell is used once. The alkaline cell in a torch oxidises zinc powder
against manganese dioxide in a potassium hydroxide paste, and while the chemistry
could in principle be pushed backwards, in practice the electrodes change
physical form as they react. Zinc powder does not reassemble into zinc powder.
Attempting to recharge one produces gas, heat and leakage.

A secondary cell is designed so that the reaction can be reversed by forcing
current backwards, and the design constraint is structural rather than chemical.
The electrodes must return to something close to their original physical
arrangement after each cycle, thousands of times. This is a materials problem of
considerable difficulty and it explains why rechargeable chemistries are so much
rarer than the thermodynamics alone would suggest.

The lead-acid battery solves it by brute force. Lead and lead dioxide plates sit
in sulfuric acid; discharge converts both toward lead sulfate, charge converts
them back. The plates are thick, heavy and mechanically robust, which is why a
car battery weighs what it does and why it survives a decade of shallow cycling.
Its energy density is poor by any modern standard and it remains in production
because it is cheap, tolerant of abuse, and capable of the enormous brief
current a starter motor demands.

Lithium-ion solves it far more cleverly, by avoiding the conversion of one solid
into a different solid altogether. Both electrodes are host structures with
lithium ions living in the gaps between their atomic layers. On discharge,
lithium ions leave the layered graphite anode, swim across the electrolyte, and
slot into vacancies in a layered metal-oxide cathode; electrons make the same
journey through the external circuit. On charge, they go back. The host lattices
barely change — they swell and contract a little, which is why cells age — but
nothing dissolves and nothing plates. This intercalation, the reversible
insertion of a guest ion into a host framework, is the central idea that made
portable electronics possible, and it is a genuinely different concept from the
dissolve-and-replate chemistry that preceded it.

## Running the Reaction Backwards on Purpose

If forcing current through a cell can reverse its chemistry, it can also drive
reactions that would never occur spontaneously, and this is the industrial face
of electrochemistry. Aluminium exists as a commodity metal rather than a
curiosity because of it. Aluminium oxide is so stable that no ordinary chemical
reducing agent will strip the oxygen away at a workable cost; the metal was
briefly more precious than silver for that reason. Dissolving the oxide in
molten cryolite and passing an enormous current through the bath does what
chemistry alone could not, which is why aluminium smelters are built beside
hydroelectric dams and why the metal's price tracks the price of electricity
more closely than the price of ore.

Electroplating works the same way at a gentler scale, depositing a controlled
thickness of chromium, nickel or gold onto a part by making it the cathode in a
bath of the appropriate ions. Chlorine and sodium hydroxide, two of the largest
industrial chemicals by volume, are produced together by electrolysing brine.
And electrochemistry works in reverse as a form of protection: bolt a block of
magnesium or zinc to a steel hull and the more reactive metal corrodes
preferentially, holding the steel at a potential where iron will not oxidise.
The sacrificial anode is a battery deliberately designed to waste itself, and
ship hulls and buried pipelines are covered in them.

## Why Batteries Disappoint in the Cold and Die of Old Age

A cell's rated voltage is a thermodynamic quantity, a statement about
equilibrium. The voltage you actually measure while drawing current is lower,
and the gap is called overpotential. Some of it is simple resistance — the
electrolyte, the current collectors and the contacts all oppose current and
dissipate energy as heat. Some of it is kinetic: the electron transfer at each
electrode surface has an activation barrier, and driving the reaction faster
requires pushing harder. And some of it is transport: at high current, ions near
the electrode surface are consumed faster than diffusion can resupply them, and
the cell starves locally even while the bulk electrolyte is full.

Cold weather worsens all three. Electrolyte viscosity rises, ion mobility falls,
and reaction kinetics slow. A cell that delivers its full capacity at room
temperature may deliver a fraction of it near freezing, and the loss is mostly
apparent rather than real — warm the cell and the capacity returns, because the
active material was there the whole time and simply could not be reached fast
enough.

Permanent ageing is a different matter, and it is a slow accumulation of side
reactions that were never part of the design. Electrolyte decomposes at the
electrode surface, building an insulating film that thickens over years and
consumes lithium in the process. Cathode material dissolves slightly and
redeposits where it is not wanted. Repeated swelling and contraction cracks
particles, exposing fresh surface for more decomposition. None of these is the
intended reaction; all of them are unavoidable consequences of holding reactive
materials in intimate contact at a voltage that is, thermodynamically speaking,
outside the electrolyte's comfortable range. A battery is a controlled instance
of two substances that want very much to react, kept apart by a membrane and a
film measured in nanometres, and the surprising thing is not that they
eventually degrade but that they behave for as long as they do.
