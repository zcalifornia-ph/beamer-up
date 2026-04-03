# Version v0.0.24 Documentation

## Title
Corrected the UP Cover-Page Logo Path So the Front-Page Lockup No Longer Reads as Squashed

## Quick Diagnostic Read

This version is a narrow title-page logo follow-up.
It does four concrete things:

- keeps the `v0.0.23` cover-page text-layout rebalance,
- replaces the flatter intermediate inline cover mark with the trimmed horizontal white UP lockup on title pages,
- nudges the title-page logo anchor slightly higher,
- records the local compile and text-layer verification for the first two cover pages.

## One-Sentence Objective

Fix the perceived squashed or stretched look of the UP logo on the cover pages without rewriting the title-page composition again.

## Why This Version Matters

The prior title-page harmony pass improved the overall composition, but the visible UP mark still did not look right on the front pages.

The issue was no longer the text stack.
The issue was the specific title-page logo source being used.

The earlier follow-up had switched the cover path to trimmed inline UP assets.
That improved visual weight compared with the original thin standalone wordmark, but in actual front-page use the chosen inline mark still read as too flat.

That produced the effect the user called out:

- the UP logo looked squashed,
- the lockup felt compressed at the top-left corner,
- the front-page identity mark still did not look fully resolved.

This version fixes that by changing only the visible title-page logo source and its immediate placement tuning.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerthemeUU.sty`.
2. Inspect the non-`nl` title-page logo include path.
3. Replace the title-page inline lockup path with the trimmed horizontal white UP lockup.
4. Compile `beamer-up/main.tex`.
5. Inspect pages 1 and 2.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Extract text from pages 1 and 2 of the rebuilt PDF.
3. Compare the current title-page logo path against the previous `v0.0.23` title-page lockup path.

## System View

The title-page logo path now looks like this:

```text
english / filipino option
  -> title-page-specific horizontal white UP lockup
  -> language-specific trim to visible bounds
  -> dedicated title-page width
  -> slightly raised top-left anchor
  -> existing v0.0.23 text-block rebalance remains unchanged
```

This matters because the front-page logo problem turned out to be an asset-fit problem, not a broader layout failure.

## Artifact Map

### Implementation surface updated in this version

- `beamer-up/beamerthemeUU.sty`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-24-docs.md`

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

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The front-page problem narrowed to the cover-logo source

`v0.0.23` already fixed the broader composition issue by:

- reshaping the title-page copy into one left-aligned block,
- improving the overall relationship between the logo and the text stack.

That part was not the problem anymore.

The remaining defect was perceptual:
the selected title-page logo still looked flattened on the actual page.

So this version intentionally does not revisit the text stack.
It narrows the change to the visible logo path only.

## 2) The title page now uses the horizontal white UP lockup

This version changes the non-`nl` title-page include macros in `beamer-up/beamerthemeUU.sty` from the intermediate inline cover-mark path to:

- `up-horizontal-logo-with-white-engtype.png`
- `up-horizontal-logo-with-white-tagtype.png`

with the same language-sensitive selection rule:

- `english` -> English lockup,
- `filipino` -> Filipino lockup,
- `nl` -> legacy Dutch-logo compatibility path.

The include path also applies the same language-specific trims already used to keep those horizontal white assets visually bounded.

That change removes the flatter title-page look without disturbing the text layout introduced in the previous version.

## 3) The logo size and anchor were tuned with the asset swap

Changing the source asset alone is not enough.

Because the horizontal white lockup has a different visible proportion than the inline mark, this version also updates:

- the title-page logo width,
- the title-page top-left y-offset.

That keeps the corrected mark visually balanced inside the same cover-page structure instead of dropping a different asset into the old anchor unchanged.

## 4) The rest of the logo system stays isolated

This follow-up does not rewrite the other UP logo surfaces.

Specifically unchanged:

- the content-slide header lockup path,
- the title-page text-block structure added in `v0.0.23`,
- the repaired `\thankframe` layout,
- the lowered thank-page footer position,
- bibliography behavior and source selection.

That isolation matters because the reported issue was specifically the cover-page logo appearance.

## Verification

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdftotext -f 1 -l 2 main.pdf -
```

Observed result on April 2, 2026:

- the deck compiled successfully,
- the cover pages used the horizontal white UP title-page lockup path,
- page 1 still exposed the title, subtitle, author, institute, and date,
- page 2 still exposed the multi-author and conference metadata,
- the logo-path correction remained isolated to the title-page mark.

## Pitfalls and Debugging Notes

### 1) A stronger asset can still be the wrong asset

The previous inline title-page mark had more presence than the original thin standalone wordmark, but it still did not fit the cover slot correctly.

### 2) Perceived distortion can be an aspect-ratio choice problem

Even when TeX preserves the literal image dimensions, a mark can still look stretched or squashed if its visible proportion is a poor fit for the slot.

### 3) Small anchor moves matter on sparse cover pages

On a page with only a logo, title block, and metadata, minor shifts in the title-page mark are very noticeable.

## Practice Task

Compile the showcase deck and inspect pages 1 and 2.

Self-check:

- the UP cover mark no longer looks visually flattened,
- the title-page logo feels proportionate to the title block,
- the single-author and multi-author covers still read cleanly,
- the change does not spill into the content-slide header or the thank page.

## Next 24-72 Hours

1. Review the Filipino cover-page route to confirm the same improvement with the alternate horizontal white lockup.
2. Decide whether the inline cover-mark path should remain available only as a future experiment rather than the active title-page path.
3. Remove the generated local build artifacts after review.
