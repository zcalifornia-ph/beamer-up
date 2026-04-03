# Version v0.0.11 Documentation

## Title
Aligned the UP Content-Slide Logotype to the Right Content Margin in `beamer-up`

## Quick Diagnostic Read

This version is a narrow follow-up to the earlier UP logotype rollout.
It does four concrete things:

- moves the English and Filipino UP content-slide wordmark off the raw page edge and onto the right content margin,
- keeps the legacy `nl` logo path unchanged so Dutch compatibility does not move unexpectedly,
- revalidates the affected showcase slides after the placement change,
- records the new local page-render inspection PNGs for later deletion instead of removing them automatically.

## One-Sentence Objective

Make the visible right edge of the UP content-slide logotype line up with the same right margin used by the slide content blocks.

## Why This Version Matters

The previous logotype work already introduced selectable English and Filipino UP wordmarks and runtime-cropped assets.
What still felt off in the working tree was the final placement on normal content slides:

- the UP wordmark was still anchored from a page-edge offset rather than the actual Beamer content margin,
- this made the right edge drift slightly beyond the visual boundary suggested by the usage-rule and conference-title blocks,
- the behavior difference was subtle but obvious once the longer UP wordmarks replaced the compact Utrecht corner logo.

This version fixes that specific mismatch without changing the public `UP` loader, the selected logotype assets, or the legacy `nl` compatibility behavior.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerouterthemeUU.sty`.
2. Find the `showlogo` overlay node in the footline template.
3. Compile `beamer-up/main.tex`.
4. Inspect a content slide that shows the top-right UP wordmark.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Open the rendered page image used for inspection.
3. Compare the right edge of the wordmark against the right edge of the content blocks on the same slide.

## System View

The relevant progression now looks like this:

```text
added selectable UP logotype variants
  -> introduced runtime-cropped logo assets
  -> corrected official UP palette
  -> aligned content-slide wordmark to the right content margin
  -> next packaging and provenance cleanup work
```

This matters because the remaining issue was no longer asset selection.
It was the relationship between the overlay anchor and the actual slide content grid.

## Artifact Map

### Theme implementation surface updated in this version

- `beamer-up/beamerouterthemeUU.sty`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-11-docs.md`

### Temporary inspection outputs recorded in this version

- `beamer-up/preview-page-4.png`
- `beamer-up/preview-page-5.png`
- `beamer-up/preview-page-6.png`
- `beamer-up/preview-page-7.png`

## Detailed Walkthrough

## 1) The content-slide UP wordmark now follows the content grid

The old UP content-slide path still used a hard-coded offset from `current page.north east`.
That was acceptable for the inherited Utrecht corner logo, but the wider UP wordmarks made the mismatch visible.

This version changes the non-`nl` placement path so the overlay is anchored from Beamer's right content margin instead of the raw page edge.

In practice, that means:

- English `University of the Philippines` now stops at the same right visual boundary as the content blocks,
- Filipino `Unibersidad ng Pilipinas` inherits the same alignment rule,
- the position now tracks the actual content geometry rather than a guessed corner offset.

## 2) The Dutch compatibility logo is intentionally excluded from the new rule

The `nl` branch still uses the smaller inherited Dutch corner logo.
That asset has a different size, footprint, and compatibility purpose.

So this version keeps `nl` at its previous page-corner offset instead of forcing it into the UP wordmark alignment rule.

That prevents a regression in the legacy path while fixing the modern public UP path.

## 3) The change is small in code but specific in effect

Only the overlay logic in `beamer-up/beamerouterthemeUU.sty` changed.
No new public options were introduced.
No logotype files changed.
No title-slide or thank-you-slide logo logic changed.

This is a targeted placement correction for normal content slides only.

## 4) Local validation included render inspection, not just compilation

The affected showcase deck was rebuilt locally on April 1, 2026 with:

```sh
cd beamer-up
latexmk -pdf main.tex
```

The relevant pages were then rendered locally to PNG so the visible right edge of the UP wordmark could be compared against the content-block margin directly.

That extra check matters because this was a visual alignment fix, not only a compile-safety change.

## Compile and Validation Notes

Observed results from the local validation run:

- `main.pdf` was produced successfully after the alignment change,
- the rendered content slide shows the UP wordmark ending at the same right boundary as the right-side block,
- the non-fatal MiKTeX log-permission warnings remain,
- the existing `hyperref` warnings and the underfull box in the options example remain.

These warnings predate this alignment fix and were not introduced by the new placement rule.

## Pitfalls and Debugging Notes

### 1) Margin alignment is different from page-edge alignment

If a future tweak reverts the anchor back to a page-edge offset, the wider UP wordmarks will drift out of alignment again even though the logo still appears "close" to the corner.

### 2) `nl` should not be used as the reference for UP wordmark placement

The Dutch compatibility logo is intentionally smaller and still corner-based.
It is not the target geometry for the UP public path.

### 3) Inspection PNGs are disposable

The preview renders are only local comparison outputs.
They are recorded under `CHANGELOG.md` `For Deletion` and should not be treated as shipped assets.

## Practice Task

Compile the showcase deck and inspect the slide that says `Theme Options at a Glance`.

Self-check:

- does the UP wordmark end at the same right boundary as the `Conference Title` block,
- does the `nl` path remain visually separate from the new UP alignment rule,
- do the root docs describe the alignment behavior accurately.

## Next 24-72 Hours

1. Confirm the Filipino runtime asset looks equally balanced on the same content-slide geometry.
2. Remove the temporary preview renders after review.
3. Continue packaging and provenance cleanup now that the public UP wordmark placement is visually consistent.
