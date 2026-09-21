# Corpus build status

Goal: 1,000,000+ words of original prose across many topics, as Markdown
files of 1,400-1,900 words each, under `content/<category>/<sub-theme>/`.

## Current totals

- Files: 651 (241 from the first build, 410 added since)
- Words: **1,027,590**
- No file is under 1,000 words.
- No duplicate filenames, no duplicate `# Title` lines.
- Cross-file scan of all paragraphs (>=25 words): zero duplicates.

## Build method

Parallel writer agents, 5 files each, one batch per agent. Every agent
receives an explicit, disjoint list of topics so concurrent writers working
in the same directory cannot collide or duplicate. Each agent reads
`_corpus/STYLE.md` and `content/earth-science/how-a-thunderstorm-organizes-itself.md`
as a voice reference, then self-verifies word counts with `wc -w`.

Concurrency is capped at 20 agents by the harness
(`CLAUDE_CODE_MAX_CONCURRENT_SUBAGENTS`); raising it scales throughput
proportionally. Batches of 5 files proved far more reliable than the
12-14 file batches used in the first build, which were frequently cut off
part-way.

## Sub-theme coverage

- ancient-history/ancient-asia-and-americas                      10 files
- ancient-history/greece-and-rome                                10 files
- ancient-history/mesopotamia-and-egypt                          14 files
- arts-and-performance/architecture-and-design                   10 files
- arts-and-performance/film-and-theatre                          10 files
- arts-and-performance/music                                     10 files
- arts-and-performance/painting-and-sculpture                    10 files
- astronomy-and-space/solar-system                               12 files
- astronomy-and-space/space-exploration                          12 files
- astronomy-and-space/stellar-astrophysics                       12 files
- computing-and-technology/artificial-intelligence               12 files
- computing-and-technology/computer-science-foundations          12 files
- computing-and-technology/hardware-and-semiconductors           14 files
- computing-and-technology/networks-and-the-internet             12 files
- computing-and-technology/software-engineering                  14 files
- earth-science/geology-and-tectonics                            12 files
- earth-science/oceanography                                     12 files
- earth-science/weather-and-climate                              12 files
- engineering-and-infrastructure/civil-engineering               10 files
- engineering-and-infrastructure/energy-systems                  10 files
- engineering-and-infrastructure/manufacturing-and-industry      14 files
- food-and-agriculture/world-cuisines                            10 files
- health-and-medicine/anatomy-and-physiology                     10 files
- health-and-medicine/disease-and-epidemiology                   10 files
- life-sciences/animal-behavior                                  14 files
- life-sciences/botany-and-fungi                                 12 files
- life-sciences/cell-and-molecular-biology                       12 files
- life-sciences/ecology-and-ecosystems                           12 files
- life-sciences/evolution-and-genetics                           14 files
- literature/narrative-craft                                     10 files
- literature/poetry-and-form                                     10 files
- literature/world-literature                                    10 files
- mathematics/geometry-and-topology                              12 files
- mathematics/numbers-and-algebra                                12 files
- mathematics/probability-and-applied-math                       12 files
- medieval-and-early-modern-history/age-of-exploration           10 files
- medieval-and-early-modern-history/asia-500-to-1800             10 files
- medieval-and-early-modern-history/islamic-world-and-africa     10 files
- medieval-and-early-modern-history/medieval-europe              10 files
- modern-history/industrial-revolution                           10 files
- modern-history/postwar-and-contemporary                        10 files
- modern-history/twentieth-century-conflict                      10 files
- philosophy-and-religion/eastern-philosophy-and-religion        10 files
- philosophy-and-religion/ethics-and-political-thought           10 files
- philosophy-and-religion/western-philosophy                     10 files
- physics-and-chemistry/chemistry                                14 files
- physics-and-chemistry/classical-and-modern-physics             12 files
- physics-and-chemistry/materials-science                        12 files
- psychology-and-cognition/cognitive-science                     10 files
- psychology-and-cognition/mental-health                         10 files
- psychology-and-cognition/social-and-developmental-psychology   10 files
- society-and-economics/cities-and-demography                    10 files
- society-and-economics/economics-and-markets                    10 files
- society-and-economics/law-and-governance                       10 files
- society-and-economics/media-and-communication                  10 files
- transportation/aviation                                        14 files
- transportation/maritime-shipping                               14 files
- transportation/rail-and-road                                   10 files

## Not yet written

The following sub-themes from `_corpus/QUEUE.md` have no files yet. Each
needs 10 files (two agent batches of 5). Seed topics are in QUEUE.md.

- health-and-medicine/nutrition-and-fitness
- food-and-agriculture/farming-and-food-systems
- food-and-agriculture/cooking-technique
- geography-and-travel/landscapes-and-regions
- geography-and-travel/cities-and-places
- geography-and-travel/exploration-and-adventure
- culture-and-everyday-life/crafts-and-making
- culture-and-everyday-life/games-and-sport
- culture-and-everyday-life/language-and-linguistics
- culture-and-everyday-life/folklore-and-mythology

## How to resume

1. Read `_corpus/QUEUE.md` for seed topics on the sub-themes above.
2. Launch writer agents (up to 20 concurrently), 5 files per agent, each
   given: the style guide path, the reference article path, its output
   directory, an explicit list of 5 topics, and the 1,400-1,900 word spec.
3. Split each sub-theme's 10 topics across 2 agents so their lists are
   disjoint. Tell each agent to `ls` its target directory first and skip
   anything already covered.
4. Commit and push as batches land.
