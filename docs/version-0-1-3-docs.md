# Version v0.1.3 Documentation

## Title
Fixed Title-Page Multiline Metadata Flow and Wrapped Long Conference Affiliations

## Quick Diagnostic Read

This patch release corrects the title-page layout behavior under realistic metadata stress.
It does four concrete things:

- stops multiline title-page fields from pushing lower metadata off the bottom edge,
- adds a one-line bottom buffer so the cover block does not hug the page edge,
- wraps long multi-author affiliation rows inside the title block,
- applies hanging-indent continuation lines so wrapped affiliations follow the numbered reference style.

## One-Sentence Objective

Keep the single-author and multi-author title pages visually stable when users add real multiline metadata such as long institutes, campus names, or conference affiliations.

## Why This Version Matters

Title pages fail in a very visible way when layout assumptions only hold for short placeholder strings.

Before this update:

- adding line breaks to `\institute` or other title-page fields increased the text block only downward,
- the lower metadata lines could end up too close to the bottom edge,
- long `\addinstitute` values in multi-author mode were rendered through a non-wrapping `tabular` cell and could run off the slide.

This version matters because it makes the checked-in title-page baseline behave like an actual presentation template instead of only a short-demo composition.

## Plan A / Plan B

### Plan A (Recommended)

1. Reserve a bounded vertical region for the title-page text block.
2. Bottom-align the stack inside that region so added lines consume space upward.
3. Add a deliberate one-line bottom buffer.
4. Replace the multi-author affiliation `tabular` with paragraph-based hanging-indent rows.
5. Recompile the showcase deck and verify the second title page with both PDF text extraction and a rendered preview.

### Plan B

1. Keep the top-anchored layout.
2. Shorten the sample metadata only.

Plan B hides the bug in the demo, but it does not fix the template behavior for real users.

## System View

```text
single-author / multi-author title page
  -> bounded title-content region
  -> bottom-aligned content stack with one-line lower buffer
  -> long metadata grows upward instead of downward
  -> multi-author affiliation rows are paragraphs, not fixed-width table cells
  -> continuation lines hang after the affiliation number
```

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/main.tex`

### Root docs updated in this version

- `README.md`
- `CHANGELOG.md`

### Versioned public docs added in this version

- `docs/version-0-1-3-docs.md`

### Governance docs reviewed but not changed

- `CONTRIBUTING.md`
- `SECURITY.md`
- `CODE_OF_CONDUCT.md`

### Generated verification outputs observed in this version

- `beamer-up/main.pdf`
- `beamer-up/titlepage-page2-check.png`

## Detailed Walkthrough

## 1) The original title-page bug was a top-anchor problem

The title-page template used a fixed top skip and then placed all cover text into a top-aligned `minipage`.

That means TeX treated the cover copy like a box whose top edge was fixed in place.
When users added line breaks to `\institute`, `\title`, or similar fields, the box simply became taller downward.

So the visible failure was predictable:

- the title stack did not rebalance,
- the author, institute, and date lines moved closer to the page bottom,
- the cover looked broken even though the text itself was technically present.

This version replaces that behavior with a bounded title-content region whose content is bottom-aligned.
The result is that additional lines consume available space upward inside the reserved cover area.

## 2) The cover now keeps a deliberate lower breathing room

After the first structural fix, the title stack behaved correctly but sat too close to the bottom edge.

This version therefore adds a one-line bottom buffer inside the reserved title-content height.
That preserves the multiline-safe behavior while restoring the intended visual breathing room below the date or venue/date line.

## 3) The multi-author affiliation bug was caused by a non-wrapping table cell

The original conference-affiliation block rendered `\@uuconfinstitute` inside:

- a `tabular`,
- with a single `l` column,
- and natural-width content.

That layout never offered TeX a real wrapping width for long affiliation strings.
As a result, long department and campus names overran the slide edge instead of wrapping.

This version removes that table-based rendering path and replaces it with numbered paragraph rows.
Each affiliation row now:

- prints its index in `UPForestGreen`,
- reserves a fixed hanging-indent width for that index,
- wraps the text within the title block width,
- aligns continuation lines after the number rather than under it.

That matches the reference-style continuation behavior the user requested.

## 4) The showcase deck now exercises the real edge cases

The bundled `beamer-up/main.tex` demo was updated to use:

- a multiline subtitle path for the supported UP System wording,
- a multiline single-author institute path,
- long-form multi-author affiliation names for the conference example.

That matters because the checked-in showcase now demonstrates the supported behavior directly instead of leaving the regression hidden behind short sample text.

## Validation

Local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdftotext -f 2 -l 2 main.pdf -
```

Observed result on April 3, 2026:

- the deck compiled successfully,
- the title pages remained within the slide bounds,
- the single-author title page kept its bottom breathing room,
- the multi-author affiliation rows wrapped cleanly,
- continuation lines aligned after the affiliation number rather than under it.

Additional local visual confirmation was captured in `beamer-up/titlepage-page2-check.png`.

## Pitfalls and Debugging Notes

### 1) A `tabular` is the wrong tool for paragraph-wrapping affiliations

If the content needs natural paragraph wrapping, a single `l` column will usually fight you.
Use a paragraph-based structure with explicit hanging-indent behavior instead.

### 2) Fixing growth direction and fixing page breathing room are separate concerns

Making the content grow upward solved the functional bug.
Adding the one-line lower buffer solved the visual follow-up.

Both were needed for a clean final result.

### 3) Demo metadata should exercise real lengths

If the bundled showcase uses only short placeholder institutions, title-page regressions stay hidden until users hit them in actual thesis or conference decks.

## Practice Task

Open `beamer-up/main.tex` and make one of the multi-author affiliations one clause longer.

Self-check:

- the affiliation still wraps inside the slide,
- the second line starts after the number,
- the venue/date row keeps its lower breathing room.

## Next 24-72 Hours

1. Recheck the Filipino title-page route with equally long affiliation text so the same wrapping behavior is confirmed under both runtime logo selections.
2. Add one showcase example that uses an intentionally long single-author `\institute{...}` entry without manual line breaks.
3. Capture a refreshed public screenshot if the repository front page should start advertising this exact corrected title-page baseline.
