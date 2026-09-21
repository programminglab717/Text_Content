# How Economists Measure Inequality

The Dutch economist Jan Pen once asked his readers to imagine a parade. Everyone
in the country marches past in a single hour, arranged from poorest to richest,
and each person's height is scaled to their income, so that someone of average
income stands at average height. The parade opens with figures so small they are
hard to see. The minutes pass and the marchers stay stubbornly tiny. Only well
past the half-hour do people of recognisably normal stature appear, and only in
the final minutes does anything dramatic happen — at which point heads vanish
into the clouds, and the last few marchers are miles tall.

The image does something no single number can. It shows that the distribution is
not a spread around a middle but a long, thin tail attached to a dense clump, and
that nearly everyone marches below the mean. Any summary statistic has to
compress that shape into a scalar, and every method of compressing it throws
away something different. Choosing an inequality measure is therefore not a
technical preliminary to the analysis. It is part of the analysis, and it
embodies a judgement about which differences matter.

## Settle the Units First

Before any index can be computed, four questions have to be answered, and
disagreements about inequality are far more often disagreements about these than
about arithmetic.

What is being distributed? Market income, before taxes and transfers, measures
what the economy hands out before the state intervenes. Disposable income, after
direct taxes and cash benefits, measures what households can actually spend.
Consumption is smoother than either, because people borrow and save against
temporary swings, and in poorer countries it is often the only reliably measured
quantity. Wealth is a stock rather than a flow and behaves quite differently
again. A country can look egalitarian on one of these and unequal on another
without any contradiction.

Among whom? Per household, or per person? A household of four with twice the
income of a household of one is not twice as well off, but neither is it equally
well off, since rent, heating and a refrigerator are shared. Statistical agencies
handle this with equivalence scales, dividing household income by some function
of household size — commonly the square root of the number of members, or a
weighted count that gives the first adult a weight of one and additional adults
and children smaller weights. The choice of scale shifts measured inequality
appreciably, especially where family sizes differ systematically by income.

Over what period? Annual income conflates the genuinely poor with the medical
resident, the business owner who had a bad year, and the retiree living off
savings. Lifetime inequality is invariably lower than any single year's, because
the young poor and the old rich are partly the same people at different ages. A
country with high annual inequality and high mobility is a different place from
one with the same annual figure and none.

And who is counted? Top incomes are chronically under-reported in household
surveys, which is why researchers increasingly splice survey data with tax
records and national accounts. The very rich are hard to sample, reluctant to
answer, and hold income in forms that questionnaires do not name.

## The Lorenz Curve and Its Famous Summary

Max Lorenz proposed the workhorse diagram in 1905. Rank everyone from poorest to
richest along the horizontal axis as a cumulative share of the population; plot
the cumulative share of total income they receive on the vertical. Perfect
equality gives a straight diagonal: the bottom forty per cent have forty per cent
of the income. Real distributions sag below that line, and the depth of the sag
is the inequality.

Corrado Gini's coefficient, introduced a few years later, is simply the area
between the diagonal and the actual curve, expressed as a fraction of the whole
triangle beneath the diagonal. Zero means everyone has the same; one means a
single person has everything. Among rich countries, disposable-income values run
roughly from the mid-twenties to the low forties when expressed on a
zero-to-hundred scale, which is a narrow band that nonetheless separates
societies that feel quite different to live in.

The Gini's virtues are real. It is scale-invariant, so doubling every income
leaves it unchanged. It is population-invariant, so comparing a small country to
a large one is legitimate. It satisfies the transfer principle: moving money from
a richer person to a poorer one, without reversing their ranks, always reduces
it. And it can be pictured, which matters more than theorists like to admit.

Its weaknesses are equally real. A single number cannot distinguish between very
different shapes, and two countries can share a Gini while one has a hollowed-out
middle and the other a destitute bottom. Less obviously, the Gini is most
sensitive to transfers around the middle of the distribution and relatively dull
to what happens in the tails — an awkward property given that most public
argument about inequality concerns precisely the tails. And it is not cleanly
decomposable: the inequality of a whole population does not break tidily into
inequality within regions plus inequality between them, because the subgroup
distributions overlap.

## Ratios, Shares and Blunter Instruments

Because of those limits, most serious work reports several measures at once.

Percentile ratios are the bluntest and often the most communicative. The ratio
of income at the ninetieth percentile to that at the tenth compares a
comfortably-off household with a poor one while ignoring both extremes entirely.
Splitting it into the ninety-to-fifty and fifty-to-ten ratios separates what is
happening above the median from what is happening below it, which is how analysts
established that the American and British experiences of rising inequality
differed in structure, not merely in degree.

Income shares go straight for the tail. The share of total income received by the
top one per cent, or the top tenth of one per cent, is the statistic that
reshaped the public conversation in the past two decades, largely through the
long-run series assembled from tax records by Anthony Atkinson, Thomas Piketty,
Emmanuel Saez and their collaborators. The great advantage of these series is
historical reach: tax data go back a century or more in several countries, long
before household surveys existed. The great caveat is that tax data measure what
is declared under whatever rules applied at the time, and definitions of taxable
income change.

The Palma ratio, proposed by José Gabriel Palma, splits the difference. It
compares the income share of the top ten per cent with that of the bottom forty,
on the empirical observation that the five middle deciles capture a remarkably
stable share of national income across countries and eras. If the middle is
roughly fixed, the interesting action is the split of the remainder, and the
Palma measures exactly that.

## Measures With Ethics Written Into Them

Two families of index make explicit what the Gini leaves implicit.

Henri Theil borrowed from information theory, treating inequality as a kind of
entropy — a measure of how surprising the distribution of income across people
is, relative to a world where income is spread evenly. The payoff is exact
decomposability. A Theil index for a whole country separates cleanly into a term
for inequality within subgroups and a term for inequality between them, which
lets you ask how much of a nation's inequality is regional, or how much is
between occupations rather than inside them. Answers to those questions are
frequently surprising: between-group differences usually explain less of the
total than intuition suggests.

Anthony Atkinson's index goes further by making the value judgement a parameter.
It asks what fraction of total income a society could throw away, if the
remainder were distributed perfectly equally, and still be exactly as well off as
it is now. That fraction depends on an inequality-aversion parameter the analyst
must choose. Set it near zero and only the average matters; raise it and
increasing weight falls on the bottom of the distribution. Rather than burying an
ethical stance inside a formula, Atkinson put a dial on the front and asked
users to turn it deliberately.

## Wealth Is a Different Animal

Everything above applies to income. Wealth distributions are far more skewed,
partly because wealth accumulates over a lifetime and partly because it can be
negative — a graduate with student debt and a young family with a mortgage both
have less than nothing, which no income measure allows. Wealth Gini coefficients
routinely exceed those for income by a wide margin, often sitting above
seven-tenths even in countries with mild income inequality. The measurement
problems compound too. Housing is the main asset of the middle and is valued by
estimate; pension entitlements may or may not be counted; business equity is
illiquid and privately valued; and the wealthiest holdings are the most likely to
sit in structures designed not to be enumerated.

None of this makes the exercise futile, but it does mean that any single reported
figure conceals a chain of decisions. The honest way to read an inequality
statistic is backwards: find out what was being distributed, among whom,
adjusted how, over what interval, and measured by whom. A country's Gini can fall
while the top share rises, if the gains at the very top are swamped by
compression in the middle. Both facts are true. They are answers to different
questions, and the argument that follows is usually about which question anyone
should have been asking.
