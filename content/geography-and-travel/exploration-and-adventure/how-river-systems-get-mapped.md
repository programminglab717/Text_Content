# How River Systems Get Mapped

Stand at the top of a pasture where two shallow gullies join and you are
looking at a decision someone had to make. One gully carries water most of the
year; the other runs only after storms. On the topographic map, one of them is
drawn as a solid blue line and the other is not drawn at all. That choice,
repeated a few hundred thousand times, is what a map of a river system actually
is: not a photograph of water, but a long accumulation of judgments about what
counts as a stream, where it starts, and which branch gets the parent river's
name.

Mapping a drainage is harder than mapping a coastline or a road network,
because the object refuses to hold still. Channels migrate, headwaters dry up in
August and reappear in March, and the whole system is three-dimensional in a way
that surface maps hide, with water moving through gravel and limestone as well
as along the open bed. The techniques used to pin it down have changed
completely in two centuries, but the underlying problems have not.

## The Divide Comes First

A river system is defined by its basin, not by its channel. Before you can say
anything useful about where the water goes, you have to find the rim of the
bowl it falls into — the drainage divide, the line along which a raindrop's fate
is decided. Early surveyors traced divides on foot, walking ridgelines with a
compass and a barometer, noting where the ground tipped one way rather than the
other. In broken mountain country this is straightforward enough to see and
exhausting to do. On the flat interiors of continents it is almost invisible:
the divide between two enormous basins can run through a wet meadow where the
gradient in either direction is less than the slope of a table.

Divides also cheat. In karst terrain, water sinks into limestone on one side of
a topographic ridge and emerges as a spring in the next valley over, so the
surface divide and the true hydrologic divide are different lines. Dye-tracing
experiments — pouring a fluorescent dye into a sinkhole and watching which
springs turn green — have repeatedly shown basins borrowing water from their
neighbors. Glacial deposits do something similar, burying an older valley under
till so that modern drainage runs across the grain of the landscape it sits on.
And divides move. A stream eroding headward at a faster rate than its neighbor
will eventually cut back through the ridge and capture the other's headwaters, a
process visible in the field as an abandoned valley too large for the trickle
now occupying it, with a sharp elbow where the flow used to turn.

## Chasing the Source

The public argument about rivers is almost always about length, and length
depends entirely on a convention for choosing the source. The usual rule is the
farthest point of continuous flow measured back up the longest chain of
tributaries, which sounds decisive and is not. It requires deciding whether a
glacier counts, whether a seasonal spring counts, and what to do when the
longest headwater is not the one carrying the most water.

By that rule the Mississippi's source is not in Minnesota at all; the Missouri
is far longer, and the combined system is measured from the Rockies. But
Mississippi is the name that stuck to the lower river, and Lake Itasca — given
its name in the 1830s from a clipped Latin phrase meaning true head — remains
the ceremonial source, a place where you can wade across the river in a few
steps. The Nile and the Amazon have been traded back and forth for the title of
longest river for decades, with each new claim resting on a different headwater
choice in the Andes or a different decision about where the Amazon ends among
the tidal channels of its delta. These are not really discoveries. They are
arguments about definitions, dressed as expeditions.

## From Plane Table to Pixel

Surveying a river by traveling it is a miserable way to get good geometry. A
party moving downstream can record compass bearings and estimate distances by
time and speed, but errors accumulate with every bend, and rivers are nothing but
bends. The classic correction was astronomical: fix latitude by the sun or a
star, fix longitude by lunar distances or, later, by chronometer, and then
stretch the accumulated traverse to fit the fixed points. The interior maps
produced by nineteenth-century exploring parties are often remarkably good in
their overall placement and quite wrong in the shape of individual reaches.

Systematic national mapping worked the other way around, from the outside in.
Triangulation networks established precise positions on hilltops across a whole
country; plane-table surveyors then stood at those known points and sketched the
valleys below them by sighting along an alidade. A river appeared on the map as
a consequence of the terrain around it, drawn by someone looking down at it from
a ridge rather than paddling along it. Aerial photography in the middle of the
twentieth century industrialized this. Overlapping photographs viewed in stereo
give elevation directly, and photogrammetrists traced contours and blue lines
off the stereo model by the thousand-square-kilometer.

The current method dispenses with drawing altogether. Given a digital elevation
model — a grid of ground heights, of the kind produced globally by a radar
mission flown on the Space Shuttle in 2000 — a computer fills the spurious pits,
routes water from each cell into its steepest downhill neighbor, and counts how
many cells drain through every point. Set a threshold on that count and the
channel network falls out automatically, complete with basin boundaries and
tributary hierarchy. Nearly every river map made in the last thirty years is
some version of this computation rather than a record of anyone visiting the
stream.

It fails in the places that matter most. On a delta or a braided plain the
gradient is too gentle and too ambiguous for steepest-descent routing, and the
algorithm invents channels that are not there while missing the ones that are.
Under forest canopy, radar and photogrammetric elevation models sit somewhere in
the treetops, so small valleys vanish. Airborne lidar has fixed much of this by
firing pulses dense enough that some reach the ground between leaves; stripped
of vegetation, the bare-earth model shows headwater swales, abandoned meander
scars, old mill races, and the faint ridges of a floodplain's former channels
with a clarity no field survey could match.

## Ordering the Branches

Once you have a network, you can describe its structure. The standard scheme
assigns order one to every branch with no tributaries; where two first-order
streams meet, the result is second order; two second-order streams make a third,
and so on, with a junction between unequal orders leaving the larger one
unchanged. It is a crude rule that captures something real: within a given
basin, the number of streams of each order falls off in a roughly constant ratio
as order rises, their average lengths rise in a similar ratio, and the drainage
looks statistically like itself at many scales.

The catch is that stream order is a property of the map, not of the river. Map
a watershed at one scale and its trunk is fourth order; map the same watershed
from lidar, where every hillside crease resolves into a channel, and the trunk
becomes sixth or seventh. Drainage density — total channel length per unit area
— behaves the same way, which makes comparisons between basins meaningful only
when the mapping rules were identical. A great deal of published hydrology
quietly rests on the threshold someone chose for the flow-accumulation count.

## What the Map Leaves Out

A blue line says nothing about how much water is in it. Discharge is measured at
gauging stations, and the measurement is indirect: what a gauge records
continuously is stage, the water's height against a datum, which is converted to
flow by a rating curve built from periodic hand measurements across the channel
with a current meter or an acoustic profiler. Rating curves drift as the bed
scours and fills, and they are least reliable at exactly the extremes anyone
cares about, since nobody is wading a river in flood to calibrate the top of the
curve. Satellite altimetry now supplements this by measuring water-surface
elevation from orbit across lakes and wide rivers, extending records into basins
with no instruments and no political appetite for sharing the ones they have.

The map also leaves out time. A channel drawn accurately in one decade can be
several hundred meters away in the next as meanders migrate, cutting the outside
of each bend and depositing on the inside. Occasionally a river abandons its
course entirely, breaking through a low spot on its levee and taking up a new
path across the floodplain — an avulsion, sometimes shifting a major river by
tens of kilometers in a season and redrawing a national boundary along with it.
The lower Mississippi has been leaning toward one of these for the better part
of a century, restrained by a control structure built specifically to keep the
river where the maps and the ports say it should be.

Which is a reasonable way to think about a drainage map generally. It is a
claim about where water was going, at a particular season, resolved at a
particular scale, according to somebody's rule about what a stream is.
