# Corpus build status

Goal: 1,000,000+ words of original prose across many topics, as Markdown
files of 1,000-2,000 words each, under `content/<category>/<sub-theme>/`.

Plan: 68 sub-themes. The first 20 were written at 12 files each; every batch
from #21 onward is specified at **14 files of 1,400-1,900 words** (the early
batches averaged ~1,290 words, which left too little margin over 1M).

Build method: parallel writer agents, one per sub-theme, each reading
`_corpus/STYLE.md` plus `content/earth-science/how-a-thunderstorm-organizes-itself.md`
as a voice reference, then self-verifying word counts with `wc -w`.
Concurrency cap is 20 agents (`CLAUDE_CODE_MAX_CONCURRENT_SUBAGENTS`), which
is the throughput bottleneck.

## Progress at last checkpoint

- Files: 241
- Words: 354335
- No file is under 1,000 words.

## Sub-themes complete (12/12 files)

- astronomy-and-space/solar-system/
- astronomy-and-space/space-exploration/
- astronomy-and-space/stellar-astrophysics/
- computing-and-technology/artificial-intelligence/
- computing-and-technology/computer-science-foundations/
- computing-and-technology/networks-and-the-internet/
- earth-science/geology-and-tectonics/
- earth-science/oceanography/
- earth-science/weather-and-climate/
- life-sciences/botany-and-fungi/
- life-sciences/cell-and-molecular-biology/
- life-sciences/ecology-and-ecosystems/
- mathematics/geometry-and-topology/
- mathematics/numbers-and-algebra/
- mathematics/probability-and-applied-math/
- physics-and-chemistry/classical-and-modern-physics/
- physics-and-chemistry/materials-science/

## Sub-themes partially written — finish these first

Agents were interrupted mid-batch. Top these up to 14 files each.

- ancient-history/mesopotamia-and-egypt/ — 1 files, needs 13 more
- computing-and-technology/hardware-and-semiconductors/ — 1 files, needs 13 more
- computing-and-technology/software-engineering/ — 5 files, needs 9 more
- engineering-and-infrastructure/manufacturing-and-industry/ — 4 files, needs 10 more
- life-sciences/animal-behavior/ — 11 files, needs 3 more
- life-sciences/evolution-and-genetics/ — 4 files, needs 10 more
- medieval-and-early-modern-history/asia-500-to-1800/ — 0 files, needs 14 more
- medieval-and-early-modern-history/islamic-world-and-africa/ — 0 files, needs 14 more
- medieval-and-early-modern-history/medieval-europe/ — 0 files, needs 14 more
- physics-and-chemistry/chemistry/ — 7 files, needs 7 more
- transportation/aviation/ — 2 files, needs 12 more
- transportation/maritime-shipping/ — 1 files, needs 13 more
- transportation/rail-and-road/ — 0 files, needs 14 more

## Sub-themes not yet started

See `_corpus/QUEUE.md` — entries 21-68 list every remaining sub-theme with
seed topic directions. Anything not appearing in the two lists above still
needs its full 14 files.

## How to resume

1. Read `_corpus/QUEUE.md` for the remaining sub-theme list and seed topics.
2. Launch writer agents (up to 20 concurrently), one per sub-theme, each
   given: the style guide path, the reference article path, its output
   directory, its seed topics, and the 14-file / 1,400-1,900-word spec.
3. Tell each agent to `ls` its target directory first and only write topics
   not already covered there, so partial batches are topped up rather than
   duplicated.
4. Commit and push after each batch lands.
