# Version v0.0.25 Documentation

## Title
Fixed the Title-Page Inline UP Logo by Switching to Runtime-Cropped Cover Assets Derived from the Requested Files

## Quick Diagnostic Read

This version is a narrow title-page logo-rendering follow-up.
It does four concrete things:

- keeps the rebalanced cover-page text layout from the previous title-slide passes,
- changes the title-page logo slot from direct TeX clipping of the requested inline files to stable runtime-cropped derivatives,
- generalizes the title-page logo sizing hook so the requested cover assets can be sized by height cleanly,
- records the local compile, page-1 PNG render, and page-1/page-2 text-layer verification for the final fix.

## One-Sentence Objective

Make the requested inline English and Filipino UP cover logos render correctly on the title pages without the trim artifact or upside-down spill seen in the broken intermediate state.

## Why This Version Matters

The previous change honored the user's request to use:

- `up-inline-logo-eng-white.png`
- `up-inline-logo-tag-white.png`

on the title pages, but the direct TeX-side clipping path still produced a visibly broken result.

The issue was no longer about choosing the wrong logo family.
It was about how the raw raster assets were being cropped and placed.

The user-provided evidence showed the actual failure mode clearly:

- the logo did not simply look slightly off,
- it produced a visible upside-down spill at the top-right edge of the slide,
- the cover mark was not rendering as a stable bounded title-page element.

This version fixes that by keeping the requested source family but moving the crop step out of the fragile inline-TeX clipping path.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerthemeUU.sty`.
2. Inspect the non-`nl` title-page logo include path.
3. Create stable runtime-cropped derivatives of the requested inline white source files.
4. Wire the title-page include path to those runtime-cropped files.
5. Compile `beamer-up/main.tex`.
6. Export page 1 and inspect the result.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Open the new runtime-cropped logo assets under `beamer-up/logos/`.
3. Compare the fresh page-1 preview against the broken prior render.

## System View

The title-page logo path now looks like this:

```text
requested inline white source files
  -> runtime-cropped stable title-page PNG derivatives
  -> title-page-specific height-based include
  -> generic title-logo size hook
  -> current top-left title-page anchor
  -> clean bounded UP cover mark on page 1 / page 2
```

This matters because the cover-page bug was caused by the rendering path, not by the requested UP logo family itself.

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerthemeUU.sty`

### Runtime assets added in this version

- `beamer-up/logos/up-inline-logo-eng-runtime-white.png`
- `beamer-up/logos/up-inline-logo-tag-runtime-white.png`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-25-docs.md`

### Generated verification outputs recorded in this version

- `beamer-up/main.aux`
- `beamer-up/main.bbl`
- `beamer-up/main.bcf`
- `beamer-up/main.blg`
- `beamer-up/main.fls`
- `beamer-up/main.log`
- `beamer-up/main.nav`
- `beamer-up/main.out`
- `beamer-up/main.pdf`
- `beamer-up/main.run.xml`
- `beamer-up/main.snm`
- `beamer-up/main.toc`
- `beamer-up/main.vrb`
- `beamer-up/titlepage-preview-v2.png`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The requested source files were correct, but the direct clip path was not

The user explicitly asked for the title-page logo to use:

- `up-inline-logo-eng-white.png`
- `up-inline-logo-tag-white.png`

That request was valid.

The failure came from trying to crop those large raster assets directly inside TeX with a title-page include that had to do too much at once:

- clip the raw source,
- size it,
- anchor it,
- and render it safely on the page.

The resulting render proved that this path was not stable enough for the cover-page slot.

## 2) The fix keeps the same source family, but moves to stable runtime assets

This version creates stable runtime-cropped title-page derivatives:

- `up-inline-logo-eng-runtime-white.png`
- `up-inline-logo-tag-runtime-white.png`

These are cropped from the requested source files ahead of time and then treated as the clean runtime assets for the title page.

That gives the title-page include path a much simpler job:

- include the already-bounded image,
- size it,
- place it.

This is the actual fix that removed the artifact.

## 3) The title-page logo sizing hook is now generic

`beamer-up/beamerinnerthemeUU.sty` now uses a generic `\@uutitlelogosize` hook instead of the earlier width-specific title-logo variable.

That matters because the current title-page logo path is now height-based.
The new hook is a better fit for the actual rendering contract:

- the asset path can decide whether height or width is appropriate,
- the title-page template no longer encodes that assumption in the variable name,
- later title-page adjustments can stay localized.

## 4) The cover-page composition stays intact

This follow-up does not undo the earlier title-page rebalance.

It keeps:

- the single left-aligned title-page text block,
- the current title/subtitle/divider/metadata rhythm,
- the existing title-page anchor strategy,
- the separate content-header and closing-slide logo systems.

The only meaningful change in this release is the final repair of how the requested inline title-page logo family is rendered.

## Verification

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdftoppm -png -f 1 -singlefile main.pdf titlepage-preview-v2
pdftotext -f 1 -l 2 main.pdf -
```

Observed result on April 2, 2026:

- the deck compiled successfully,
- the title-page logo used the runtime-cropped inline English/Filipino UP cover assets,
- the page-1 PNG preview no longer showed the upside-down spill artifact,
- pages 1 and 2 still exposed the expected title, subtitle, author, institute, affiliation, venue, and date text in the PDF text layer.

## Pitfalls and Debugging Notes

### 1) Correct source assets can still fail through the wrong rendering path

Using the right UP logo family did not automatically guarantee a correct title-page render.
The crop-and-place path still had to be stable.

### 2) Raster clipping inside TeX can hide rendering issues until the page is actually rendered

The text layer looked fine long before the page-image preview confirmed the logo was truly fixed.

### 3) Page-image verification matters for visual theme work

For slide-theme changes, a successful compile is necessary but not sufficient.
Fresh rendered-page inspection is often the real acceptance check.

## Practice Task

Compile the showcase deck and inspect page 1.

Self-check:

- the title-page logo appears as a bounded top-left mark,
- there is no upside-down spill or trim artifact,
- the title-page text composition remains unchanged,
- the cover page still feels balanced overall.

## Next 24-72 Hours

1. Review the Filipino title-page route to confirm the same clean rendering with the alternate runtime-cropped asset.
2. Decide whether the raw inline white source files should remain as source-only assets and the runtime-cropped versions as the permanent title-page path.
3. Remove the generated local preview and build artifacts after review.
