# What Grid-Scale Batteries Actually Do

The site looks like nothing. Forty or four hundred white steel containers in
rows on a gravel pad, chain-link fence, a switchyard at one end, no moving parts
visible from the road except the fans. Most of the time the containers sit
there absorbing a trickle of power to run their own air conditioning. Then a
coal unit three hundred kilometres away trips offline, the grid frequency starts
to sag, and within a fraction of a second — long before any human has read a
screen — the whole pad is pushing a hundred megawatts into the network. Twenty
minutes later it stops, having done the only thing anyone needed from it that
day.

The public conversation about grid batteries is mostly a conversation about
hours: how long could this thing run the city if the wind stopped? That is
almost never the question the battery was built to answer. Understanding what
these installations are for means separating three quite different jobs that
happen to use the same hardware.

## Seconds, Minutes, Hours

An alternating-current grid is a machine that has to balance instantaneously.
There is no reservoir of electricity anywhere in the wires; generation equals
consumption at every moment, and the evidence of any mismatch is frequency. When
load exceeds generation, the spinning masses of every turbine and motor
connected to the system give up a little rotational energy to make up the
difference, and they all slow down together. Fifty hertz becomes 49.8. Push it
far enough and protective relays start disconnecting things, which makes the
imbalance worse, which is how a regional grid can unravel in under a minute.

That first stage of resistance — the slowing of the spinning mass itself — is
inertia, and it is free but finite. It buys the system a few seconds. Into
those seconds, traditionally, step governors on partially loaded thermal plants,
opening steam valves to add output. Governor response is measured in tens of
seconds because it involves physically admitting more steam into a turbine that
weighs as much as a locomotive.

A battery's power electronics respond in milliseconds. It does not need to warm
anything, spin anything up, or wait for a pressure to build. This is why the
earliest commercially successful grid batteries were not built to store energy
in any meaningful quantity but to sell frequency regulation — the continuous
small corrections that keep frequency on target minute by minute. A battery
following a regulation signal spends the day drifting between forty and sixty
percent charge, never doing anything you could call storage. It was an
extraordinarily profitable trade for whoever got there first, and the market
saturated fast, because the total quantity of regulation any grid needs is small
and a few hundred megawatts of batteries can supply it all.

The second job is capacity: being available at the hour of highest demand so
that some gas turbine doesn't have to exist. The third is arbitrage — buying
cheap energy and selling expensive energy — which in a system with a lot of
solar means charging at midday, when prices in California or South Australia
regularly go negative, and discharging into the steep evening ramp after sunset.
Those three jobs stack on the same asset, and the revenue that justifies the
capital usually comes from all of them at once.

## Inside the Container

Open one and the interior is unglamorous: vertical racks of modules, each module
a brick of cells, wired in series to a few hundred or a thousand volts and in
parallel for capacity, with a cooling loop threading through and a fire
suppression head overhead.

Almost all of it is now lithium iron phosphate. The stationary market moved away
from the nickel-manganese-cobalt chemistry that dominates cars, and the reasons
are not the ones people expect. LFP is heavier per kilowatt-hour, which is fatal
in a vehicle and irrelevant on a gravel pad. It tolerates being held at full
charge, cycles more times before it wears out, and — most importantly — its
thermal runaway threshold is considerably higher and its failure less energetic.
When density stops mattering, the whole optimisation flips.

Each rack reports to a battery management system that watches individual cell
voltages and temperatures, because a pack is only as good as its worst cell and
an undetected weak cell is how fires start. Above the racks sits the piece that
actually makes the installation a grid asset: the power conversion system, a
bank of inverters turning several hundred volts DC into three-phase AC, and a
transformer stepping that up to distribution or transmission voltage. Round
trip, from grid in to grid out, something like eighty-five percent of the energy
survives. The rest goes to heat in the cells, losses in the inverters, and the
parasitic load of keeping the whole building at a temperature the chemistry
likes — which in a desert summer is a real number.

## Why Four Hours

Nearly every merchant battery built in the last several years stores about four
hours of energy at its rated power. That is not a technical constant. It is an
economic and regulatory one.

Power and energy are priced separately. The inverters, transformer, switchgear,
interconnection, land, and permitting scale with megawatts; the cells scale with
megawatt-hours. Adding a fifth and sixth hour means adding cells to a site whose
expensive interconnection is already paid for, and those extra hours earn less
than the first four, because the daily price spread that arbitrage feeds on is
narrow and sharp. Evening peaks are short. A battery that can cover the four
worst hours captures most of the value available; one that can cover twelve
captures a little more for three times the cell cost.

Regulators pushed the same direction. California's resource adequacy rules, by
crediting four-hour storage at essentially full capacity value, effectively told
every developer in the state what to build. The duration will drift upward as
solar saturation flattens the midday price floor and lengthens the evening ramp,
and some markets already reward six and eight hours. But nobody is building a
lithium battery to ride out a still, cloudy week. That is a different problem,
with a different cost structure, and lithium loses it badly — the seasonal job
belongs to hydro reservoirs, hydrogen, thermal storage, or generation that
doesn't depend on weather at all.

## Wearing Out on Purpose

A battery is a consumable dressed as infrastructure. Capacity fades two ways at
once. Calendar ageing happens simply because time passes, accelerated by heat
and by sitting at high state of charge — which is why a well-run site parks at
partial charge when it has nothing to do and why the cooling bill is never
optional. Cycle ageing accumulates with throughput: every full charge and
discharge grows the solid electrolyte layer on the anode a little thicker and
strands a little more lithium.

The practical consequence is that operating a battery hard is a decision to
spend the asset. Owners model degradation as a cost per megawatt-hour cycled and
compare it against the price spread on offer that day. On an ordinary Tuesday
the spread does not cover the wear, and the sensible move is to sit still. It
takes a genuinely scarce evening to be worth the damage.

Because fade is predictable, the industry designs around it: the site is
oversized at commissioning so it still meets its contracted capacity years
later, and augmentation — adding fresh racks into empty positions mid-life — is
planned from the start. The warranty is the real product being sold, and it
usually guarantees a retained capacity percentage after a specified number of
cycles under specified conditions, which is why operators guard their
temperature and depth-of-discharge records carefully.

Fire is the other liability, and the failure mode is specific: a single cell
goes into thermal runaway, vents flammable electrolyte vapour, and heats its
neighbours until they do the same. The engineering response has been less about
extinguishing — water does little once a pack is self-heating — than about
containment and geometry. Modern sites use outdoor enclosures no one walks into, with
deflagration panels, fixed spacing between units, and detection that watches for
off-gassing before there is any flame. The large California installation that
burned repeatedly was a retrofit into an old turbine hall, thousands of racks
sharing one enormous volume, which is close to the opposite of current practice.

## The Quieter Shift

Most inverters on the grid today are grid-following. They watch the voltage
waveform around them, lock onto its phase, and inject current in step. That
works beautifully as long as something else is establishing the waveform — which
has always been true, because synchronous generators do it by construction. A
grid made mostly of followers has no one to follow.

Grid-forming inverters behave instead like voltage sources: they set a frequency
and phase of their own and let power flow according to the angle difference,
which is exactly how a synchronous machine behaves, implemented in software. A
grid-forming battery can hold up a network section on its own, ride through a
fault, provide a synthetic inertial response in the first cycles after a
disturbance, and in some installations black-start a dead system — energising a
line so that a gas turbine has something to synchronise to.

That capability is what makes batteries structural rather than supplementary.
The storage is almost incidental. What the grid is buying is a machine that can
impose a waveform on a network at the instant the machines that used to do it
are no longer there.
