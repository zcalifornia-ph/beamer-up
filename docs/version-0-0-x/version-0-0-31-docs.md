# Version v0.0.31 Documentation

## Title
Switched the Content-Frame Header to Canonical Lineshot Lockups and Rebalanced Its Header Spacing

## Quick Diagnostic Read

This version is a narrow content-frame header follow-up.
It does four concrete things:

- replaces the old composed content-frame header lockup with runtime-cropped assets derived from the canonical prebuilt English and Filipino lineshot files,
- adds those runtime-cropped header assets under `beamer-up/logos/`,
- reduces the rendered lockup size and lowers it slightly so it sits more comfortably between the top edge and the green rule,
- advances the public root docs to `v0.0.31` so they describe the current checked-in header behavior accurately.

## One-Sentence Objective

Make the non-`nl` content-frame UP header feel closer to the inherited Utrecht header rhythm by using the canonical prebuilt lineshot-with-logotype artwork and giving the visible lockup more breathing room inside the header band.

## Why This Version Matters

The earlier UP content-slide header work already established the right basic direction:

- a visible UP mark on content frames,
- English and Filipino language variants,
- right-margin alignment within the header band.

What remained was quality and proportion:

- the header was still being composed from a separate lineshot seal plus wordmark at render time,
- the visible lockup sat too large in the strip,
- the top and bottom padding around the mark felt tighter than the inherited Utrecht reference.

This version matters because it narrows the content-frame header to the requested canonical art path and then tunes the visible spacing instead of leaving the UP lockup visually overpacked in the band.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerouterthemeUU.sty`.
2. Replace the composed content-frame header path with direct English and Filipino runtime-asset includes.
3. Generate stable runtime-cropped header assets from the canonical `up-inline-lineshot-*-black.png` source files.
4. Retune the header widths and vertical anchor in the non-`nl` branch.
5. Compile `beamer-up/main.tex` with `pdflatex`.
6. Inspect the outline-slide header render.

### Plan B

1. Compare the current `beamerouterthemeUU.sty` diff against the prior composed header path.
2. Confirm that the title-page and closing-slide logo paths were left alone.
3. Confirm that the only new tracked assets are the two runtime-cropped content-frame header files.

## System View

```text
content frame
  -> showlogo
  -> language branch (english / filipino)
  -> runtime-cropped header asset include
  -> smaller width + slightly lower anchor
  -> more even breathing room inside the header band
```

The key point is that the header now uses one stable prebuilt lockup per language instead of assembling the lineshot seal and wordmark live inside TeX.

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/beamerouterthemeUU.sty`
- `beamer-up/logos/up-inline-lineshot-eng-runtime-black.png`
- `beamer-up/logos/up-inline-lineshot-tag-runtime-black.png`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-31-docs.md`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The content-frame header no longer composes the mark from separate pieces

The old non-`nl` header path in `beamerouterthemeUU.sty` built the content-frame mark from:

- a standalone lineshot seal image,
- a separately placed English or Filipino wordmark,
- a small hand-tuned horizontal offset inside a TikZ picture.

This version removes that composition path for content frames.

Instead, the English and Filipino header branches now include:

- `up-inline-lineshot-eng-runtime-black.png`,
- `up-inline-lineshot-tag-runtime-black.png`.

Those assets are derived directly from the canonical requested prebuilt lineshot source files, so the visible header lockup now comes from one stable artwork path per language.

## 2) Stable runtime-cropped header assets were added on purpose

The canonical source files are the right visual source, but they still carry a large transparent canvas.

For the content-frame header, that matters because the available band is short and the lockup has to fit predictably.

This version therefore adds stable runtime-cropped derivatives:

- `beamer-up/logos/up-inline-lineshot-eng-runtime-black.png`,
- `beamer-up/logos/up-inline-lineshot-tag-runtime-black.png`.

That mirrors the same pragmatic pattern already used elsewhere in the theme for title-page assets:

- preserve the canonical requested source art,
- derive stable cropped runtime assets for deterministic placement inside TeX.

## 3) The header was then resized and lowered for better breathing room

After switching to the stable runtime assets, the next issue was vertical density.

The requested target was closer to the Utrecht reference:

- smaller visible mark,
- clearer breathing room above,
- clearer breathing room above the green rule.

The non-`nl` content-frame anchor therefore now uses:

- `3.85cm` width for the English header lockup,
- `3.45cm` width for the Filipino header lockup,
- `yshift=-0.15cm` instead of the tighter earlier placement.

That combination keeps the lockup aligned to the right content margin while reducing the sense that it fills the whole header strip.

## 4) Title-page and closing-slide logo behavior were intentionally left unchanged

This version is deliberately narrow.

It does not reopen:

- the light-surface title-page logo path,
- the content-page `nl` compatibility branch,
- the closing-slide horizontal white lockups,
- the current bibliography baseline from `v0.0.30`.

That keeps the release note set honest and the implementation surface bounded to the actual diff.

## Validation

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
```

Observed result on April 3, 2026:

- the showcase deck compiled successfully on the supported `pdfLaTeX` path,
- the outline slide rendered the English header through `up-inline-lineshot-eng-runtime-black.png`,
- the visible lockup remained aligned to the right content margin,
- the rendered mark sat smaller and more comfortably inside the header band than before.

The follow-up render inspection of the outline slide confirmed that the visible header lockup no longer crowds the strip.
The existing bibliography warnings remain outside the scope of this narrow header-layout follow-up because `biber` was not rerun here.

## Pitfalls and Debugging Notes

### 1) Canonical source art is not always placement-ready art

Even when the requested logo file is visually correct, large transparent margins can make direct placement unreliable inside a short header band.
Stable runtime-cropped derivatives are the safer path when deterministic layout matters.

### 2) A correct lockup can still feel visually wrong if the header band is too dense

This change was not only about which file renders.
It was also about perceived spacing.
The lockup needed to shrink and shift slightly lower to feel closer to the inherited Utrecht breathing room.

### 3) Keep the scope bounded to one surface

The content-frame header, title page, and closing slide each have different logo constraints.
Treating them as one shared tuning problem would have created unnecessary regressions.

## Practice Task

Compile the showcase deck and inspect the outline slide header.

Self-check:

- the header uses the prebuilt English lineshot lockup,
- the mark is smaller than the previous crowded version,
- there is visible space above the logo and above the green rule,
- the right edge still aligns with the content block margin.

## Next 24-72 Hours

1. Verify the Filipino content-frame header path visually with the same spacing target.
2. Decide whether the current header widths are final or should be tuned one more step against the Utrecht reference.
3. Continue release-packaging cleanup once the current content-frame header baseline is accepted.
