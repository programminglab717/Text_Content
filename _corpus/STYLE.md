# Corpus Style Guide — Text_Content

You are writing files for a large plain-prose corpus. Quality and variety matter:
this text will be read and processed, so it must read like genuine human-written
articles, not filler.

## Hard requirements (non-negotiable)

1. **Length: 1,000–2,000 words of body text per file.** Aim for 1,400–1,700.
   Verify with `wc -w <file>` after writing. If a file is under 1,000 words,
   expand it before moving on. Never pad with repetition to hit the count.
2. **Format:** plain Markdown. Start with a single `# Title` line, then prose.
   Use `##` subheadings (typically 3–6 per file). No YAML front matter.
   No "Word count:" footers, no meta-commentary about the assignment.
3. **Filenames:** lowercase kebab-case, `.md` extension, e.g.
   `the-carbon-cycle-explained.md`. Descriptive, not numbered.
4. **One topic per file.** Topics within your batch must be clearly distinct
   from one another — not twelve angles on the same subject.

## Voice and construction

- Write mostly in flowing paragraphs. Bullet lists are allowed but should be a
  minority of any file — never turn an article into an outline.
- Vary the register across your batch. Rotate among forms such as:
  explainer, historical narrative, essay, "how it works" walkthrough,
  profile of a person/place/object, field-guide or primer, argument/analysis,
  practical guide, retrospective.
- Vary sentence length. Mix short declaratives with longer developed sentences.
- Open with something concrete — an image, a moment, a question, a specific
  detail — not "In today's world" or "Throughout history".
- Avoid stock AI phrasing: "delve into", "tapestry", "it's important to note",
  "in conclusion", "navigate the complexities", "testament to". Avoid closing
  every file with a tidy summarizing paragraph; end where the thought ends.

## Accuracy

- Write only things you actually believe to be true. General, well-established
  facts are ideal.
- **Do not invent precise statistics, dates, study results, quotations, or
  citations.** If you don't know an exact figure, write qualitatively
  ("roughly a third", "by the late nineteenth century") or leave it out.
- Do not fabricate named sources, papers, or people. Real named people are fine
  when you are confident about them; don't invent quotes for them.
- No references section, no footnotes.

## What not to write

- Nothing about Claude, AI assistants, this task, or corpus generation.
- No placeholders, TODOs, or "[expand here]".
- No duplicated paragraphs across your files.
