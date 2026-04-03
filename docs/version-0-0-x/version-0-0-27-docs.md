# Version v0.0.27 Documentation

## Title
Strengthened the Light-Surface Title-Page Typography, Divider, and Conference Metadata Accents

## Quick Diagnostic Read

This version is a narrow cover-page polish pass.
It does four concrete things:

- bolds the title-page subtitle and keeps it dark on the white cover surface,
- turns the cover divider rule and venue/date separator dot maroon,
- makes conference affiliation superscripts and affiliation-list numbers forest green,
- refreshes the bundled showcase metadata and `v1.0.0` accent in `beamer-up/main.tex`.

## One-Sentence Objective

Make the light-surface single-author and conference title pages read as one coherent UP-directed hierarchy instead of leaving mixed accent colors and mismatched conference markers on the cover.

## Why This Version Matters

`v0.0.26` solved the larger title-page direction:

- white main field,
- maroon left accent bar,
- black runtime-cropped cover lockup.

What remained was smaller but visibly inconsistent:

- the subtitle weight still felt too light,
- the short divider rule stayed green,
- the venue/date separator dot stayed yellow,
- the conference superscripts above author names did not match the green affiliation numbers below,
- the bundled showcase metadata still leaned on older placeholder samples.

This version matters because it resolves those remaining accent mismatches inside the same title-page system instead of treating them as isolated one-off tweaks.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerinnerthemeUU.sty`.
2. Inspect `\uutitlemeta`, `\addinstitute`, and the `title page` template.
3. Change the divider, separator, and conference-marker colors in the actual title-page path.
4. Open `beamer-up/main.tex`.
5. Refresh the sample title metadata and the cover accent examples.
6. Compile `beamer-up/main.tex` with `pdflatex`.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Compare the first two title-page frames in the rebuilt showcase PDF against the prior `v0.0.26` cover treatment.
3. Confirm that the author superscripts, affiliation numbers, divider rule, and venue/date separator now follow the intended UP palette.

## System View

```text
light-surface title page
  -> runtime-cropped inline black UP cover lockup
  -> maroon title + forest-green version accent
  -> bold dark subtitle
  -> maroon divider rule
  -> maroon author/date line and maroon venue/date separator
  -> forest-green conference superscripts + affiliation list numbers
```

This matters because the cover now reads as one intentional accent system instead of mixing black, green, maroon, and yellow for unrelated reasons.

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/main.tex`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-27-docs.md`

### Generated verification outputs recorded in this version

- `beamer-up/main.aux`
- `beamer-up/main.bcf`
- `beamer-up/main.fls`
- `beamer-up/main.log`
- `beamer-up/main.nav`
- `beamer-up/main.out`
- `beamer-up/main.pdf`
- `beamer-up/main.run.xml`
- `beamer-up/main.snm`
- `beamer-up/main.toc`
- `beamer-up/main.vrb`

### Cleanup candidates recorded in the changelog

- `beamer-up/cover-check.bcf`
- `beamer-up/cover-check.log`
- `beamer-up/cover-check.pdf`
- `beamer-up/cover-check.run.xml`
- `beamer-up/cover-check.toc`
- `beamer-up/cover-check.vrb`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The conference affiliation markers now use the same green accent above and below

The visible bug on the multi-author title page was that the numbers below the author line were green while the superscripts attached to the author names stayed maroon.

This version fixes that in the actual Beamer title-author expansion path:

- `\addinstitute` now keeps the numbered affiliation list in `UPForestGreen`,
- the title-page template now overrides `\beamer@insttitle` rather than trying to shadow `\inst` locally,
- the result is that the superscripts beside each author now match the green numbered affiliation rows below them.

This is a small but important correction because the conference title page now reads as one system instead of two conflicting number treatments.

## 2) The light-surface cover now keeps maroon where the hierarchy wants emphasis

Once the title page moved to a white surface, the smaller accent elements mattered more.

This version therefore moves the remaining title-page accent separators into maroon:

- the short horizontal divider rule below the subtitle is now `UPMaroon`,
- the dot between venue and date is now `UPMaroon`.

That keeps the strongest emphasis on the same color family already used by the title and the author/date line.

## 3) The subtitle is now explicitly bold and dark on the white cover surface

The subtitle line was previously readable, but it still felt underweighted compared with the title and the new white cover treatment.

This version strengthens that hierarchy in two places:

- the title-page template now renders the subtitle in bold dark text on the light cover,
- the bundled showcase deck also wraps the sample subtitle in `\textbf{...}` so the public sample reflects the intended visual result directly.

The point is not just "more bold."
It is to make the title block feel deliberate after the broader white-surface inversion.

## 4) The bundled showcase deck now demonstrates the new cover rhythm more clearly

`beamer-up/main.tex` now also refreshes the sample content used on the first two title frames:

- the `v1.0.0` badge beside the title now uses a forest-green accent,
- the single-author title frame now uses refreshed UP-oriented sample metadata,
- the conference title frame now uses refreshed UP campus affiliations for the multi-author example.

That means the shipped showcase deck better demonstrates the intended single-author and conference title-page path for actual local academic use cases.

## Verification

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
```

Observed result on April 3, 2026:

- the deck compiled successfully on the supported `pdfLaTeX` path,
- page 1 and page 2 kept the expected single-author and multi-author title layouts,
- the cover divider rule and venue/date separator rendered maroon,
- the multi-author superscripts and affiliation-list numbers matched in forest green.

The existing bibliography warnings remain outside the scope of this narrow visual pass because `biber` was not rerun here.

## Pitfalls and Debugging Notes

### 1) `\inst` overrides inside title templates do not necessarily win

In Beamer, `\insertauthor` rewires `\inst` internally.
If you patch the wrong macro, the superscripts on the rendered author line will ignore your color change.

### 2) Small accent colors matter more on a white cover

Once the surface is light, leftover yellow or green accents stand out more sharply.
That is why the divider rule and the venue/date separator dot needed deliberate cleanup instead of being left as inherited secondary colors.

### 3) `pdfLaTeX` validation is enough for this narrow pass

This version validates the current supported baseline.
It does not reopen the broader engine-specific typography work.

## Practice Task

Compile the showcase deck and compare the two title pages.

Self-check:

- the subtitle is bold and dark,
- the divider rule is maroon,
- the venue/date separator dot is maroon,
- the superscript affiliation markers match the green numbers below,
- the title version accent remains forest green.

## Next 24-72 Hours

1. Decide whether the refreshed sample metadata should be generalized further for thesis-defense and lecture templates.
2. Re-run the full `pdflatex -> biber -> pdflatex -> pdflatex` chain if the bibliography warning noise should be cleared in the bundled PDF.
3. Continue packaging and release-note cleanup for the first public release.
