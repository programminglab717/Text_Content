# Transformers and the High-Voltage Grid

Stand near a substation on a still night and you hear it: a low, steady hum,
flat and unmusical, coming from the grey tanks behind the fence. The note is
not the sound of anything spinning, because nothing in there spins. It is the
core itself changing shape. Silicon steel is magnetostrictive — it lengthens
very slightly when magnetised, in either direction — so a core driven by
sixty-hertz alternating current stretches and relaxes a hundred and twenty times
a second, and the laminations press against each other and against the oil and
the tank wall. The grid's most important machine announces itself with a
mechanical side effect of the physics it depends on.

Transformers are why the electrical system has the shape it has. Every argument
about where to put generation, how far it can be from load, and what a national
grid even means comes back to the ability to change voltage cheaply, in both
directions, with no moving parts and efficiency above ninety-nine percent.

## The Argument Voltage Won

The physics is a single equation. Power delivered down a line is voltage times
current, but power *wasted* in the line is current squared times resistance. The
resistance of a given conductor is fixed by its metal and its cross-section.
Current is therefore the enemy, and for a fixed amount of power delivered, the
way to reduce current is to raise voltage. Carry the same megawatts at ten times
the voltage and you lose one percent as much heat.

This was not obvious in the 1880s, and it did not matter for Edison's direct
current systems, which had no practical way to change voltage and were
consequently stuck. A DC station could serve customers within roughly a mile
before the copper needed to hold voltage up became absurd — which is why early
electrification meant a generating station every few blocks, burning coal in the
middle of the city.

The escape had been assembling in Europe. Lucien Gaulard and John Dixon Gibbs
demonstrated open-core induction coils in the early 1880s, wired in series in a
way that made them awkward to use. In Budapest, three engineers at the Ganz
works — Zipernowsky, Bláthy, and Déri — built the version that mattered: a
closed magnetic core with windings around it, devices connected in parallel
across a constant-voltage distribution main so that each load could be switched
independently of the others. In Massachusetts, William Stanley built
transformers for Westinghouse and lit the main street of Great Barrington with
them in 1886, stepping generator voltage up for the run into town and back down
at the shops. Within a decade the question was settled in the most public way
available: the Niagara Falls project chose alternating current, and the power it
sent to Buffalo travelled a distance that no direct-current system of the era
could have contemplated.

## A Machine With No Moving Parts

Inside the tank, two things are being managed at once: the magnetic circuit and
the heat.

The core is built from thin sheets of silicon steel, each coated in insulation
and stacked rather than cast solid. A solid core would work magnetically and
fail thermally, because the changing flux would drive circulating eddy currents
through the iron and cook it. Laminating the core breaks those current loops
into thin slices. Silicon content raises the steel's electrical resistivity
further and reduces hysteresis loss — the energy spent dragging the metal's
magnetic domains around a loop twice per cycle. Modern core steel is
grain-oriented, rolled so its crystal structure aligns with the direction the
flux will travel, and the corners of a core are mitred so that flux never has to
turn across the grain more than it must.

Windings are copper, wound in concentric cylinders around each core limb, the
high-voltage winding outside the low-voltage one so that the largest insulation
distance is to the tank rather than between the coils. The insulation itself is
kraft paper and oil. Mineral oil does double duty here: it is a better
dielectric than air, and it carries heat from the windings out to the radiators
by convection, sometimes helped by pumps and fans on the largest units. A
conservator tank on top gives the oil room to expand, and a gas relay in the
pipe between them will trip the transformer if bubbles start collecting — which
they do when something inside is arcing.

The one component that does move is the tap changer. Grid voltage drifts with
load, and transformers correct it by switching the number of active turns in a
winding, a percent or two at a time. Doing that while energised without ever
interrupting current is a genuinely hard mechanical problem, solved with spring-
loaded diverter switches that transfer the load between taps in a few tens of
milliseconds. On-load tap changers are, unsurprisingly, the part of a
transformer most likely to need maintenance.

## Out on the Line

The conductors leaving the substation are almost never copper. Overhead line is
aluminium — lighter, cheaper, and adequate once you accept a larger diameter —
usually stranded around a steel core that carries the mechanical tension while
the aluminium carries the current. At high voltages each phase is split into two,
three, or four conductors held apart by spacers, which looks like a way to add
capacity but is really a way to fatten the effective surface. Electric field
strength at a conductor's surface rises as the conductor gets thinner, and past a
threshold the air around it begins to ionise. That is corona: it wastes power,
generates radio noise, makes ozone, and produces the crackle you hear under a
line in damp weather. Bundling spreads the field and keeps the surface gradient
below the onset.

What ultimately limits a line is not voltage but temperature. Current heats the
aluminium, heat makes it expand, expansion makes the span sag lower between
towers. A line's rating is the current at which it sags to its minimum legal
clearance — which is why ratings are higher in winter and on windy days, and why
grid operators have started measuring conductor temperature directly instead of
assuming a worst case. The cascade that blacked out the American Northeast in
2003 began with exactly this: heavily loaded lines in Ohio sagging into trees
that had not been trimmed, tripping one after another, each trip shifting load
onto the remaining lines and pushing them down into the canopy too.

Long lines have a subtler problem. The conductors form a capacitor with the
ground and with each other, and at transmission voltages that capacitance draws
a substantial charging current even with nothing connected at the far end. On a
lightly loaded long line the effect actually raises the voltage at the receiving
end above the sending end. Utilities counter it with shunt reactors — large
inductors whose only job is to absorb reactive power — and the management of
reactive flow, invisible in any energy statistic, is half of what a control room
does.

## The Case for Direct Current, Again

Underground and submarine cables make the capacitance problem fatal rather than
annoying. A cable's conductor sits centimetres from a grounded sheath instead of
metres from the ground, so its capacitance per kilometre is far larger, and past
fifty or eighty kilometres an AC cable spends essentially all its capacity
charging and discharging itself. There is no length of AC cable that will cross
an ocean.

Direct current has no charging current, because nothing alternates. It also
needs only two conductors instead of three, suffers no skin effect, and imposes
no requirement that the systems at either end run in step — which is how Japan
links its fifty-hertz north to its sixty-hertz south, and how asynchronous grids
anywhere tie together. The historical obstacle was conversion. Turning hundreds
of megawatts of AC into DC and back was impractical until mercury-arc valves,
then thyristors, then insulated-gate transistors made it a matter of
semiconductor stacks in a valve hall.

The economics are a crossover. HVDC terminals cost much more than substations;
HVDC line costs less per kilometre and loses less. Somewhere past several
hundred kilometres overhead, or a few dozen underwater, the lines win. China
built its grid around that crossover, running ultra-high-voltage DC links two
thousand kilometres from western hydro and coal to the coastal cities, and
Europe is stitching offshore wind into the mainland the same way.

What has not changed is the underlying bargain. Every one of these systems still
ends at a transformer — a stack of steel sheets and a few tonnes of copper in
oil, doing the one trick that made a continental grid thinkable. They are also
the grid's quiet vulnerability. A large power transformer is custom-built to the
substation it serves, takes a year or more to order, weighs enough to require a
specialised rail car, and there is no warehouse of spares. Geomagnetic storms
drive slow currents through grounded neutrals and push cores into saturation;
through-faults hammer windings with forces that loosen clamping over decades.
Utilities sample the oil and run it through a gas chromatograph, reading
dissolved hydrogen, methane, and especially acetylene the way a doctor reads
blood work, because acetylene in the oil means something inside is arcing and the
tank cannot be opened to look.
