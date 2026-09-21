# How a Nuclear Reactor Is Controlled

A power reactor running at full output is, in one narrow sense, doing nothing at
all. The neutron population inside the core is exactly replacing itself,
generation after generation, neither growing nor shrinking. Every fission
scatters a couple of neutrons into the moderator, most of them get absorbed by
structure or coolant or leak out the side, and on average precisely one survives
to split another nucleus. The whole apparatus — thousands of tonnes of steel,
zirconium, water, and uranium oxide — exists to hold that balance steady enough
that a turbine on the other side of the wall spins at constant speed.

The arithmetic of that balance is the quantity engineers call k, the
multiplication factor. If k is one, the reactor is critical and power is
constant, whether that power is a watt or three gigawatts. If k is slightly
above one, power climbs; slightly below, it decays away. Nothing about the word
"critical" implies danger. A reactor that is not critical is either shutting
down or starting up.

## Why the Reaction Is Slow Enough to Steer

The obvious worry is speed. A neutron born in fission slows down in the
moderator and finds a new nucleus in something like a ten-thousandth of a
second. If every generation took that long and k were even a percent above one,
power would double roughly every millisecond. No mechanical system could
intervene. No human could.

Reactors are controllable because a small fraction of fission neutrons do not
arrive on that schedule. Fission produces fragments that are badly
neutron-rich, and a handful of those — bromine-87 and iodine-137 among them —
shed a neutron some seconds or tens of seconds after they are formed, as part of
their decay. For uranium-235 this delayed fraction is only about two-thirds of
one percent of all neutrons produced. It is a rounding error in the energy
budget and the single most important number in reactor physics.

Because the chain reaction cannot sustain itself on prompt neutrons alone, it
has to wait for the stragglers. The effective generation time stretches from a
ten-thousandth of a second to something closer to a tenth of a second, and the
reactor's response to a small change in reactivity slows by three orders of
magnitude. Pull a control rod a few centimetres and power does not jump; it
drifts upward over a minute or two while the operator watches it. The entire
operating envelope of every commercial reactor sits inside that narrow margin.
Push reactivity past the delayed fraction and the reaction becomes
self-sustaining on prompt neutrons alone — prompt critical — at which point the
delayed neutrons no longer matter and the excursion is over before any
mechanism can respond. Reactivity is measured in units of that fraction for
exactly this reason: one dollar of reactivity is the amount that would make a
core prompt critical, and operators work in cents.

## The Things That Move

A pressurized water reactor has three ways to change reactivity deliberately,
and they work on very different timescales.

Control rods are the fast one. Clusters of tubes filled with boron carbide, or
an alloy of silver, indium, and cadmium, hang above the fuel assemblies on
electromagnetic latches. Boron and cadmium have enormous appetites for thermal
neutrons; sliding those rods into the fuel lattice removes neutrons from
circulation immediately. Cut power to the latches — deliberately, or through
any one of several dozen automatic trip signals — and the rods fall into the
core under gravity in a couple of seconds. Boiling water reactors, which have
steam in the upper core and no room for rods to drop from above, instead drive
their cruciform blades upward from beneath on hydraulic accumulators, which is
mechanically harder but achieves the same end.

The slow one is chemical. A pressurized water reactor dissolves boric acid
directly in the primary coolant and adjusts its concentration over hours by
feeding and bleeding water through the purification system. This "chemical
shim" compensates for the gradual burn-up of fuel across an eighteen-month
cycle: a freshly loaded core holds far more reactive material than it needs, and
rather than parking control rods deep in the fuel and distorting the power shape
for a year, operators drown the excess reactivity in boron and dilute it away as
the uranium is consumed. By the end of a cycle the boron concentration is near
zero and the core is running out of margin, which is what determines when the
plant shuts down for refuelling.

The third mechanism does not move at all. Burnable absorbers — gadolinium mixed
into some fuel pellets, or a thin boride coating on the cladding — hold down
reactivity early in life and are themselves consumed by the neutrons they
capture, so their grip weakens on roughly the same schedule as the fuel depletes.

## The Reactor Controls Itself

Most of the second-to-second regulation, though, is not done by any of these.
It is done by physics, and it is the reason a large reactor can be left to
follow the grid.

Two feedbacks dominate. The first is Doppler broadening. As uranium dioxide
pellets get hotter, the thermal motion of uranium-238 nuclei widens the
resonance energies at which they capture neutrons, and the fuel swallows more
neutrons on their way down from fission energy to thermal. This happens within
the fuel itself, instantly, the moment temperature rises. The second is the
moderator coefficient: hotter water is less dense, moderates less effectively,
and — in a borated core — carries less boron per unit volume, though in a
well-designed light water reactor the density effect wins and the net sign is
negative.

Both feedbacks push back against power increases. The practical consequence is
that the turbine, not the operator, sets the reactor's output. Open the steam
valves and more heat leaves the steam generators, returning colder water to the
core; colder water is denser, moderates better, reactivity rises, and power
climbs until the core temperature is back where it started. Close the valves
and the reverse happens. The reactor chases the load on its own, with the rods
making only fine adjustments to hold average coolant temperature on programme.

This is exactly what the RBMK at Chernobyl lacked. Graphite did the moderating
there, and the water was primarily a coolant and a neutron absorber, so boiling
the water away in the channels *removed* an absorber and raised reactivity. At
low power that positive void coefficient overwhelmed the other feedbacks, and a
reactor that should have been pushing back was instead leaning in. The
control-rod design compounded it: graphite followers on the rod tips briefly
displaced water and added reactivity in the lower core during the first seconds
of insertion, so the emergency shutdown itself provided the final push.

## Xenon, and the Memory of Yesterday

The subtlest thing an operator manages is a poison that the reactor makes for
itself. Fission yields iodine-135, which decays with a half-life of several
hours into xenon-135, which has one of the largest neutron absorption cross
sections of any nuclide known. At steady power, xenon is produced and burned
out by the flux at a balanced rate and simply costs the core a few percent of
reactivity.

Shut the reactor down and the balance breaks. The flux that was destroying
xenon disappears, but the iodine inventory keeps decaying into more of it.
Xenon concentration climbs for something like nine or ten hours before its own
decay takes over. A reactor tripped from full power enters a window during which
it cannot be restarted at all — no amount of rod withdrawal will overcome the
poison — and operators either restart within the first hour or wait the better
part of a day. In large cores the effect can also slosh: a local power increase
burns out xenon locally, raising power further, while the other end of the core
builds poison, producing slow power oscillations between top and bottom that
must be damped by hand or by dedicated grey rods. A reactor remembers what its
power was doing half a day ago, and behaves accordingly.

## After the Rods Drop

Shutting a reactor down does not stop the heat. The fission products
accumulated in the fuel keep decaying, and immediately after a trip that decay
heat amounts to several percent of full thermal power — for a large plant, a
hundred megawatts or more of heat with nowhere to go. It falls off quickly,
roughly an order of magnitude over the first hours, but it never reaches zero
within any timescale that matters to a plant operator.

So the control problem does not end at shutdown; it changes shape. It becomes a
problem of moving heat out of a core that is no longer generating its own
electricity, using pumps that need power, into a heat sink that has to keep
existing. Every serious accident at a water-cooled reactor has been a decay heat
accident rather than a reactivity accident. Three Mile Island lost coolant
through a stuck relief valve while instrumentation told the crew the opposite.
Fukushima Daiichi shut down cleanly on the earthquake, exactly as designed, and
then lost first the grid and then the emergency diesels to the tsunami, leaving
three intact but unattended cores' worth of decay heat and no working pumps. The
chain reaction had already been stopped in each case. What remained was the
residue, and the residue was enough.
