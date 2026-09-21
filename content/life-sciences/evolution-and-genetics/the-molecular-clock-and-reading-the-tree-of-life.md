# The Molecular Clock and Reading the Tree of Life

In the early 1960s, Emile Zuckerkandl and Linus Pauling were comparing the amino
acid sequences of hemoglobin from different animals and noticed something they
had not been looking for. The number of differences between any two species'
hemoglobins scaled, roughly, with how long ago the paleontologists said those
species had diverged. Horse and human differed by more than human and gorilla.
Fish and human differed by more still, in about the proportion the fossil record
implied. The protein appeared to be accumulating changes at a rate steady enough
to function as a timer.

It was a startling suggestion, because nothing in Darwinian thinking predicts
constancy. Adaptation comes in bursts. Some lineages change fast and some barely
change at all — a coelacanth and a horse have had exactly the same amount of
time since their common ancestor, and one of them has done a great deal more
with it. If molecules were being shaped by selection the way bodies are, they
ought to be just as erratic.

## Why a Clock Can Tick at All

The resolution came from a different direction. Motoo Kimura argued in the late
1960s that the great majority of substitutions that become fixed in a genome are
not adaptive at all. They are neutral or nearly so — changes at third codon
positions, in introns, in pseudogenes, or amino acid swaps too mild to matter —
and their fate is decided by drift rather than selection. The mathematics of
that process has an elegant consequence. In a population, neutral mutations
appear at a rate proportional to population size, and each has a probability of
eventually being fixed inversely proportional to population size. The two
factors cancel. The long-run rate at which neutral substitutions accumulate in a
lineage equals the neutral mutation rate per generation, regardless of how large
or small or successful the population is.

That is the theoretical engine of the clock, and it explains its peculiar
behavior. Regions under strong functional constraint change slowly, because most
mutations there are removed; regions with no function change quickly, at close
to the raw mutation rate. Different genes therefore run at different speeds
while each stays roughly constant within itself, which is why a slowly evolving
ribosomal gene is used to compare bacterial phyla and a rapidly evolving
mitochondrial region is used to compare populations of the same species. Picking
the right molecule for the depth of the question is the first practical skill in
the field.

## Fossils, Calibration, and an Old Argument

A clock with no calibration gives relative distances, not dates. To convert
sequence divergence into years, some node in the tree has to be pinned to an
absolute age, and almost always that pin comes from a fossil. This is where the
method gets contentious, because fossils supply minimum ages, not true ages: the
oldest known member of a group tells you the lineage existed by then, not that
it did not exist earlier. Calibration therefore imports the uncertainties of the
fossil record into every date the clock produces.

The first serious collision came in the late 1960s, when Vincent Sarich and
Allan Wilson used immunological distances between blood proteins to estimate
when humans and African apes had diverged, and got something close to five
million years. The prevailing view among paleoanthropologists at the time,
resting on interpretations of a Miocene ape called Ramapithecus, put the split
three to five times earlier. The dispute was bitter and the molecular estimate
essentially won: Ramapithecus was reinterpreted as a relative of orangutans, and
subsequent fossil and genomic work settled on a divergence in the range the
molecules had indicated.

The lesson was not that molecules always beat rocks. In the reverse direction,
early molecular clock studies placed the diversification of modern bird and
placental mammal orders deep in the Cretaceous, tens of millions of years before
any fossils of those groups appear, implying that a substantial radiation had
gone unrecorded. Paleontologists objected that the rock record is not that bad.
Decades of refinement have narrowed but not closed the gap, and the current
picture involves some lineages originating before the end-Cretaceous extinction
while the explosive diversification came after it.

A third case shows what the method is good for when fossils are scarce. Human
mitochondrial DNA is inherited only down the maternal line and does not
recombine, so every copy alive today traces back through an unbroken chain of
mothers to a single ancestral molecule. Surveys of mitochondrial variation in
the 1980s found that the deepest splits were among African lineages and that
the total accumulated diversity was small, pointing to a recent common ancestor
and an African origin for modern humans. The popular name attached to that
ancestor was unfortunate, because it encouraged a misreading that the clock
itself makes obvious: the date marks when one molecule's lineages last
converged, not when a population arose or how many people were alive. Thousands
of women were her contemporaries, and their mitochondrial lines simply ended
somewhere in the intervening generations, as most lines do. The Y chromosome
tells a parallel story with a different and not necessarily matching date,
because each locus has its own coalescent history.

## Where the Clock Misbehaves

Constancy was always an approximation and the deviations are systematic enough
to model. Mutation happens largely during DNA replication, so species with short
generations accumulate substitutions faster per year: rodents evolve more
quickly than primates by this measure, and among primates, small quick-breeding
lemurs faster than great apes. Metabolic rate, body size, DNA repair efficiency,
and effective population size all leave their mark. Two lineages diverging from
the same ancestor can therefore accumulate visibly different amounts of change
in the same number of years.

A second problem is saturation. Given enough time, the same site mutates
repeatedly — a position that went from A to G and later to C records only one
observed difference despite two events, and a site that changed and changed back
records none. Raw counts of differences therefore underestimate the true amount
of evolution, increasingly so for deep comparisons, and flatten out entirely at
great distances. Correcting for this requires a statistical model of how
sequences change: how often transitions occur relative to transversions, whether
base frequencies are equal, and crucially how much the rate varies from site to
site across a gene. Fitting these parameters from the data and correcting the
distances is what turns a naive count into a usable estimate.

Modern practice abandons the strict clock altogether in favor of relaxed clocks,
which allow the rate to vary from branch to branch — either drifting gradually
from ancestor to descendant, or drawn independently on each branch from a
distribution. Combined with Bayesian inference and multiple fossil calibrations
expressed as probability distributions rather than fixed points, this yields
dated trees with honest credible intervals, which are often wide.

## Building the Tree Itself

Dating a tree presupposes having one, and reconstructing branching order is a
separate problem with its own methods. The simplest approach converts sequences
into pairwise distances and clusters them, which is fast and works acceptably
when rates are uniform. Maximum parsimony instead searches for the tree
requiring the fewest evolutionary changes, an intuitive criterion with a known
failure mode: when two lineages are evolving rapidly, chance similarities
accumulate between them, and parsimony pulls those long branches together
regardless of their true positions. Long-branch attraction misplaced several
major groups in the early molecular literature, and it does not go away with
more data — it gets more confident.

Maximum likelihood and Bayesian methods avoid this by evaluating trees under an
explicit model of sequence evolution, asking which tree and parameter values
make the observed data most probable. They are computationally heavy, since the
number of possible trees explodes past astronomical with even a few dozen taxa,
so the search is heuristic. Confidence is assessed by resampling sites and
rebuilding the tree many times, or read directly from the posterior
distribution.

The deeper complication is that a gene tree is not a species tree. Different
genes in the same organisms genuinely have different histories. Ancestral
polymorphism that persists through a speciation event sorts randomly into the
descendants, so some genes group species A with B and others group B with C —
incomplete lineage sorting, expected whenever divergences are close together and
ancestral populations were large. Hybridization moves genes across species
boundaries after the fact; Neanderthal sequence in living human genomes is an
example. Among bacteria, horizontal transfer is pervasive enough that the
tree metaphor strains, and different genes in the same cell can have radically
different provenances. Contemporary methods handle this by modeling the
coalescent process explicitly, inferring a species tree that best accounts for a
forest of conflicting gene trees rather than pretending the conflict is noise.

## Clocks Running Fast Enough to Watch

The oddest and most useful application inverts the usual logic. For organisms
that evolve quickly enough — RNA viruses, in particular, with error-prone
polymerases and generation times measured in hours — sequences sampled at
different dates differ measurably. The sampling dates themselves become the
calibration, no fossils required. Give a program a few hundred influenza or
coronavirus genomes tagged with collection dates and it will estimate the
substitution rate, place the most recent common ancestor in time, and often
locate it in space, which is how the origin dates of outbreaks are reconstructed
and how transmission chains are traced during them.

Ancient DNA does the same thing on an archaeological timescale. A genome
recovered from a bone with a radiocarbon date is a sample of a lineage as it
existed then, and enough such samples allow the rate of change to be measured
rather than assumed. That has made it possible to check the clock against
independent evidence over tens of thousands of years — and the checks have
generally held, with the dated mutation rate in humans coming out somewhat
slower than earlier phylogenetic estimates suggested, pushing a number of
divergence dates modestly further back.
