# Version v0.0.9 Documentation

## Title
Implemented the UP-Directed Slide System for `beamer-up`

## Quick Diagnostic Read

This version is the implementation pass that follows the earlier visual-direction planning work.
It does four concrete things:

- turns the approved UP palette into the checked-in runtime colour system,
- rewrites the major slide templates to look and behave like the current UP direction,
- updates the bundled showcase deck so it demonstrates the new public reality instead of the older inherited look,
- reconciles the root public docs with the actual implementation and compile state.

## One-Sentence Objective

Ship the approved `U-D` styling adaptation so the public `UP` loader now produces a coherent UP-directed presentation surface rather than only a planned visual direction.

## Why This Version Matters

Before this version, the repository had already solved the public loader problem:
users could load `\usetheme{UP}` and the docs could explain the intended derivative identity.

What was still incomplete was the visual contract.
The repo had a design direction, but the checked-in slide surfaces still carried too much inherited Utrecht-era behavior in the live theme implementation.

This version closes that gap.
The public runtime state now aligns much more closely with what the project claims it is trying to become:

- a UP-directed derivative,
- with a stable public `UP` loader,
- a documented `pdfLaTeX` plus `biber` compile path,
- and a showcase deck that demonstrates the current reality instead of a future plan.

## Plan A / Plan B

### Plan A (Recommended)

1. Read the updated root `README.md`.
2. Read `CHANGELOG.md` for the short release summary.
3. Open `beamer-up/beamercolorthemeUU.sty`, `beamer-up/beamerinnerthemeUU.sty`, `beamer-up/beamerouterthemeUU.sty`, and `beamer-up/beamerthemeUU.sty`.
4. Compile `beamer-up/main.tex` and inspect the resulting PDF.

### Plan B

1. Open `beamer-up/main.tex` first.
2. Compare its old Utrecht-facing examples against the current UP-facing examples and palette names.
3. Use this document as the detailed bridge between the implementation files and the public docs.

## System View

The repo progression now looks like this:

```text
approved derivative governance
  -> approved brownfield understanding
  -> implemented UP public loader
  -> approved UP visual-direction mapping
  -> implemented UP-directed slide system
  -> next showcase/packaging/distribution work
```

That sequence matters because the public runtime identity is now backed by the checked-in templates themselves, not only by planning or governance documents.

## Artifact Map

### Theme implementation surfaces updated in this version

- `beamer-up/beamercolorthemeUU.sty`
- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerouterthemeUU.sty`
- `beamer-up/beamerthemeUU.sty`
- `beamer-up/main.tex`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-9-docs.md`

## Detailed Walkthrough

## 1) The runtime palette is now explicitly UP-directed

The colour theme no longer defines the inherited Utrecht palette as the primary design language.
Instead, it introduces concrete UP-facing tokens:

- `UPMaroon`
- `UPForestGreen`
- `UPGold`
- `UPBlack`
- `UPWhite`

It also adds tint and divider tokens so the visual system has a controlled range for blocks, accents, and supporting surfaces.

The important engineering choice here is that legacy `UU*` names still exist only as compatibility aliases.
That means the implementation can keep older internal references stable while the public-facing palette has already moved forward.

## 2) Typography and code surfaces now match the supported baseline

The theme now standardizes on a simpler and more reproducible font stack:

- Palatino for body reading surfaces,
- Helvetica-style sans for titles, subtitles, frame titles, and footlines,
- the documented baseline remains `pdfLaTeX` plus `biber`.

This is a meaningful improvement because the earlier README still described optional Merriweather/Open Sans behavior that no longer matches the checked-in theme source.

The listings configuration was also updated so:

- keywords use UP maroon,
- strings use UP forest green,
- comments and line numbers use the muted dark token,
- the code background uses a light gold tint.

That keeps code examples inside the same mapped visual system instead of looking like a leftover inherited surface.

## 3) Core slide templates were restyled, not just recolored

The inner and outer themes now do more than change token names.
They change the actual slide composition:

- title slides now use a maroon-led full-surface treatment with green and gold accents,
- section dividers and manual section frames now use the green-plus-gold treatment,
- standout and thank-you frames now use maroon hero surfaces with gold accents,
- the footline and frame-title treatments now carry the updated UP accent structure,
- logo placement is smaller and more controlled on content slides.

This matters because the visual identity shift is now structural.
It is not just a search-and-replace of colours.

## 4) The bundled showcase deck now demonstrates the new public truth

`beamer-up/main.tex` was updated so the demo itself stops teaching the older visual language.

Concrete examples:

- the multi-author example now uses UP campuses and UP-oriented conference wording,
- the palette slide now presents the UP institutional colours instead of the inherited Utrecht set,
- the typography guidance now explains the supported Palatino plus sans hierarchy,
- diagrams, charts, and listings now use the new UP token set directly,
- captions and summary text now describe the current runtime styling accurately.

This is important because the showcase deck is the fastest path most users will take to understand the theme.
If the demo is stale, the implementation feels inconsistent even when the source files are correct.

## 5) The compile path was revalidated against the implemented theme

The supported compile command was rerun successfully on April 1, 2026:

```sh
cd beamer-up
latexmk -pdf main.tex
```

That produced the bundled `main.pdf` successfully with the public `UP` loader.

Observed caveats from the local validation run:

- MiKTeX emitted non-fatal logging permission warnings for its own log directory,
- `hyperref` emitted non-fatal warnings about repeated `pdfauthor` option setting and a token in a PDF string,
- the build still completed successfully and produced the expected PDF output.

## Pitfalls and Debugging Notes

### 1) Seeing `UU` names in the source does not mean the public contract regressed

Many filenames and helper internals still carry legacy `UU` names.
In this milestone, that is a compatibility detail, not a statement that `UU` is the supported public loader.

### 2) Build artifacts are still generated locally

The showcase compile writes generated files like `main.pdf`, `main.log`, and `main.run.xml`.
This task records them in the changelog rather than deleting them automatically.

### 3) The `nl` option is still a compatibility path

The default `showlogo` path now uses UP PNG assets.
The `nl` option remains for legacy Dutch-logo compatibility and should not be treated as the main public branding path.

## Practice Task

Compile the showcase deck, then inspect these three surfaces in the resulting PDF:

1. the single-author title page,
2. the section-divider slide,
3. the thank-you slide.

Self-check:

- Do all three read as part of one visual system?
- Does the deck now look UP-directed rather than Utrecht-directed?
- Do the README usage notes match what you actually see in the PDF?

## Next 24-72 Hours

1. Prepare the `U-E` showcase and packaging evidence for first-release readiness.
2. Expand the demo with more common UP academic presentation scenarios.
3. Reconcile distribution guidance for GitHub and Overleaf with the current implemented styling state.
