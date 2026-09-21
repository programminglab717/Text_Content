# Photolithography and How Chips Are Printed

Tilt a bare silicon wafer under a lamp and it throws back a rainbow, like an oil
slick on wet asphalt. The color is not paint. It comes from interference in films
a few hundred atoms thick, deposited and then selectively cut away dozens of times
during manufacture. Every one of those layers got its pattern the same way: light
was shone through a stencil onto a light-sensitive coating, the coating was
developed like a photograph, and whatever survived became the mask for the next
physical step. A processor is a printed object in the most literal sense the word
allows. It is printed something like fifty to eighty times over, each impression
aligned to the ones beneath it to within a few nanometers.

This is photolithography. It is the most expensive step in semiconductor
manufacturing, the slowest, and the one that sets the limit everyone else designs
around. When people say a chip is made on a "five-nanometer process," they are
mostly making a claim about what the lithography can resolve — or, lately, about
what the lithography can be tricked into resolving.

## One Turn of the Cycle

Start with a wafer that already carries a blanket film of something useful: silicon
dioxide, silicon nitride, polysilicon, a metal. The film covers everything, and the
job is to remove it everywhere except where the circuit wants it.

The wafer is spun at a few thousand revolutions per minute while a viscous polymer
is dripped onto its center. Centrifugal force flings it outward into a film under a
micron thick and remarkably uniform. A brief bake drives off the solvent. This is
the photoresist, and it is the actual recording medium — the chip's negative.

The wafer then goes into the exposure tool, where light passes through a photomask:
a flat plate of ultra-pure fused quartz carrying the pattern in an opaque chrome
film. Where light reaches the resist, it changes the polymer's chemistry. In a
positive resist, exposure breaks bonds and makes the polymer soluble in an alkaline
developer, so the illuminated regions wash away. A negative resist does the reverse.
Either way, after a post-exposure bake and a developer rinse, the wafer is covered
in a three-dimensional polymer stencil that reproduces the mask pattern in relief.

What follows is not photography at all. The wafer is fed into a plasma etcher, where
energetic ions strike its surface nearly vertically and chew through the exposed
film while the resist protects everything underneath. Or it goes into an implanter,
where dopant ions are fired into the bare silicon and stopped by the resist
elsewhere. Then the remaining resist is stripped off in oxygen plasma or hot
solvent, the wafer is cleaned, a new film is deposited, and the whole cycle begins
again with a different mask. Layer by layer, transistors appear in the silicon and a
multi-story lattice of copper wiring is built above them.

Modern deep-ultraviolet resists add a step of chemical leverage. A photoacid
generator embedded in the polymer releases a strong acid when it absorbs a photon,
and the post-exposure bake lets each acid molecule catalyze many deprotection
reactions before it is quenched. One photon therefore does the work of dozens. This
chemical amplification is what made short-wavelength lithography practical, because
the light sources involved are dim and exposures have to be fast.

## Everything Hinges on Diffraction

Early lithography pressed the mask directly against the wafer. It worked, and it
destroyed masks — every contact ground particles into the chrome, and a mask defect
prints on every die it touches for the rest of its life. The industry moved to
projection: a lens sits between mask and wafer, and it demagnifies, typically by a
factor of four. The pattern written on the mask is four times larger than what lands
on silicon, which means mask-writing tolerances are four times looser and mask
defects shrink to a quarter of their size.

Introducing a lens also introduces the fundamental constraint. Light passing through
fine apertures diffracts, and a lens can only collect the diffracted orders that fall
within its aperture. The rule of thumb, borrowed from microscopy, is that the
smallest resolvable feature scales as the wavelength divided by the numerical
aperture, with a process-dependent factor out front that engineers call k1. Depth of
focus, meanwhile, scales as the wavelength divided by the *square* of the numerical
aperture. That squared term is the whole tragedy of the field: every step toward a
sharper image costs you focus budget, and wafers are not perfectly flat, resist has
thickness, and the stage is moving.

So the industry attacked the wavelength. Mercury arc lamps supplied the g-line at
436 nanometers, then the i-line at 365. Excimer lasers took over with krypton
fluoride at 248 nanometers, then argon fluoride at 193. A push to fluorine lasers at
157 nanometers was attempted and abandoned; the lens materials that far into the
ultraviolet were too absorbing and too difficult to grow.

Argon fluoride at 193 nanometers then refused to die. Engineers flooded the gap
between the final lens element and the wafer with ultrapure water, whose refractive
index near that wavelength is about 1.44. Immersion does not change the light's
frequency, but it shortens the wavelength inside the medium and allows numerical
apertures above 1.0, which is impossible in air. The effective wavelength drops to
roughly 134 nanometers. The cost is a set of problems no optical engineer wanted:
bubbles, water-borne defects, drying marks, and thermal gradients from evaporation,
all in a gap a fraction of a millimeter wide with a wafer moving underneath it at
high speed.

## Printing Smaller Than You Can Resolve

With the wavelength pinned and the numerical aperture maxed out, the remaining lever
is k1, and pushing it toward its theoretical single-exposure floor near 0.25 has
occupied a generation of engineers.

Some of the tricks are illumination tricks. Rather than lighting the mask uniformly
from straight on, the source is shaped into rings, dipoles, or quadrupoles, tuned so
that the diffracted orders from the specific pattern being printed land inside the
lens pupil. Some are mask tricks. Phase-shift masks etch the quartz beneath alternate
openings to a depth that flips the light's phase by half a wave, so the fields from
neighboring apertures interfere destructively in between and carve a dark line
sharper than the optics could otherwise produce.

The most visible consequence is that a modern photomask no longer resembles the
circuit. Corners are decorated with serifs, line ends with hammerheads, and isolated
features are flanked by sub-resolution assist bars — structures too small to print
themselves, placed purely to bend the diffraction pattern around the feature that
matters. Computing those corrections for a whole chip is a simulation problem of
serious scale, and it is run again and again as the source shape and the mask are
optimized jointly.

When even that is not enough, the pattern is split across more than one exposure.
The blunt method prints half the features, etches, and prints the rest offset between
them, which doubles cost and makes overlay error a direct contributor to the final
dimensions. The more elegant method, self-aligned double patterning, prints lines at
a comfortable pitch, deposits a conformal film over them, etches it back so only the
sidewalls remain, then removes the original lines. What is left is twice as many
lines at half the pitch — and their spacing is set by a deposited film thickness,
which can be controlled far better than an optical image. Run the trick twice and you
get quadruple patterning.

## Thirteen and a Half Nanometers

Extreme ultraviolet light at 13.5 nanometers is not light you can handle in the
ordinary sense. It is absorbed by air, by glass, by quartz, by almost everything, so
the entire optical path runs in vacuum and nothing can be transmissive. The lenses
are mirrors — molybdenum and silicon multilayer stacks, dozens of alternating pairs
engineered as Bragg reflectors, and even then each bounce returns only around
seventy percent of what hits it. String enough mirrors together to make a projection
system and most of your photons are gone before the wafer sees them. The mask is
reflective too, with the pattern written in an absorbing layer on top of a multilayer
stack.

The source is stranger still. Molten tin is squirted out as a stream of droplets tens
of thousands of times a second. A carbon-dioxide laser pulse flattens each droplet,
a second pulse vaporizes it into a plasma hot enough to radiate at 13.5 nanometers,
and a collector mirror gathers what it can before the tin debris coats everything.
Keeping that source running at the power and uptime a production fab demands took
many years longer than anyone expected.

EUV also brought back a problem that had been dormant since the earliest days:
randomness. A photon at 13.5 nanometers carries far more energy than one at 193, so a
given exposure dose delivers far fewer photons. Photon arrivals are Poisson-
distributed, resist molecules sit where they happen to sit, and at these dimensions
the statistics show up in the print as ragged line edges, occasional bridges between
lines that should be separate, and occasional missing contacts. Raising the dose
smooths the noise and slows the machine, and throughput is what the economics run on.

None of this is exotic physics. It is photography, with a lens, a stencil, and a
sensitized film. What makes it the hardest manufacturing process ever
industrialized is that the picture has to come out right on a few hundred wafers an
hour, every hour, with the previous picture already underneath it and the next one
still to come.
