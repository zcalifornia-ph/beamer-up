# Version v0.0.12 Documentation

## Title
Rebuilt the UP Content-Slide Header as a Seal-Plus-Logotype Lockup in `beamer-up`

## Quick Diagnostic Read

This version is a focused follow-up to the earlier UP header-alignment pass.
It does five concrete things:

- replaces the standalone non-`nl` UP content-slide wordmark with a real seal-plus-logotype header lockup,
- scales the lineshot seal and lockup spacing so the composed mark stays inside the header band,
- assigns separate English and Filipino wordmark widths so both variants read at a consistent apparent text height,
- leaves the legacy `nl` Utrecht corner-logo path unchanged,
- records the extra local inspection previews for later deletion instead of removing them automatically.

## One-Sentence Objective

Make the UP content-slide header behave like a compact branded lockup that follows the UP spec more closely while still fitting the Beamer header band cleanly.

## Why This Version Matters

The previous alignment work corrected where the UP header wordmark ended.
It did not yet solve what the header actually was.

That left three visible problems:

- the non-`nl` UP path still rendered only the wordmark rather than a seal-plus-logotype lockup,
- the first seal-and-wordmark attempt was too tall for the header band and visually collided with the gold rule,
- the English and Filipino wordmarks did not read at the same apparent size when paired against the same seal.

This version addresses those constraints directly.
It keeps the same public `UP` loader and option names, but it changes the content-slide branding surface to behave more like a compact institutional lockup instead of a long corner label.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerouterthemeUU.sty`.
2. Find the non-`nl` `showlogo` branch in the footline overlay.
3. Compile `beamer-up/main.tex`.
4. Inspect the top-right header on the outline slide and a normal content slide.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Open the high-resolution cropped header previews recorded for this version.
3. Compare the resulting lockup against the UP spec image and the old Utrecht corner-lockup behavior.

## System View

The relevant progression now looks like this:

```text
added selectable UP logotype variants
  -> aligned the UP header wordmark to the content margin
  -> rebuilt the content-slide header as a seal-plus-logotype lockup
  -> tuned seal scale and language-specific wordmark widths
  -> next packaging and provenance cleanup work
```

This matters because the current issue was no longer just placement.
It was the relationship between seal, wordmark, spacing, and the fixed vertical budget of the header band.

## Artifact Map

### Theme implementation surface updated in this version

- `beamer-up/beamerouterthemeUU.sty`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-12-docs.md`

### Temporary inspection outputs recorded in this version

- `beamer-up/logos/up-logo-lineshot-on-white-preview.png`
- `beamer-up/logos/up-logotype-eng-black-on-white-preview.png`
- `beamer-up/logos/up-logotype-tag-black-on-white-preview.png`
- `beamer-up/preview-page-3-hi.png`
- `beamer-up/preview-page-3-hi-topright.png`
- `beamer-up/preview-page-6-hi.png`
- `beamer-up/preview-page-6-hi-topright.png`

## Detailed Walkthrough

## 1) The content-slide UP path now composes a real lockup

The non-`nl` content-slide logo path no longer drops in only the selected wordmark.
Instead, it now composes:

- the UP lineshot seal on the left,
- the selected English or Filipino UP wordmark on the right,
- a fixed gap between them inside one compact TikZ lockup.

This makes the UP header behave more like the institutional lockup shown in the branding specification rather than a free-floating text mark.

## 2) The lockup now respects the header-band height

The first composed attempt was visibly too tall.
The seal dipped into the rule area and the overall result felt oversized relative to the Utrecht header reference.

This version scales the lineshot seal down and adjusts the lockup anchor so the whole mark stays inside the available header band instead of spilling downward.

That change is small in code but important in the rendered slide.

## 3) English and Filipino now use different header widths deliberately

The English and Filipino wordmarks have different lengths and letter shapes.
Using one shared width made one variant look too large or the other too small relative to the seal.

So the header now uses:

- one width for English,
- a separate width for Filipino,
- the same seal size and spacing rule for both.

The goal is not identical total lockup width.
The goal is consistent apparent text height next to the seal while still fitting the header band.

## 4) The Dutch compatibility path remains separate

The `nl` branch still uses the inherited Dutch corner-logo behavior.
It was not converted into the new UP seal-plus-logotype composition.

That preserves legacy compatibility and keeps the new lockup logic scoped to the public UP path only.

## 5) Validation required high-resolution inspection

This change could not be judged reliably from compilation alone.
The deck was rebuilt locally and then rendered again at higher resolution so the top-right header could be inspected directly.

That inspection confirmed:

- the seal is present and legible,
- the lockup stays inside the header band,
- the English header reads as a compact seal-plus-wordmark composition rather than a standalone line of text.

## Compile and Validation Notes

The affected showcase deck was rebuilt locally on April 1, 2026 with:

```sh
cd beamer-up
latexmk -pdf main.tex
```

Observed results from the validation run:

- `main.pdf` was produced successfully after the lockup composition change,
- the higher-resolution local header crops show the seal-plus-logotype composition on the affected content slides,
- the non-fatal MiKTeX log-permission warnings remain,
- the existing `hyperref` warnings and the underfull box in the options example remain.

These warnings predate this lockup refinement and were not introduced by the new composition rule.

## Pitfalls and Debugging Notes

### 1) Header fit is constrained by height more than width

The content-slide header has very little vertical budget.
A lockup that looks reasonable at source-image size can still be wrong once it is placed against the rule and the page top.

### 2) One shared wordmark width is not enough for both languages

English and Filipino do not scale into the same apparent size when placed beside the same seal with the same width parameter.
Treat them as separate header-fit cases.

### 3) `nl` should remain a separate compatibility path

The Dutch logo is still a legacy compatibility surface.
It should not be used as the source of truth for UP seal-to-wordmark proportions.

### 4) Inspection PNGs are disposable

The white-background asset previews and high-resolution page crops are only local review outputs.
They are recorded under `CHANGELOG.md` `For Deletion` and should not be treated as shipped theme assets.

## Practice Task

Compile the showcase deck and inspect:

1. the outline slide,
2. the `Theme Options at a Glance` slide.

Self-check:

- does the content-slide UP header now include the lineshot seal,
- does the full lockup stay above the gold rule,
- does the English or Filipino text read proportionally against the smaller seal,
- does the `nl` path remain unchanged.

## Next 24-72 Hours

1. Verify the Filipino header lockup visually with a dedicated rendered crop, not only the English default deck.
2. Remove the temporary preview images after review.
3. Continue packaging and provenance cleanup once the UP content-slide header lockup is considered visually final.
