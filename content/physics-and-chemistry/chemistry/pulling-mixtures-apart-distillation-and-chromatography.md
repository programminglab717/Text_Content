# Pulling Mixtures Apart: Distillation and Chromatography

Almost nothing in nature arrives pure. Crude oil is a soup of thousands of
hydrocarbons. A plant extract holds the compound you want alongside sugars,
pigments, waxes and several hundred relatives that differ from your target by a
single hydroxyl group. Blood plasma carries proteins spanning four orders of
magnitude in abundance. The work of separating one substance from the rest is
so fundamental that entire industries are essentially separation businesses
wearing other clothes, and the two dominant techniques — distillation and
chromatography — rest on the same underlying idea approached from opposite
directions.

The idea is this: if two substances distribute themselves unequally between two
phases, and you can repeat that unequal distribution enough times, even a very
small preference compounds into a complete separation. One pass might enrich
your mixture from fifty-fifty to fifty-five–forty-five. A hundred passes turns
that into essentially pure product. Both techniques are machines for performing
a modest separation many times in a row without a human intervening between
each step.

## Boiling the Easy Ones Off First

Distillation exploits the difference between a liquid and the vapour sitting
above it. When a mixture of two liquids boils, the vapour is not the same
composition as the liquid. It is enriched in whichever component is more
volatile — the one with the lower boiling point, roughly speaking, though the
strength of interactions between unlike molecules complicates this. Condense
that vapour and you have a liquid richer in the volatile component than what
you started with.

A simple distillation does this once. Heat a flask, collect what comes over,
and you have partially separated your mixture. If the boiling points differ by a
hundred degrees, once is enough — separating water from dissolved salt, for
instance, is trivial, because the salt has no meaningful vapour pressure at all.
If they differ by ten degrees, one pass leaves you with two mediocre fractions
and a headache.

The fractionating column is the answer, and it is an elegant one. Between the
boiling flask and the condenser, insert a tall vertical tube packed with glass
beads, or metal mesh, or a stack of perforated trays. Vapour rising through the
column meets liquid trickling back down. At every point along its height, vapour
condenses onto the packing and liquid re-evaporates from it, and each of those
exchanges is another partial separation. The vapour that reaches the top has
effectively been distilled and redistilled dozens of times. Engineers count
these as theoretical plates — the number of idealised single distillations a
given column is equivalent to — and a column's separating power is essentially
its plate count. A laboratory column might offer twenty. A petroleum refinery's
crude tower, forty metres of steel with trays every half metre, offers enough
to draw off butane at the top, then naphtha, then kerosene, then diesel, then
heavy gas oil, each at its own height where the temperature happens to match
its condensation point.

The technique has limits that are worth knowing because they are absolute rather
than practical. Some pairs of liquids form azeotropes, mixtures at which vapour
and liquid have identical composition. At that point no further separation is
possible by distillation at all, no matter how tall the column, because the
whole mechanism has nothing to work with. Ethanol and water form one at roughly
ninety-five percent ethanol, which is why rectified spirit tops out where it
does and why producing anhydrous ethanol requires some other trick entirely —
adding a third component that breaks the azeotrope, or passing the vapour over a
molecular sieve that adsorbs water preferentially.

Other variations extend the range. Vacuum distillation lowers the pressure so
that liquids boil at lower temperatures, which matters enormously for compounds
that would decompose before reaching their atmospheric boiling point; refineries
use it on the residue from the main tower to pull out lubricating oils that
would crack under direct heat. Steam distillation carries volatile organics over
at temperatures below their own boiling points by mixing them with water vapour,
a gentle enough method that it remains the standard way to extract essential
oils from plant material.

## Letting Molecules Race Down a Tube

Chromatography attacks the same problem with a different pair of phases. Instead
of liquid and vapour, it uses a stationary phase — a solid, or a liquid coated
onto a solid — and a mobile phase that flows past it. The sample is introduced
at one end and pushed along. Molecules that interact strongly with the
stationary phase spend more of their time stuck to it and less of it moving, so
they travel slowly. Molecules that prefer the mobile phase travel quickly. Given
enough length, components that started as a single spot emerge as separate
bands.

The simplest version needs almost nothing. Put a drop of black ink near the
bottom of a strip of filter paper, stand the strip in a shallow dish of water,
and watch the water climb by capillary action. The dyes separate into coloured
arcs at different heights, because each one partitions differently between the
water and the cellulose fibres. Every more sophisticated form of chromatography
is a variation on this, with better control over the phases and a detector at
the far end.

Column chromatography packs the stationary phase — usually silica gel, a polar
powder — into a vertical tube. Solvent is poured in at the top and percolates
down. Polar compounds cling to the silica and lag; nonpolar ones wash through.
By collecting the effluent in a series of small tubes and checking each one, a
chemist recovers the components in order of polarity. This is the workhorse
purification of synthetic organic chemistry, and a graduate student's
relationship with it is generally not affectionate.

Gas chromatography puts the mobile phase in the vapour state. A sample is
injected into a heated port, flashes to vapour, and is swept by an inert carrier
gas through a capillary tube whose inner wall carries a thin film of stationary
liquid. The tubes are long — tens of metres, wound into a coil inside an oven —
and narrow, which is what allows such high plate counts in a device you can put
on a bench. Separation here depends on volatility as well as on affinity for the
coating, which means gas chromatography combines something of distillation's
mechanism with chromatography's geometry. It is superb for anything that can be
vaporised without decomposing: fuels, flavours, solvent residues, blood alcohol.

High-performance liquid chromatography handles what gas chromatography cannot —
large, polar, thermally fragile molecules, which is to say most of biochemistry.
The stationary phase is packed as very fine particles, so fine that solvent must
be forced through at high pressure. Small particles mean short diffusion
distances, which means sharp bands rather than smeared ones, which means better
resolution. Reversed-phase HPLC, where the stationary phase is nonpolar and the
mobile phase is water mixed with an organic solvent, has become the default
method for analysing pharmaceuticals and peptides.

## Why Bands Spread

A separation is only as good as the sharpness of what emerges, and every
chromatographic band is fighting a slow tendency to smear. Three mechanisms do
the smearing. Molecules take different paths between the packed particles, some
longer than others, so identical molecules arrive at slightly different times.
Molecules diffuse along the direction of flow simply because they are warm.
And the exchange between mobile and stationary phase takes finite time, so a
molecule that happens to be adsorbed when its neighbours are moving falls
behind.

These three work against each other as flow rate changes, which produces a
characteristic result: there is an optimum flow, neither fastest nor slowest,
at which bands are narrowest. Run too slowly and longitudinal diffusion has
time to blur everything. Run too quickly and the phases never reach
equilibrium. Practitioners find this optimum empirically and then generally run
slightly faster than it, trading a little resolution for getting home earlier.
Smaller stationary-phase particles shift the optimum toward higher flow rates
and flatten the penalty for exceeding it, which is the entire justification for
the high pressures in modern liquid chromatography.

Detection is a separate craft. Something at the column outlet has to notice that
the effluent composition has changed. Ultraviolet absorbance is the common
choice for liquid work, since most molecules of interest absorb somewhere;
refractive index detectors catch what UV misses but are fussy about
temperature. Gas chromatography favours the flame ionisation detector, which
burns the effluent and measures the ions produced, responding to essentially
any organic compound in proportion to its carbon content. Coupling either
technique to a mass spectrometer, so that each emerging band is immediately
weighed and fragmented, turns a separation into an identification, and that
pairing underlies most of modern analytical chemistry.

## Choosing Between Them

The practical difference is throughput against resolution. Distillation is
continuous and enormous. A refinery tower separates hundreds of thousands of
barrels a day, forever, with no consumables beyond the heat. Chromatography is
generally a batch process, run on milligrams or grams, consuming solvent and
stationary phase, and it is used in bulk only where the product is valuable
enough to justify the cost — certain pharmaceuticals, high-purity sugars.

But chromatography resolves what distillation cannot. Two molecules with the
same boiling point are invisible to a distillation column. If they differ in
shape or polarity, a chromatographic column sees them clearly. Mirror-image
molecules, identical in every bulk physical property, can be separated on a
stationary phase that is itself chiral and therefore interacts differently with
each hand. That capability has no equivalent in distillation and it matters
enormously in drug manufacture, where one enantiomer may be therapeutic and its
mirror image inert or worse.

In practice the two are often used in sequence: distil to get from tonnes to
kilograms and from a hundred components to five, then chromatograph to get from
five to one. The engineering question is never which technique is better but
where along the purification the changeover should happen, and that turns out to
depend as much on the price of solvent and the value of the product as on any
property of the molecules involved.
