# Version v0.0.26 Documentation

## Title
Inverted the Title-Page Surface to White, Swapped the Left Accent Bar to Maroon, and Moved the Cover Lockup to Runtime-Cropped Black UP Assets

## Quick Diagnostic Read

This version is a narrow title-page presentation pass.
It does four concrete things:

- turns the title-page main field from maroon to white,
- turns the left vertical accent bar from forest green to maroon,
- switches the non-`nl` title-page logo path to runtime-cropped inline black English and Filipino UP cover lockups,
- keeps the already repaired title-page composition while making the cover readable on the lighter surface.

## One-Sentence Objective

Make the front and cover slides read more cleanly by inverting the title-page surface to a white field with a maroon side bar and a title-page logo treatment that actually belongs on a light background.

## Why This Version Matters

The prior title-page passes had already fixed the broken trim behavior and made the UP cover mark render reliably.

What still felt unresolved was the cover-page color balance.
The user asked for a simpler directional change:

- the large maroon background should become white,
- the left forest-green bar should become maroon.

That sounds small, but a title page is not just a background fill.
Once the surface becomes white, the title-page logo and the title metadata can no longer stay on the dark-surface color path.

This version matters because it completes that inversion cleanly instead of only swapping the fills and leaving the rest of the cover page mismatched or unreadable.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerinnerthemeUU.sty`.
2. Inspect the title-page TikZ background fills and the title-page content block.
3. Change the left accent bar to maroon and the main title-page field to white.
4. Apply local title-page text colors appropriate for a light background.
5. Open `beamer-up/beamerthemeUU.sty`.
6. Switch the non-`nl` title-page logo include hook to black runtime-cropped cover assets.
7. Compile `beamer-up/main.tex`.
8. Export and inspect page 1.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Compare the added black runtime title-page assets under `beamer-up/logos/` with the earlier white runtime title-page assets.
3. Open the generated page-1 preview and confirm the new light-surface cover behavior.

## System View

The title-page path now behaves like this:

```text
title-page background fill
  -> left accent bar = maroon
  -> main title-page field = white
  -> title-page logo include = runtime-cropped inline black UP cover lockup
  -> local title/subtitle/author/institute/date colors for light background
  -> same rebalanced left-aligned title-page content block
```

This matters because the visible cover result is controlled by the combined surface, logo, and text path rather than by any one of those parts on its own.

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerthemeUU.sty`

### Runtime assets added in this version

- `beamer-up/logos/up-inline-logo-eng-runtime-black.png`
- `beamer-up/logos/up-inline-logo-tag-runtime-black.png`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-26-docs.md`

### Generated verification outputs recorded in this version

- `beamer-up/main.bcf`
- `beamer-up/main.fls`
- `beamer-up/main.log`
- `beamer-up/main.pdf`
- `beamer-up/main.run.xml`
- `beamer-up/main.synctex.gz`
- `beamer-up/main.toc`
- `beamer-up/main.vrb`
- `beamer-up/titlepage-white-preview.png`
- `beamer-up/titlepage-white-preview-current.png`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The title-page surface is now intentionally inverted

`beamer-up/beamerinnerthemeUU.sty` now changes the title-page fills directly inside the title-page template:

- the left accent bar is `UPMaroon`,
- the main field is `UPWhite`.

This keeps the overall inherited composition logic intact while changing the title-page mood much more decisively than the earlier dark-surface variant.

## 2) The title-page text colors are now local to the lighter cover surface

The root Beamer color theme still needs to support the rest of the deck, including maroon and dark surfaces elsewhere.

Because of that, this version does not globally rewrite the document color theme just to satisfy the title page.
Instead, the title-page template now applies local title-page color overrides before rendering the title content block:

- title in maroon,
- subtitle in muted dark gray,
- author in maroon,
- institute in muted dark gray,
- date in muted dark gray.

That keeps the title-page inversion tightly scoped and avoids collateral regressions on the section pages, content slides, or the repaired closing slide.

## 3) The non-`nl` title-page logo path is now the black runtime-cropped family

Once the title page became white, the title-page lockup needed to leave the white-asset path.

This version adds:

- `up-inline-logo-eng-runtime-black.png`
- `up-inline-logo-tag-runtime-black.png`

and points the non-`nl` title-page include hook at those assets.

The important detail is that these are runtime-cropped bounded assets, not the raw large-canvas source PNGs.
That preserves the stable title-page placement behavior that was achieved in the previous title-logo rendering fix.

## 4) The change stays limited to the cover pages

This version does not rewrite the header logo system or the thank-page footer logo system.

It keeps:

- the content-slide header lockup logic,
- the repaired `\thankframe` layout,
- the current bibliography example path,
- the earlier title-page text-block rebalance.

Only the title-page surface and its title-page-specific logo/text treatment changed here.

## Verification

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdftoppm -png -f 1 -singlefile main.pdf titlepage-white-preview-current
pdftotext -f 1 -l 2 main.pdf -
```

Observed result on April 2, 2026:

- the deck compiled successfully,
- page 1 rendered with a white main field and a maroon left accent bar,
- the title-page logo used the new black runtime-cropped inline UP cover lockup path,
- pages 1 and 2 still exposed the expected title, subtitle, author, affiliation, venue, and date text in the PDF text layer.

## Pitfalls and Debugging Notes

### 1) Inverting a title-page background is not just a fill change

If the page surface changes from dark to light, the logo and text treatment must change with it or the cover stops reading correctly.

### 2) Stable runtime assets still matter after a palette change

The earlier trim-artifact fix remains relevant here.
Moving back to a raw large-canvas logo source would have risked reintroducing placement problems.

### 3) Page-image verification is still the acceptance check

A successful compile alone would not have been enough for this task.
The rendered page preview is what confirmed that the white title-page surface and the black UP lockup actually looked correct together.

## Practice Task

Compile the showcase deck and compare page 1 against page 23.

Self-check:

- the title page now reads as a light-surface cover,
- the left accent bar is maroon instead of forest green,
- the UP cover lockup stays readable on white,
- the thank page still keeps its separate repaired dark-surface footer treatment.

## Next 24-72 Hours

1. Review whether the same white-surface title-page treatment should become the long-term default for all public screenshots and README imagery.
2. Decide whether the white and black runtime title-page cover assets should both remain checked in as stable render targets.
3. Remove the generated local preview and build artifacts after review.
