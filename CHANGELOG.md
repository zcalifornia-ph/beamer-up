# Changelog

Status: current approved public documentation baseline `v0.3.2`; the supported public loader is `UP`, the checked-in starter-template and usage guide define the published baseline, earlier `0.0.x` to `0.2.x` narratives are grouped into archive folders under `docs/`, and `docs/release-readiness.md` records the still-human-gated evidence handoff for `B-UE-02`.

## v0.3.2

### Added or Changed
- Bumped the root public documentation baseline from `v0.3.0` to `v0.3.2` for a docs-only archive-reorganization release.
- Reorganized the historical public version trail so the `v0.0.x`, `v0.1.x`, and `v0.2.x` narratives now live under `docs/version-0-0-x/`, `docs/version-0-1-x/`, and `docs/version-0-2-x/` instead of crowding the root `docs/` directory.
- Kept the active `v0.3.x` docs at the root of `docs/`, including the current baseline narrative, the `v0.3.0` reconciliation follow-up, the pending `v0.3.1` readiness narrative, and the new `docs/version-0-3-2-docs.md` archive-reorganization note.
- Updated `README.md` and `SECURITY.md` so the public repo layout and supported-version matrix match the reorganized version-doc trail.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace, including `main.*`, `cover-check.*`, sync data, and related compile byproducts, remained cleanup candidates before release packaging.

## v0.3.0 Reconciliation Follow-Up

### Added or Changed
- Normalized the root public documentation version markers back to `v0.3.0` so the published baseline matches the approved requirements state while `B-UE-02` remains awaiting human approval.
- Kept `docs/release-readiness.md` as the tracked compile, screenshot, packaging, and human-review handoff artifact for Unit `U-E` / Bolt `B-UE-02` without treating it as a published `v0.3.1` baseline.
- Kept `repo/images/project_screen.png` and the aligned README or usage wording as current supporting evidence for the pending readiness review rather than as a separate approved public release.
- Left `docs/version-0-3-1-docs.md` in the public version trail as a pending follow-up narrative for the readiness pass rather than as the current approved baseline.
- Added `docs/version-0-3-0-reconciliation-docs.md` to explain the `v0.3.0` baseline normalization and the pending status of the release-readiness follow-up materials.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace remained cleanup candidates before release packaging.

## v0.3.0

### Added or Changed
- Bumped the root public documentation baseline from `v0.2.0` to `v0.3.0`.
- Expanded `beamer-up/main.tex` from a showcase-only deck into the checked-in starter template for thesis defenses, class reports, and research talks while preserving the supported public `UP` loader path and the existing title-page, special-frame, bibliography, and content-surface coverage.
- Added `docs/usage-guide.md` as the tracked public quick-start, migration, compile, provenance, and distribution-scope guide for the current baseline.
- Updated `README.md` and `CONTRIBUTING.md` so the public onboarding contract and contributor guidance both point to the new starter-template plus usage-guide baseline.
- Updated `SECURITY.md` so the supported-version matrix follows the `v0.3.0` public baseline.
- Added `docs/version-0-3-0-docs.md` so the public version trail records the starter-template and usage-guide release.

### For Deletion
- Generated local LaTeX build outputs and local compile-validation artifacts remained cleanup candidates before release packaging.

## v0.2.0

### Added or Changed
- Bumped the root public documentation baseline from `v0.1.4` to `v0.2.0`.
- Reconciled the root README status, roadmap, and next-action wording to the current planning reality: identity/governance, brownfield understanding, public `UP` interface migration, and visual adaptation are in place, while showcase expansion and distribution readiness remain open.
- Preserved the current checked-in title-page baseline in the public docs, including multiline-safe metadata layout and explicit-linebreak-safe conference affiliations.
- Updated `SECURITY.md` so the supported-version matrix follows the `0.2.x` public baseline.
- Added `docs/version-0-2-0-docs.md` so the public version trail records the `0.2.0` documentation reconciliation release.

### For Deletion
- Generated local LaTeX build outputs and local title-page verification preview PNGs remained cleanup candidates before release packaging.

## v0.1.4

### Added or Changed
- Reworked the conference-affiliation row formatter in `beamer-up/beamerinnerthemeUU.sty` so explicit `\\` line breaks inside `\addinstitute{n}{...}` stay inside the same hanging-indent text column instead of resetting to the left margin.
- Updated `beamer-up/main.tex` to exercise the manual-linebreak conference-affiliation case directly in the bundled multi-author title-page example.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-1-4-docs.md` so the public version trail distinguishes the explicit-linebreak follow-up from the earlier automatic-wrap repair.

### For Deletion
- Generated local LaTeX build outputs and local title-page verification preview PNGs remained cleanup candidates before release packaging.

## v0.1.3

### Added or Changed
- Reworked `beamer-up/beamerinnerthemeUU.sty` so the title-page content stack grows within a bounded vertical region, preserving the cover composition when multiline metadata is added.
- Added a one-line lower buffer to the title-page content region so the single-author and multi-author covers no longer hug the bottom edge after the multiline layout fix.
- Replaced the multi-author affiliation `tabular` path with hanging-indent paragraph rows so long conference affiliations wrap inside the slide and continuation lines align after the affiliation number.
- Updated `beamer-up/main.tex`, `README.md`, `CHANGELOG.md`, and added `docs/version-0-1-3-docs.md` so the showcase and public docs reflect the multiline subtitle/institute stress cases and the title-page metadata-flow repair.

### For Deletion
- Generated local LaTeX build outputs and local title-page verification preview PNGs remained cleanup candidates before release packaging.

## v0.1.2

### Added or Changed
- Sanitized the root public docs so they no longer reference ignored internal planning paths or specific ignored local LaTeX artifact names.
- Refreshed `repo/images/project_screen.png` to reflect the current public showcase surface used by the repository front page.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-1-2-docs.md` so the public version trail reflects the screenshot refresh and docs sanitization pass.

### For Deletion
- Generated local LaTeX build outputs for the bundled showcase deck remained cleanup candidates before release packaging.

## v0.1.1

### Added or Changed
- Refined `beamer-up/beamerinnerthemeUU.sty` so the light-surface title page now carries a subtle `UPForestGreen` gradient wash.
- Updated `beamer-up/main.tex` to replace the inherited title-slide `v1.0.0` marker with `v0.1.1` and shortened the subtitle copy to "A \LaTeX\ presentation template for the UP System."
- Updated `README.md` and added `docs/version-0-1-1-docs.md` so the root documentation trail reflects the checked-in cover-page baseline and showcase metadata.

### For Deletion
- Generated local LaTeX verification outputs for the bundled showcase deck remained cleanup candidates before release packaging.

## v0.1.0

### Added or Changed
- Bumped the public root documentation baseline from `v0.0.31` to `v0.1.0`.
- Reconciled `README.md`, `CHANGELOG.md`, `CONTRIBUTING.md`, and `SECURITY.md` with the approved planning and requirements baseline.
- Removed stale cross-project changelog content so the root changelog now reflects `beamer-up` only.
- Tightened public wording so `UP` is the supported public loader and any remaining `UU` names are described only as implementation or migration detail.
- Added `docs/version-0-1-0-docs.md` to preserve the versioned public-docs trail for this release.

### For Deletion
- Generated local LaTeX build outputs remain cleanup candidates before release packaging.

## v0.0.31

### Added or Changed
- Switched the non-`nl` content-frame header to canonical runtime-cropped English and Filipino lineshot lockups.
- Rebalanced the visible content-frame header spacing so the lockup renders smaller and lower in the header band.
- Updated the root docs to describe the refined content-frame header baseline.

### For Deletion
- Generated local showcase build outputs from header verification remained cleanup candidates.

## v0.0.30

### Added or Changed
- Replaced the first numeric bibliography item in the showcase deck with the `Paper-thin Threads: Stecker, Art, and Computing` web citation.
- Revalidated the bibliography flow with the documented `pdflatex -> biber -> pdflatex -> pdflatex` chain.
- Updated the root docs to reflect the checked-in bibliography baseline.

### For Deletion
- Generated local showcase build outputs from bibliography verification remained cleanup candidates.

## v0.0.29

### Added or Changed
- Returned the light-surface title-page venue/date separator accent to forest green.
- Revalidated the title-page follow-up on the documented compile path.
- Updated the root docs to reflect the checked-in title-page accent baseline.

### For Deletion
- Generated local showcase build outputs from title-page verification remained cleanup candidates.

## v0.0.28

### Added or Changed
- Normalized public cleanup notes so ignored local build outputs were described generically instead of by specific ignored paths.
- Published the root docs as a docs-only reconciliation release for the then-current checked-in `beamer-up` baseline.

### For Deletion
- None from this docs-only reconciliation release.

## v0.0.27

### Added or Changed
- Strengthened the light-surface title-page typography, divider treatment, and metadata accents.
- Refreshed the bundled showcase metadata on the first title frames.
- Updated the root docs to describe the rebalanced title-page presentation surfaces.

### For Deletion
- Generated local showcase build outputs from title-page verification remained cleanup candidates.

## v0.0.26

### Added or Changed
- Inverted the title-page surface to white, retained the maroon accent bar, and moved the cover-page mark to runtime-cropped black UP lockups.
- Added stable title-page runtime assets for the supported non-`nl` UP cover path.
- Updated the root docs to describe the light-surface title-page baseline.

### For Deletion
- Generated local showcase build outputs from title-page verification remained cleanup candidates.

## v0.0.23-v0.0.25

### Added or Changed
- Reworked the title-page logo path around trimmed and runtime-cropped inline UP lockups.
- Rebalanced the title-page text block so single-author and multi-author covers shared a clearer layout rhythm.
- Continued updating the root docs and per-version narratives as the cover-page implementation stabilized.

### For Deletion
- Generated local showcase build outputs from cover-page verification remained cleanup candidates.

## v0.0.20-v0.0.22

### Added or Changed
- Replaced the inherited Utrecht branding citation in the showcase deck with the UP Visual Identity Guide reference.
- Repaired and rebalanced the UP thank-page footer treatment across several follow-up passes.
- Updated the root docs to track the checked-in bibliography and closing-slide baselines.

### For Deletion
- Generated local showcase build outputs from bibliography and closing-slide verification remained cleanup candidates.

## v0.0.10-v0.0.19

### Added or Changed
- Added selectable UP logotype variants and runtime logo placement paths for the supported non-`nl` surfaces.
- Refined section-divider rendering, closing-slide footer treatment, and content-frame header behavior across multiple narrow follow-up releases.
- Reconciled the public root docs several times as the checked-in visual baseline changed.

### For Deletion
- Generated local showcase build outputs from visual verification remained cleanup candidates.

## v0.0.2-v0.0.9

### Added or Changed
- Established the brownfield baseline, naming/governance baseline, and asset-governance baseline for `beamer-up`.
- Approved the reverse-engineered static and dynamic models of the inherited theme.
- Implemented the public `UP` theme interface and the first UP-directed slide-system baseline.
- Added the versioned public-docs trail under `docs/` to explain each step of the early migration and visual adaptation work.

### For Deletion
- Generated local showcase build outputs from early migration and validation work remained cleanup candidates.
