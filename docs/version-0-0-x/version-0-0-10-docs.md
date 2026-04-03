# Version v0.0.10 Documentation

## Title
Added Selectable UP Logotype Variants, Stable Runtime Logo Placement, and the Corrected Official UP Palette for `beamer-up`

## Quick Diagnostic Read

This version is a focused branding/runtime follow-up to the earlier UP-directed styling pass.
It does six concrete things:

- corrects the active UP core palette to the official maroon, forest green, yellow, and spot-black values,
- adds public theme options for English and Filipino UP logotype variants,
- rewires content, title, and thank-you slides so the selected logotype is reused consistently,
- introduces runtime-cropped logo assets so the theme does not depend on oversized transparent source canvases,
- updates public docs so the usage contract matches the current working tree,
- records the temporary image-inspection outputs for later deletion instead of removing them automatically.

## One-Sentence Objective

Make the checked-in UP theme expose selectable UP logotype language variants, use the corrected official UP palette, and provide a more controlled header-branding path without changing the supported public `UP` loader.

## Why This Version Matters

The earlier UP-directed styling milestone already gave `beamer-up` a coherent palette, typography system, and slide-surface treatment.
What was still rough in the working tree was the remaining mismatch between the current docs, the active palette constants, and the newer logo behavior:

- the checked-in color tokens no longer matched the corrected official palette values now required for the project,
- the content-slide branding path was still too tied to earlier one-asset assumptions,
- the new UP logotype variants were not yet exposed as part of the public theme API,
- large transparent logo canvases made header placement fragile,
- the docs no longer matched the actual working tree once the new PNGs and runtime derivatives were introduced.

This version tightens that area specifically.
It does not change the public loader contract, but it does make the current `showlogo` path more expressive and more explicit.

## Plan A / Plan B

### Plan A (Recommended)

1. Read `README.md` for the public usage contract.
2. Open `beamer-up/beamerthemeUU.sty`, `beamer-up/beamerinnerthemeUU.sty`, and `beamer-up/beamerouterthemeUU.sty`.
3. Compile `beamer-up/main.tex`.
4. Inspect a title slide, a content slide with `showlogo`, and the thank-you slide.

### Plan B

1. Read `CHANGELOG.md` first for the short release summary.
2. Open `beamer-up/main.tex` and compare the usage notes against the theme options in `beamerthemeUU.sty`.
3. Use this document as the detailed bridge between the code changes and the root release docs.

## System View

The relevant repo progression now looks like this:

```text
implemented UP-directed slide system
  -> added selectable UP logotype variants
  -> stabilized runtime logo placement with cropped runtime assets
  -> reconciled README, changelog, and version-note docs
  -> next packaging/provenance cleanup work
```

That matters because the logo path is now not only a visual decision.
It is also a runtime-asset and public-usage-contract decision.

## Artifact Map

### Theme implementation surfaces updated in this version

- `beamer-up/beamercolorthemeUU.sty`
- `beamer-up/beamerthemeUU.sty`
- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerouterthemeUU.sty`
- `beamer-up/main.tex`

### Logo assets added or promoted in this version

- `beamer-up/logos/up-logotype-eng-black.png`
- `beamer-up/logos/up-logotype-eng-white.png`
- `beamer-up/logos/up-logotype-tag-black.png`
- `beamer-up/logos/up-logotype-tag-white.png`
- `beamer-up/logos/up-logotype-eng-runtime-black.png`
- `beamer-up/logos/up-logotype-eng-runtime-white.png`
- `beamer-up/logos/up-logotype-tag-runtime-black.png`
- `beamer-up/logos/up-logotype-tag-runtime-white.png`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-10-docs.md`

## Detailed Walkthrough

## 1) The active palette now matches the corrected official UP core values

`beamer-up/beamercolorthemeUU.sty` now uses these palette values directly:

- maroon `#8E1537`
- forest green `#005740`
- yellow `#FFB81D`
- spot black `#231F20`
- white `#FFFFFF`

The implementation now treats `UPYellow` as the canonical accent token.
`UPGold` is still present only as a compatibility alias so the existing theme code keeps compiling while the public naming moves to the corrected palette language.

## 2) The public theme API now includes logotype language selection

The supported public loader is still:

```tex
\usetheme{UP}
```

But the checked-in theme now exposes these additional logo-selection flags:

- `english`
- `filipino`
- `showlogo`
- `nl`

The important part is that the new language flags are additive to the existing public path.
Users do not need a new theme name or a new helper macro just to switch between the two bundled UP wordmark variants.

## 3) Logo behavior is now split into source art vs runtime art

The new source PNGs in `beamer-up/logos/` arrive on very large transparent canvases.
That is acceptable as source artwork, but it makes direct runtime placement brittle when the theme needs the logo near the top-right header zone.

This version therefore introduces runtime-cropped derivatives:

- one black and one white English asset,
- one black and one white Filipino asset.

The engineering tradeoff is straightforward:

- keep the supplied source art intact,
- add deterministic runtime copies for placement-sensitive theme surfaces,
- document the source/runtime split in the root docs and the release note.

## 4) Content, title, and thank-you slides now share the same language selection

The implementation now routes the selected language variant through the theme rather than treating each slide surface independently.

In practice:

- content slides use the light-surface runtime asset,
- title and thank-you slides use the dark-surface runtime asset when available,
- `nl` remains the legacy Dutch compatibility path,
- helper commands such as `\thankframe` keep working under the same public interface.

This matters because the change is structural, not a one-off header hack.
The same language decision now follows the slide surfaces that actually show the mark.

## 5) The root public docs now describe the current runtime honestly

`README.md` now reflects:

- the `v0.0.10` version marker,
- the corrected official palette values and yellow naming,
- the supported `english` and `filipino` options,
- the runtime-cropped logo handling that supports the new placement path.

`CHANGELOG.md` now reflects:

- the corrected official palette values and the `UPYellow` / `UPGold` compatibility story,
- the new public option surface,
- the runtime-cropped logo asset addition,
- the local validation run,
- the temporary inspection outputs that should be deleted after review.

## 6) Local inspection artifacts were recorded, not deleted

During this change, temporary PNG outputs were generated to inspect:

- inherited Utrecht logo renders,
- UP logotype composites on visible backgrounds,
- selected pages from the compiled PDF.

This task does not delete them.
Instead, they are recorded under `CHANGELOG.md` `For Deletion` so the user can remove them deliberately later.

## Compile and Validation Notes

The supported compile path was rerun successfully on April 1, 2026:

```sh
cd beamer-up
latexmk -pdf main.tex
```

Observed caveats from the local validation run:

- MiKTeX emitted non-fatal logging permission warnings for its own log directory,
- `hyperref` emitted the same non-fatal repeated-`pdfauthor` warnings already seen in prior local builds,
- the build still completed successfully and produced the updated `main.pdf`.

## Pitfalls and Debugging Notes

### 1) Source logo files and runtime logo files are not the same thing

If you change only the source `up-logotype-*.png` files, the theme will not automatically pick up a better crop.
The runtime-cropped variants are separate assets in the current working tree.

### 2) `nl` is still a compatibility branch, not the main branding path

The new language-selection work applies to the UP path.
`nl` is retained only as the legacy Dutch compatibility path.

### 3) Inspection PNGs are disposable

The preview and comparison PNGs are not part of the theme contract.
They are temporary review outputs and should not be treated as shipped assets.

## Practice Task

Compile the showcase deck twice:

1. once with `\usetheme[showlogo,english]{UP}`,
2. once with `\usetheme[showlogo,filipino]{UP}`.

Self-check:

- does the selected wordmark change without changing the public loader,
- do title and thank-you slides follow the same language choice,
- do the README usage notes match what you see in the PDF.

## Next 24-72 Hours

1. Decide whether the new UP logotype source assets need further art correction or replacement before release packaging.
2. Clean up the temporary inspection PNGs listed in `CHANGELOG.md` once review is complete.
3. Document provenance and packaging basis for the source and runtime UP logo assets before calling them release-ready.
