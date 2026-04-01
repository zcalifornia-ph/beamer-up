# Changelog

Status: independently maintained derivative work with approved brownfield baselines, an implemented public `UP` entry path, and a drafted guide-backed `U-D` visual-direction baseline pending review before template restyling.

## Unreleased

### Added or Changed
- None yet.

### For Deletion
- None yet beyond items already recorded in the latest released entry.

## v0.0.8

### Added or Changed
- Drafted the `U-D` visual-direction baseline for `beamer-up`, including a concrete UP palette, typography hierarchy, logo strategy, and decorative-rule set for title, section, content, standout, and closing-slide surfaces.
- Recorded contrast and readability guidance for the mapped visual system, including the explicit rejection of white-on-gold text and the approval of high-contrast maroon, forest-green, gold, and dark-text pairings.
- Updated `README.md` to move the public project state to `v0.0.8`, document that the visual-system mapping is drafted, and position the next bolt as template styling rather than interface migration.
- Added `docs/version-0-0-8-docs.md` as the public narrative note for this visual-direction planning milestone.

### For Deletion
- `beamer-up/main.bcf` (generated bibliography control file from local showcase compilation).
- `beamer-up/main.fls` (generated `latexmk` file list from local showcase compilation).
- `beamer-up/main.log` (generated TeX log from local showcase compilation).
- `beamer-up/main.pdf` (generated showcase PDF build artifact).
- `beamer-up/main.run.xml` (generated bibliography/runtime metadata artifact).
- `beamer-up/main.synctex.gz` (generated editor sync artifact).
- `beamer-up/main.toc` (generated table-of-contents artifact).
- `beamer-up/main.vrb` (generated Beamer verbatim cache artifact).
- `beamer-up/logos/UU_logo_EN_BLACK-eps-converted-to.pdf` (generated EPS-conversion artifact from local compile flow).
- `beamer-up/logos/UU_logo_EN_RGB-eps-converted-to.pdf` (generated EPS-conversion artifact from local compile flow).

## v0.0.7

### Added or Changed
- Implemented and approved the public `UP` theme interface so the checked-in demo and public usage guidance now load through `\usetheme{UP}`.
- Added `beamer-up/beamerthemeUP.sty` as the canonical public loader and updated `beamer-up/beamerthemeUU.sty` to treat direct `UU` loading as deprecated compatibility with warning guidance.
- Updated the bundled showcase deck in `beamer-up/main.tex` to exercise the supported `UP` path, refresh usage messaging, and point users to the current repository instead of the upstream Utrecht project.
- Reconciled `README.md`, `CHANGELOG.md`, and `CONTRIBUTING.md` so the public docs now describe `U-C` as complete and position `U-D` visual adaptation as the next major workstream.
- Added `docs/version-0-0-7-docs.md` as the public milestone note for the implemented `UP` interface release.

### For Deletion
- None from this task context.

## v0.0.6

### Added or Changed
- Approved the brownfield dynamic compile and usage baseline so downstream migration work can depend on one canonical runtime model.
- Drafted the public `UP` entry-point migration policy: `UP` becomes the canonical loader, helper commands and options stay stable, and any remaining `UU` loader behavior is treated as deprecated compatibility rather than a coequal public contract.
- Updated the root `README.md` from stale unrelated project content to the current `beamer-up` public state, including the approved brownfield baseline, the drafted `UP` migration plan, and the next implementation milestone.
- Added `docs/version-0-0-6-docs.md` as the public narrative note for this planning-and-docs milestone.

### For Deletion
- `test.tmp` (temporary scratch file created during local editing workaround and not part of the project).

## v0.0.5

### Added or Changed
- Approved the brownfield dynamic compile and usage baseline for the inherited theme and recorded that the current bundled demo still compiles successfully through the legacy `UU` interface.
- Reconciled public root docs so they reflect the approved governance plus brownfield baseline without naming maintainer-only workflow artifacts or ignored internal paths.
- Updated `README.md` to move the public docs to `v0.0.5`, mark the brownfield baseline as approved, and position the public `UP` interface migration as the next major milestone.
- Updated `CONTRIBUTING.md` to replace maintainer-only path references with public contribution expectations around attribution, branding, assets, and release notes.
- Added `docs/version-0-0-5-docs.md` as the public narrative note for this documentation reconciliation milestone.

### For Deletion
- None new from this task context beyond generated local build artifacts already recorded in earlier entries.

## v0.0.4

### Added or Changed
- Recorded final approval of the governance baseline and formalized the brownfield static theme model as a maintained migration baseline.
- Added build-task-grade design, ADR, and traceability support around the static model so later interface work could depend on one canonical structural source.
- Updated public docs to reflect the fully approved governance baseline and the then-open brownfield static-model review gate.
- Added `docs/version-0-0-4-docs.md` for the public milestone note.

### For Deletion
- None new from this task context beyond generated local build artifacts already recorded in earlier entries.

## v0.0.3

### Added or Changed
- Added the asset-governance baseline for current logo and package-surface decisions.
- Classified the current logo set by runtime source, generated output, and candidate future asset status.
- Closed the earlier naming and disclaimer review gate and updated public docs to reflect the remaining asset-governance review.
- Added `docs/version-0-0-3-docs.md` for the public milestone note.

### For Deletion
- None new from this task context beyond generated local build artifacts already recorded in earlier entries.

## v0.0.2

### Added or Changed
- Completed brownfield reverse-engineering artifacts for the inherited theme implementation and established the first naming, attribution, and disclaimer baseline for the derivative.
- Updated root docs and contributor guidance so the repository described the brownfield migration posture and approved `UP` naming contract more accurately.
- Added `docs/version-0-0-2-docs.md` for the public milestone note.

### For Deletion
- Generated LaTeX showcase build artifacts and EPS-conversion outputs from local compilation were recorded for later cleanup rather than deleted in place.

## v0.0.1

### Added or Changed
- Initialized `README.md` with project identity, derivative attribution, setup steps, usage notes, roadmap, and maintainer links.
- Initialized `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, and `SECURITY.md` with project-specific governance and reporting details.
- Added conservative ignore rules for local workspace files and generated LaTeX build artifacts for the bundled showcase deck.

### For Deletion
- None from this task context. Existing generated artifacts remain in place for user review because initialization does not delete files.
