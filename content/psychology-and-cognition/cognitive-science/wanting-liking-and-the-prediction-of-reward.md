# Wanting, Liking, and the Prediction of Reward

At McGill in 1954, James Olds and Peter Milner were aiming an electrode at a
region of the rat brainstem and missed. The animal they had implanted started
doing something odd: it kept returning to the corner of the enclosure where the
current had been delivered, and it would go back there reliably enough that they
could steer it around the box by waiting until it wandered into a spot they
liked and then stimulating.

So they built the obvious apparatus. A lever, wired so that pressing it
delivered a brief pulse through the electrode, and a rat left alone with it. The
rat pressed. It pressed at rates nothing in the ordinary rat repertoire could
match, for hours, pausing only when it collapsed. Offered the choice between the
lever and food after a day without eating, it chose the lever. It would cross an
electrified floor grid to reach the lever at currents that stopped a hungry rat
from crossing to reach a meal.

The immediate interpretation was that they had found the pleasure center, and
for about two decades that reading held. It was wrong in a way that took a long
time to see, and the correction turns out to be the most interesting thing in
the field.

The finding crossed into humans quickly and badly. Through the 1950s and 1960s
several groups implanted electrodes in psychiatric and neurological patients and
let them self-stimulate, most notoriously Robert Heath at Tulane, in work whose
consent arrangements and therapeutic aims would not survive any modern review
board. What the patients reported is the part worth keeping. They pressed
compulsively, and when asked what it felt like they generally did not describe
rapture. They described wanting to press again, an urgency, a sense that
something was about to happen — closer to the feeling of being on the verge of
something than to the feeling of having got it.

## What Is Actually Down There

The electrode was near the medial forebrain bundle, a thick fiber tract
carrying, among much else, the axons of dopamine neurons headed from the
midbrain to the forebrain. Those cell bodies sit in two small clusters: the
ventral tegmental area and the substantia nigra. They are not numerous — a few
hundred thousand in a human brain, against tens of billions of neurons overall —
but each one branches extravagantly, so that a modest population blankets
enormous stretches of forebrain.

Three projections matter here. The nigrostriatal pathway runs from substantia
nigra to the dorsal striatum, is central to the initiation of movement and to
habit formation, and is the one that dies in Parkinson's disease. The mesolimbic
pathway runs from the ventral tegmental area to the nucleus accumbens, in the
ventral striatum. The mesocortical pathway carries the same signal up to
prefrontal cortex.

Dopamine is not a fast transmitter in the way glutamate is. It is a modulator:
released more slowly, acting on receptors that alter a target cell's
responsiveness rather than directly exciting or inhibiting it, and spreading
through tissue to reach receptors some distance from the release site. It
changes the gain on whatever else is happening. Calling it the pleasure chemical
is roughly as informative as calling a thermostat the warmth device.

## The Signal Is About Surprise

The decisive experiments were Wolfram Schultz's, recording from individual
dopamine neurons in monkeys during simple learning tasks.

Give a monkey an unexpected squirt of juice and the dopamine neurons fire a
short burst. Straightforward enough, and consistent with reward. Now precede the
juice with a tone, consistently, for a few dozen trials. The burst does not
simply grow. It moves. Once the tone reliably predicts the juice, the neurons
stop responding to the juice altogether and fire instead at the tone — the
moment the world's estimate of the future improved. And if the tone comes and
the juice does not, something striking happens: at exactly the time the juice
was due, the neurons' firing drops below their baseline rate. A pause. The
absence of an expected good thing is signaled by a hole in the activity, timed
to the moment of disappointment.

What the neurons are reporting is not how good something is. It is the
difference between how good it turned out to be and how good it was expected to
be — a reward prediction error. Positive when the world outperforms
expectations, zero when it meets them exactly, negative when it falls short.

This is precisely the quantity a learning system needs. It had been derived
independently from animal conditioning data, where it explains why a cue that
adds no new information about an upcoming reward fails to become associated with
it, and independently again in machine learning, where temporal difference
methods use exactly this error term to learn the value of states. Three lines of
work converging on the same equation, and then a population of midbrain neurons
found to be broadcasting it, is about as good as neuroscience gets.

It also explains a piece of everyday experience that otherwise looks like a
design flaw. If the signal that drives learning is the gap between expectation
and outcome, then reliably getting what you expected produces nothing. The raise
that has been anticipated for months lands flat on the day it arrives.
Expectation catches up with circumstance, the error term returns to zero, and
the system goes looking for the next gap.

## Wanting Without Liking

That left the Olds and Milner rat unexplained. If dopamine carries a teaching
signal, why does stimulating the pathway feel — or at least act — so compelling?

Kent Berridge attacked this by finding a way to measure pleasure that did not
depend on asking. Rats given something sweet produce a stereotyped pattern of
facial and mouth movements: rhythmic tongue protrusions, a particular lip
motion. Given something bitter they produce a different pattern: gapes,
headshakes, forelimb flails. The same two patterns appear in human newborns,
which is good evidence they index something basic about hedonic impact rather
than learned display.

Now deplete a rat's dopamine severely. The animal stops working for food. It
will not press levers, will not approach, and will starve in a cage with food in
it. On the pleasure-center account it should also have stopped finding food
pleasant. But put sweet liquid directly in its mouth and the liking reactions
are entirely normal. It still likes the taste. It simply will not do anything to
get it.

Run the experiment the other way and the dissociation holds. Boost dopamine
function, or sensitize the system with repeated stimulant exposure, and animals
work far harder for rewards and are far more strongly gripped by cues that
predict them — without any increase in the liking reactions. More wanting, the
same amount of pleasure.

Berridge's term for what dopamine does is incentive salience: it makes things
and the cues that signal them magnetic, worth approaching, hard to ignore.
Liking is generated elsewhere, by opioid and endocannabinoid signaling in small
hedonic hotspots within the nucleus accumbens shell and the ventral pallidum,
regions where a microinjection can amplify the pleasure of a sweet taste. Those
hotspots are tiny. The wanting system is vast. We are built to pursue much more
thoroughly than we are built to enjoy.

A third strand of evidence comes from what dopamine does to effort. John
Salamone's experiments gave rats a choice between climbing a barrier to reach a
preferred food and eating a less preferred food freely available in the same
chamber. Normal rats climb. Rats with accumbens dopamine depleted stop climbing
and eat the cheap option instead — they have not lost their preference, and they
will still eat the good food happily if it is placed within reach, but they will
no longer pay for it. Dopamine sets the price the animal is willing to meet.
That framing has since carried over into human work on effort-based decision
making, where the willingness to exert for a payoff turns out to be a measurable
trait that moves with dopaminergic drugs and that is reduced in several
disorders.

Underneath the fast bursts there is also a slow one. Dopamine neurons maintain a
background firing rate, and the resulting ambient concentration seems to track
something more like the average rate of reward available in the current
situation — an estimate of how rich the environment is, which sets how
vigorously it is worth doing anything at all. The brief phasic burst says this
particular thing was better than expected. The tonic level says whether it is
worth getting out of bed.

## The Clinical Edge

Every reliable drug of abuse raises dopamine in the accumbens, by different
routes — cocaine by blocking reuptake, amphetamine by forcing release, opioids
and nicotine and alcohol by acting on the neurons upstream. Because the increase
is pharmacological, it does not behave like a natural reward. A natural reward
becomes predictable, the prediction error shrinks, and learning stops. A drug
produces the signal directly regardless of prediction, so the error term never
fully closes and the associated cues — the street, the lighter, the time of day
— keep accruing incentive salience.

The wanting-liking split gives that account its teeth. Sensitization of the
wanting system with repeated exposure, combined with tolerance in the systems
that generate pleasure, predicts exactly the state that addicted people describe
and that moralizing accounts of addiction cannot accommodate: craving that has
grown enormous alongside enjoyment that has largely gone. Wanting something you
no longer like is incoherent as folk psychology and perfectly coherent as
neuroscience.

The cleanest natural experiment runs through Parkinson's disease. Treating it
with dopamine agonists sometimes produces, in patients with no history of
anything of the kind, compulsive gambling, compulsive shopping, hypersexuality,
or binge eating — behaviors that begin after the drug is started and typically
resolve when the dose is reduced. The same pharmacology that restores movement
can install an appetite.

Depression approaches the machinery from the other side. Anhedonia has long been
described as an inability to feel pleasure, but when it is measured carefully
what is often impaired is not the momentary pleasure of a reward so much as the
capacity to learn from it and to be motivated by the prospect of it — a blunting
of the prediction error rather than of the hotspots. The pleasure is available;
the pull toward it is not.

Commercial design found all of this empirically long before the neuroscience
arrived. A slot machine pays on a variable schedule, which keeps the prediction
error alive indefinitely, and its near-misses are engineered rather than
incidental. Feeds that refresh with unpredictable content are built on the same
arithmetic. Nothing mysterious is being exploited. The system is doing what it
evolved to do, which is to attend hardest to whatever the world has not yet made
boring.
