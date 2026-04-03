# Version v0.1.4 Documentation

## Title
Fixed Explicit Conference-Affiliation Line Breaks on the Title Page

## Quick Diagnostic Read

This patch release fixes a narrower follow-up bug in the multi-author title page.
It does three concrete things:

- keeps explicit `\\` line breaks inside `\addinstitute{n}{...}` in the same hanging-indent column,
- preserves the correct continuation alignment already achieved for automatic wrapping,
- updates the bundled showcase and root docs so the edge case is exercised and documented.

## One-Sentence Objective

Make conference affiliations behave consistently whether their second line comes from TeX wrapping naturally or from a user-inserted explicit line break.

## Why This Version Matters

`v0.1.3` fixed the large structural problem:
long affiliation rows no longer overran the slide.

But a smaller formatting defect remained.
When a user wrote an explicit `\\` inside an affiliation string, the continuation line did not stay in the intended post-number text column.

So the bug was subtle but real:

- automatic overflow looked correct,
- explicit line breaks did not,
- users could still produce visibly broken conference title pages with perfectly reasonable manual formatting.

This version matters because real users do not only rely on automatic wrapping.
They also insert deliberate breaks to control where a department or campus name turns over.

## Plan A / Plan B

### Plan A (Recommended)

1. Inspect the conference-affiliation row formatter.
2. Identify why automatic wraps and explicit `\\` breaks are following different layout paths.
3. Replace the raw hanging-indent paragraph approach with a fixed label column plus a fixed-width text box.
4. Recompile the showcase deck with explicit `\\` still present in the sample affiliations.
5. Verify the second title page visually and through PDF text extraction.

### Plan B

1. Tell users not to insert explicit `\\` inside affiliations.
2. Rely only on automatic wrapping.

Plan B avoids the symptom, but it leaves the template inconsistent and fragile.

## System View

```text
conference affiliation row
  -> green number label box
  -> fixed-width affiliation text column
  -> automatic wraps stay in that text column
  -> explicit \\ breaks also stay in that same text column
```

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/main.tex`

### Root docs updated in this version

- `README.md`
- `CHANGELOG.md`

### Versioned public docs added in this version

- `docs/version-0-1-4-docs.md`

### Governance docs reviewed but not changed

- `CONTRIBUTING.md`
- `SECURITY.md`
- `CODE_OF_CONDUCT.md`

### Generated verification outputs observed in this version

- `beamer-up/main.pdf`
- `beamer-up/titlepage-page2-check.png`
- `beamer-up/cairo-page2-check-02.png`

## Detailed Walkthrough

## 1) What went wrong

The earlier conference-affiliation fix used a hanging-indent paragraph model.

That solved one problem well:
when TeX wrapped a long affiliation line on its own, the continuation line stayed aligned after the affiliation number.

But explicit `\\` is not the same thing as natural paragraph wrapping.
It forces a line break inside the inserted affiliation content.
Because the row still depended on paragraph-level hanging-indent behavior, the explicit break could bypass the intended continuation alignment and restart from the wrong horizontal position.

So the root cause was not "line breaks in general."
It was a mismatch between:

- paragraph-level hanging-indent mechanics,
- user-authored internal line breaks inside the row content.

## 2) The fix

This version changes the affiliation row formatter to a more explicit two-part layout:

- a fixed-width label box for the green affiliation number,
- a fixed-width `\parbox` for the affiliation text itself.

That change matters because both of these cases now happen inside the same constrained text column:

- automatic overflow wrapping,
- explicit `\\` line breaks written by the user.

So the continuation line no longer has a chance to jump back to the row origin.
It stays inside the same post-number text area.

## 3) The showcase now demonstrates the actual edge case

The bundled multi-author example in `beamer-up/main.tex` now keeps explicit `\\` breaks in the affiliation samples.

That is important for regression prevention.
Without an explicit manual-break sample in the showcase, this exact bug could quietly return while long automatic-wrap cases still looked fine.

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
- the explicit `\\` inside the first conference affiliation no longer reset the continuation line to the left margin,
- the second line stayed in the same hanging-indent text column as automatic wraps,
- the second title page remained visually consistent with the earlier multiline title-page fixes.

Additional local visual confirmation was captured in:

- `beamer-up/titlepage-page2-check.png`
- `beamer-up/cairo-page2-check-02.png`

## Pitfalls and Debugging Notes

### 1) Natural wraps and explicit `\\` are not interchangeable in TeX internals

They may look similar on the page, but they do not always pass through the same layout behavior.
If a design depends on consistent continuation alignment, test both.

### 2) Hanging indent is not always enough when users can force their own line breaks

If content includes manual `\\`, a fixed-width text box is often the safer layout primitive.

### 3) Showcase decks should keep edge-case metadata on purpose

A real regression test deck should include:

- long automatic-wrap affiliations,
- explicit line breaks,
- multiline subtitle and institute fields.

That keeps visual regressions easy to spot.

## Practice Task

Edit one `\addinstitute{...}` value in `beamer-up/main.tex` so it contains an explicit `\\` at a different clause boundary.

Self-check:

- the break happens where you forced it,
- the next line still begins in the affiliation text column,
- the number column stays fixed.

## Next 24-72 Hours

1. Recheck the Filipino title-page route with the same explicit-linebreak affiliation samples.
2. Consider adding one explicit-linebreak single-author `\institute{...}` example if that path should guarantee the same visual contract.
3. Refresh any public screenshot asset only if the repository front page should now advertise this exact explicit-linebreak-safe baseline.
