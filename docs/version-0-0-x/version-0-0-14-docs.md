# Version v0.0.14 Documentation

## Title
Restored the Exact Horizontal White UP Footer Logos on the Closing Slide Without Cropping Them Out

## Quick Diagnostic Read

This version is a narrow closing-slide follow-up to the earlier `\thankframe` work.
It does four concrete things:

- keeps the beamer-uu-style closing-slide layout introduced earlier,
- switches the non-`nl` footer back to the exact horizontal white English and Filipino UP files the user explicitly requested,
- replaces the earlier too-tight crop box with a safer footer crop and smaller rendered height so the visible logo no longer drops off the bottom edge,
- records the local page-render verification output instead of deleting it automatically.

## One-Sentence Objective

Use the exact horizontal white UP footer-logo files on the closing slide while ensuring the full visible mark stays inside the page.

## Why This Version Matters

The previous closing-slide work got the overall layout and language-switch behavior back into the right shape, but the logo rendering still had one important defect:

- the slide was no longer clipping because of layout alone,
- it was clipping because the chosen horizontal PNGs were being included with an overly aggressive crop box and a size that pushed the visible mark too close to the bottom edge.

That meant the implementation was technically using the requested UP footer assets, but not rendering them in a way that preserved the full mark.

This version fixes that specific problem and nothing broader.
It keeps the same helper macro, the same language-switch API, and the same overall closing-slide layout.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerouterthemeUU.sty`.
2. Find the `\@upclosinglogoenginclude`, `\@upclosinglogotaginclude`, and `\@upclosinglogoinclude` helpers.
3. Compile `beamer-up/main.tex`.
4. Inspect the closing `Feedback?` slide footer logo.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Render the closing slide to PNG.
3. Compare the visible footer logo against the earlier clipped result.

## System View

The relevant progression now looks like this:

```text
restored beamer-uu-style UP closing slide
  -> switched footer to requested horizontal white UP assets
  -> discovered footer cropping was still too tight
  -> widened the crop and reduced rendered height
  -> kept the exact English/Filipino asset selection rule
```

This matters because the user requirement here was not just “show a UP logo.”
It was “use these exact two files depending on the selected language and make them render fully.”

## Artifact Map

### Theme implementation surface updated in this version

- `beamer-up/beamerouterthemeUU.sty`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-14-docs.md`

### Temporary verification output recorded in this version

- `beamer-up/preview-page-23-horizontal-23.png`

## Detailed Walkthrough

## 1) The closing slide now uses the exact requested horizontal white UP files

The non-`nl` closing-slide footer path now points directly to:

- `beamer-up/logos/up-horizontal-logo-with-white-engtype.png`
- `beamer-up/logos/up-horizontal-logo-with-white-tagtype.png`

The selection rule stays the same:

- `english` selects the English file,
- `filipino` selects the Filipino file,
- `nl` remains on its compatibility fallback path.

This version does not replace those files with a composed seal-plus-wordmark fallback.
It uses the exact assets named in the task request.

## 2) The earlier trim box was too aggressive

Those horizontal PNGs sit on large transparent canvases.
That makes them awkward to place directly in a footer area.

The earlier attempt trimmed too tightly and then scaled by width, which caused the visible mark to land too low and appear cut off at the bottom of the slide.

This version fixes that by:

- widening the retained vertical band,
- leaving the horizontal crop open,
- switching to a smaller `height`-based include instead of a larger width-based include.

That combination keeps the actual visible logo intact while still ignoring most of the transparent padding.

## 3) The layout stays the same; only the footer asset handling changed

The closing slide still uses the same overall structure introduced in the prior version:

- title near the top,
- rule below the title,
- contribution block below the rule,
- footer logo centered near the bottom.

What changed is only the way the chosen horizontal UP asset is cropped and scaled before it is placed into that footer slot.

## 4) Validation was done at the closing-slide surface itself

This fix is a rendering correction, so compile success alone is not enough.

The local validation for this version used:

```sh
cd beamer-up
pdflatex main.tex
```

Then the closing slide was rendered to a PNG preview so the footer mark could be checked directly against the bottom edge of the page.

That inspection confirmed the visible logo now stays within the footer area while still using the exact requested UP horizontal asset.

## Compile and Validation Notes

Observed results from the local validation run on April 2, 2026:

- `pdflatex main.tex` completed successfully,
- the log confirms the English showcase path loads `up-horizontal-logo-with-white-engtype.png` on the closing slide,
- the rendered preview `beamer-up/preview-page-23-horizontal-23.png` was generated to inspect the footer fit,
- the usual non-fatal MiKTeX log-permission noise remains outside the repo-controlled files.

## Pitfalls and Debugging Notes

### 1) Exact source-asset usage and correct footer fit are separate problems

It is possible to satisfy one and fail the other.
Using the exact requested file does not automatically mean the visible logo will fit the footer correctly.

### 2) Transparent canvases distort intuition

These UP horizontal PNGs have large transparent borders.
If you scale them as if the visible mark filled the whole image, the rendered footer result will be wrong.

### 3) Width-based sizing is riskier here than height-based sizing

For this footer slot, a width-based include made the visible logo too dominant vertically once the crop box was tightened.
Reducing the rendered height is the safer control for keeping the mark inside the page.

## Practice Task

Compile the showcase deck twice:

1. once with `\usetheme[english]{UP}`,
2. once with `\usetheme[filipino]{UP}`.

Self-check:

- does the closing slide use the exact requested horizontal white file for each language,
- does the visible logo remain above the page bottom,
- does the `nl` path remain untouched.

## Next 24-72 Hours

1. Do a dedicated Filipino closing-slide render so the `up-horizontal-logo-with-white-tagtype.png` footer fit is visually confirmed, not only code-routed.
2. Decide whether these large horizontal source files should eventually gain dedicated runtime-cropped variants for footer use.
3. Remove the temporary preview render after review.
