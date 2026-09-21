# The Shapes of an Epidemiological Study

Suppose you want to know whether a chemical in drinking water causes a rare
cancer. You cannot randomly assign a thousand people to drink it for twenty
years, and you would not be permitted to if you could. Nearly everything
difficult about epidemiology follows from that sentence. The discipline exists
because the cleanest way to establish cause — do the thing to one group,
withhold it from another, compare — is frequently unavailable, and the
alternative is to observe people who have sorted themselves into groups for
reasons of their own.

Study designs are the accumulated answers to that problem. Each one trades away
something to get something else, and learning to read health research mostly
means learning which trade a given study made.

## The Trial, and Why Randomization Is Worth So Much

In a randomized controlled trial the investigator assigns the exposure by
chance. This sounds like a small technical detail and is in fact the whole game.
Random assignment makes the two groups comparable not only in the
characteristics you thought to measure but in the ones you did not think of,
the ones you cannot measure, and the ones nobody has discovered yet. No
observational method can offer that.

The supporting machinery matters almost as much. Allocation is concealed so
that the person enrolling a patient cannot steer a sicker one toward the
control arm. Participants and assessors are blinded where possible, because
knowing which treatment you received changes how you report symptoms and how a
clinician judges them. Analysis follows the intention-to-treat principle —
everybody is counted in the group they were assigned to, even if they never
took the pill — because dropping non-adherent participants quietly reintroduces
the self-selection that randomization was meant to remove.

The polio vaccine field trial of 1954 remains the emblematic example: hundreds
of thousands of American schoolchildren, a placebo injection for the control
group, and a result decisive enough to end the argument in a single season.

What trials cannot easily do is study harmful exposures, rare outcomes, long
latencies, or anything that takes decades. They are expensive. And their
results carry an asterisk about generalizability, because the people who enrol
in trials are typically younger, healthier, and more adherent than the patients
who will eventually receive the treatment.

## Following People Forward

A cohort study starts with exposure and waits. Identify a group, record who
smokes and who does not, or who works with asbestos and who does not, and
follow everyone over time, counting the outcomes as they occur. Because
exposure is recorded before the disease exists, the sequence of events is
unambiguous, and because you are watching a defined population over a defined
period you can calculate genuine incidence rates and compare them directly as a
relative risk.

Two cohorts founded around 1950 shaped modern medicine. In Framingham,
Massachusetts, investigators began following an entire town's adults for
cardiovascular disease, an undertaking that gave the language the phrase "risk
factor" and produced the connections between blood pressure, cholesterol,
smoking, and heart attacks that now seem self-evident. In Britain, Richard Doll
and Austin Bradford Hill sent a questionnaire to the country's registered
doctors about their smoking habits and then followed them for the rest of their
lives, an elegant choice because doctors are easy to trace through a
professional register and their deaths are reliably recorded.

Cohorts are expensive and slow, and they are vulnerable to loss to follow-up —
if the people who disappear differ systematically from those who remain, the
result bends. A variant called the retrospective cohort dodges the waiting by
reconstructing the past from existing records: find a factory's employment
files from 1965, determine who worked where, and look up what happened to them.
Fast and cheap, but limited to whatever the records happen to contain.

## Working Backwards From the Outcome

For a rare disease, a cohort is hopeless. Follow ten thousand people for a
decade and you may accumulate three cases. The case-control design inverts the
logic: gather people who already have the disease, gather a comparison group
who do not, and look backwards at what each was exposed to. Doll and Hill's
first work on smoking took this form, interviewing lung cancer patients in
London hospitals alongside other patients — and the tobacco association emerged
clearly enough that they went on to build the cohort that confirmed it.

Case-control studies are fast, cheap, and the only practical approach to
uncommon outcomes. They also fail in a characteristic way. The comparison group
must be drawn from the same underlying population that produced the cases,
which is deceptively hard to arrange, and selecting controls badly can
manufacture an association out of nothing. Exposure information usually depends
on memory or old records, and memory is not neutral: a parent of a child with a
birth defect has spent months reconstructing every medication of a pregnancy,
while the parent of a healthy child has not. That asymmetry is recall bias, and
it pushes results in a predictable direction. Because you choose how many
controls to enrol, a case-control study cannot tell you how common the disease
is; it yields an odds ratio, which approximates relative risk well when the
disease is rare and misleads when it is not.

Several hybrid designs soften these weaknesses. A nested case-control study
sits inside an existing cohort: everybody's blood was collected and frozen at
enrolment, years before anyone fell ill, so when cases accumulate you thaw
their samples and those of matched cohort members and measure only what you
need. Exposure data then comes from before the disease rather than from
memory, at a fraction of the cost of assaying the whole cohort. Stranger and
more useful still is the self-controlled case series, in which each person
serves as their own comparison. Only people who experienced the outcome are
included, and the question becomes whether the event clustered in the window
just after an exposure relative to the rest of that same individual's follow-up
time. Because the comparison is within a person, everything stable about them —
genetics, habits, chronic illness — is automatically controlled. This is the
workhorse design for vaccine safety questions, where the exposure is brief,
dated precisely, and the outcome rare.

## Snapshots and Aggregates

A cross-sectional study measures exposure and outcome at the same moment. It is
the natural design for a national health survey, and the right tool for
establishing prevalence — how many people currently have hypertension, how many
have never been screened. As evidence about causation, it is weak, because the
photograph cannot tell you which came first. If sedentary people have more
back pain, the study cannot distinguish whether inactivity caused the pain or
the pain caused the inactivity. That ambiguity is reverse causation, and
cross-sectional data is permanently exposed to it.

Ecological studies compare groups rather than individuals: average fat
consumption per country against national breast cancer rates, or water
fluoridation by district against dental decay. They are useful for generating
hypotheses and are sometimes the only available data. Their signature failure
has its own name. The ecological fallacy is the assumption that a relationship
between group averages holds for the individuals inside those groups. A country
can have both high average wine consumption and low heart disease without a
single wine drinker being protected.

## The Things That Go Wrong

Confounding is the central hazard of all observational work. A third factor
causes both the exposure and the outcome, and an association appears where no
causal link exists. Coffee drinking once looked associated with lung cancer,
because coffee drinkers were disproportionately smokers. Statistical adjustment
handles confounders you have measured accurately. It does nothing about those
you have not measured, measured poorly, or failed to imagine — which is why
randomization retains its privileged status.

Selection bias enters whenever the process of getting into the study is related
to both exposure and outcome. Volunteers differ from non-volunteers; hospital
patients differ from the community; people who answer surveys differ from those
who bin them.

The cautionary tale most often cited concerns hormone therapy after menopause.
A long run of observational studies suggested it protected against heart
disease, and practice changed accordingly. When large randomized trials were
finally conducted, they did not reproduce that benefit. The favoured
explanation is that women who took hormone therapy in those decades were also
more affluent, more health-conscious, and under more medical supervision than
women who did not — a healthy-user effect that no amount of adjustment had
removed. It was not a scandal so much as a demonstration that observation and
experiment can diverge, and that the divergence is informative.

Chance is the remaining adversary, and it is the one most often misread. A
small study produces an unstable estimate, which is why a confidence interval
matters more than the point estimate sitting in the middle of it: a wide
interval straddling no effect and a large one is a study that has answered
nothing, regardless of what its abstract emphasizes. Trouble also arrives
through sheer volume. Examine forty dietary exposures against twenty diseases
and a handful of associations will clear the conventional threshold for
statistical significance by luck alone. This is why pre-registering the
intended analysis before the data are seen has become standard practice for
trials, and why a finding drawn from a subgroup nobody planned to examine
deserves more scepticism than the headline result of the same study.

## Deciding That Something Causes Something

No single study proves causation. In a 1965 address, Bradford Hill set out a
list of considerations that has been used ever since — not a checklist to be
scored, as he was careful to say, but a set of questions worth asking. How
strong is the association? Has it been found repeatedly, in different
populations, by different methods? Does the exposure reliably precede the
disease? Is there a dose-response gradient, so that more exposure means more
outcome? Is there a plausible biological mechanism, and does the claim fit what
is already known? Has anything resembling an experiment been done?

Temporality is the only one that is strictly required. The others are weights
on a judgement, and Hill's point was that judgement is what the evidence
ultimately demands.

Modern practice leans heavily on triangulation: if a cohort, a case-control
study, a natural experiment, and an analysis using genetic variants as a proxy
for lifelong exposure all point the same way, and each has different weaknesses,
the convergence is more persuasive than any one of them. The designs are not a
hierarchy so much as a set of instruments with non-overlapping blind spots, and
the skill lies in knowing which blind spot you are standing in.
