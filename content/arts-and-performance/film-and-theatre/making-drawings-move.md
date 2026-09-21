# Making Drawings Move

An animator at a desk holds five sheets of paper fanned between the fingers of
one hand, hooked over the pegs at the bottom of the drawing board, and rolls
them back and forth with a thumb. The paper is thin enough and the light box
beneath bright enough that two or three drawings show through at once. This is
the flip, and it is the oldest diagnostic in the trade: before anything is shot,
before a single frame is exposed, the animator can already see whether the
gesture reads. If it does not flip well, it will not play well, and no amount of
rendering will save it.

Everything downstream of that desk — the celluloid, the rostrum camera, the
render farm — exists to deliver what the flip already demonstrated. The craft is
about the intervals between pictures, and the machinery is incidental.

## Why Still Pictures Move

The stock explanation, persistence of vision, is not quite right. A retinal
afterimage explains why a rapid succession of frames does not appear to flicker,
but it does not explain why a series of discrete drawings reads as continuous
motion rather than as a fast slideshow. That comes from the visual system's
willingness to construct movement between two similar shapes shown in quick
succession in nearby positions — apparent motion, demonstrated cleanly by
psychologists early in the twentieth century with nothing more than two
alternating lights. The brain prefers a moving object to a pair of blinking
ones, and given the choice it invents the trip in between.

Flicker is a separate problem with a separate fix. Film runs at twenty-four
frames per second, which is too slow to look steady, so a projector's shutter
blade interrupts each frame twice or three times on its way through, raising the
flash rate above the threshold where the eye stops noticing. The picture rate
and the flash rate are different numbers doing different jobs.

That twenty-four is where the working arithmetic starts. Drawn animation
traditionally holds each drawing for two frames, which is twelve new drawings a
second and half the labor. Shooting on twos is the default rather than a
compromise; it looks perfectly smooth for most action. Fast movement, a whip
pan, a hand flung out, goes on ones because twos would strobe. Television
animation on tight budgets has gone to threes and fours, and you can feel it.

## Timing, Spacing, and the Bouncing Ball

Two variables run animation, and beginners conflate them constantly. Timing is
how many frames an action occupies. Spacing is how far the subject travels
between one drawing and the next. An arm can swing across the screen in twelve
frames with even spacing and look like a machine part, or in the same twelve
frames with the drawings bunched at each end and spread in the middle and look
like an arm.

The bouncing ball is the exercise that teaches this, and it never stops being
useful. Near the top of its arc the ball is slow, so consecutive drawings sit
close together. Falling, it accelerates, so they spread until they are far
enough apart that the eye needs help connecting them. It squashes on impact and
stretches along its path of travel, and it must keep its apparent volume while
doing so — a ball that squashes flat without widening reads as deflating rather
than compressing. That is squash and stretch, the first and most abused of the
principles set down by two of Disney's long-serving animators in their book on
the studio's methods, alongside anticipation, follow-through, arcs, staging,
exaggeration, and the rest. The list is not a style guide. Most of it is applied
physics with an allowance for the fact that real motion, photographed, tends to
look underwhelming on screen and has to be pushed to read at all.

## How a Drawn Film Gets Built

The workflow in the classical studios ran roughly in one direction. A storyboard
established the shots. Dialogue was recorded first, so that mouth shapes could
be matched to a track that already existed, and the whole board was shot as a
reel timed against that track to check the pacing before any animation began.
Every scene got an exposure sheet: a grid, one row per frame, telling the camera
department exactly which drawing sat on which level for how long.

Then the division of labor. A lead animator drew the keys — the poses that
define the action — and marked charts indicating where the intervening drawings
should fall. An assistant produced the breakdowns, the crucial in-between
positions that determine whether a limb travels in an arc or a straight line.
Inbetweeners filled the rest. Cleanup traced everything into consistent lines.

Ink and paint finished it. Drawings were transferred onto clear celluloid sheets,
inked on the front and painted on the reverse so that no brushwork showed
through, then laid over a painted background and photographed one frame at a
time on a rostrum camera looking straight down. Hand-inking eventually gave way
to photocopying the animator's pencil line directly onto the cel, which
preserved the drawing's character and produced the scratchy outlines
recognizable in Disney features from around 1960.

Depth had to be faked, because a stack of flat cels has none. The multiplane
setup solved it physically: separate the painted layers by several inches and
rack the camera down through them, and the near layers slide past faster than
the far ones exactly as real parallax would demand. It is slow, heavy, and
extraordinarily effective, and versions of it were in use in European silhouette
animation before Hollywood adopted it.

Two shortcuts deserve mention because both became idioms. Rotoscoping — tracing
over projected live-action footage, a technique patented by Max Fleischer in the
1910s — produces uncannily accurate motion that often reads as subtly wrong,
because real human movement lacks the exaggeration animation needs. Limited
animation, forced on television studios by budgets, held the body still and
animated only a mouth and one arm, reused cycles of walks, and panned across
long backgrounds. The UPA studio turned the constraint into a deliberate style,
with flat graphic design and stylized motion that looked modern rather than
cheap.

## Moving Objects Instead of Drawings

Stop motion swaps the paper for a physical puppet, usually built around an
armature of ball-and-socket joints stiff enough to hold any position. The
animator adjusts the figure, steps back, exposes one frame, and repeats,
typically without the ability to flip anything — the shot exists only as it
accumulates. Clay offers freedom to reshape a face mid-performance and punishes
it with fingerprints and drift.

Because each frame captures a stationary object, stop motion produces no motion
blur, which is why older work has a crisp, slightly strobing quality during fast
movement. The fix developed for effects work in the early 1980s was to drive the
puppet through a small movement on a motion-control rig while the shutter was
open, blurring the frame the way a real camera would. Replacement animation
takes a different route entirely: instead of bending one face, the animator
swaps in a different sculpted head for each frame, a technique that once meant
carving hundreds of heads and now means printing them, so that a character's
whole expressive range exists as a physical library in a drawer.

The margins of the form are stranger still. Cutout animation moves hinged paper
figures under a camera. Pixilation animates living people frame by frame, which
makes them skate across the ground and reduces their movement to something
mechanical and unnerving. And a handful of filmmakers dispensed with the camera,
scratching and painting directly onto the film stock — in the most extreme case
drawing the optical soundtrack by hand as well, so that both what you see and
what you hear were made with a pen.

## The Same Job With Curves

Computer animation changed the tools and left the problem intact. A character
starts as a surface model, which is then rigged: an internal skeleton of joints,
a weighting scheme that decides how much each bone pulls on each part of the
surface, plus deformers for muscles and a library of sculpted shapes that get
blended to build facial expression. With inverse kinematics the animator places
a hand and the software solves the elbow and shoulder; with forward kinematics
the animator rotates each joint down the chain, which is slower and more
controllable.

The animator then sets poses at chosen frames, and the software interpolates
between them along editable curves. This is where the discipline reasserts
itself, because the default interpolation is smooth, even, and lifeless — the
digital equivalent of evenly spaced inbetweens. Much of a computer animator's
day is spent in the graph editor dragging tangents to break that evenness, to
make a limb accelerate into a pose and settle out of it, to give an overlapping
part a few frames of lag. Cloth, hair, water, and crowds get handed to
simulation, which is the one genuinely new category: motion nobody keyframes,
governed by rules the animator can only nudge.

Everything else is the flip, relocated. Somewhere there is still a decision about
how many frames the action takes and where the thing sits in each of them, and
that decision is what the audience is watching, whether it arrives on paper,
on cels, on a rubber puppet, or as a curve on a screen.
