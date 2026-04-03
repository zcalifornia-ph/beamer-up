# Changelog

Status: current supported public release `v1.0.0`; the supported public loader is `UP`, `beamerthemeUP.sty` is the canonical implementation entry, the active color/inner/outer subthemes use `UP` filenames, the first-release requirements and validation gates are closed, and the root public docs no longer reference ignored internal documentation paths.

## v1.0.0

### Added or Changed
- Promoted the root public baseline from `v0.4.0` to `v1.0.0` as the first supported public release.
- Reconciled `README.md`, `CHANGELOG.md`, `CONTRIBUTING.md`, and `SECURITY.md` to the approved first-release requirements state so the root docs now describe the final readiness gate as closed rather than pending.
- Removed root-doc references to ignored internal documentation paths and hidden workflow artifacts so the public contract stands on the maintained root surfaces only.
- Updated the current public README contract to remove the stale `nl` option reference and to reflect that no legacy `UU` wrapper or loader file is part of the maintained first-release surface.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace remained cleanup candidates before future packaging refreshes.

## v0.4.0

### Added or Changed
- Bumped the root public documentation baseline from `v0.3.5` to `v0.4.0`.
- Reconciled `README.md` to the approved requirements baseline so the current public status, roadmap, and next-action wording reflected that the planned first-release work was implemented and only one human approval gate remained open before deploy or ops handoff.
- Added a companion version note to capture the requirements-alignment reconciliation for this new public baseline.
- Updated `SECURITY.md` so the supported-version matrix follows the new `v0.4.0` public baseline.
- Normalized the `CHANGELOG.md` cleanup notes so ignored local LaTeX build artifacts are described generically instead of by explicit ignored filenames or wildcard patterns.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace remained cleanup candidates before release packaging.

## v0.3.5

### Added or Changed
- Bumped the root public documentation baseline from `v0.3.4` to `v0.3.5`.
- Updated the public onboarding and release-readiness wording so the current public contract centers on the supported `UP` loader and no longer presents a legacy `UU` wrapper as part of the maintained public surface.
- Updated the checked-in starter-template wording in `beamer-up/main.tex` and the source header in `beamer-up/beamerthemeUP.sty` so the current implementation notes now tell users to migrate older `\usetheme{UU}` material rather than implying an active legacy loader path.
- Added a companion version note to capture the current public-contract cleanup after the legacy-wrapper retirement.
- Updated `SECURITY.md` so the supported-version matrix follows the new `v0.3.5` public baseline.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace remained cleanup candidates before release packaging.

## v0.3.4

### Added or Changed
- Bumped the root public documentation baseline from `v0.3.3` to `v0.3.4`.
- Renamed the active color, inner, and outer subtheme files to `beamercolorthemeUP.sty`, `beamerinnerthemeUP.sty`, and `beamerouterthemeUP.sty`.
- Updated `beamer-up/beamerthemeUP.sty` so the canonical public loader now requests the `UP`-named subthemes directly.
- Updated the renamed subtheme package declarations and source headers so they identify themselves as `beamercolorthemeUP`, `beamerinnerthemeUP`, and `beamerouterthemeUP`.
- Updated the public onboarding wording, release-readiness wording, and the file-overview table in `beamer-up/main.tex` so the live docs and starter template now point at the `UP`-named subtheme files and current runtime references.
- Updated `SECURITY.md` so the supported-version matrix follows the new `v0.3.4` public baseline.
- Added a companion version note to capture the active subtheme filename migration, rationale, and compile-validation notes for this patch-level release.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace remained cleanup candidates before release packaging.

## v0.3.3

### Added or Changed
- Bumped the root public documentation baseline from `v0.3.2` to `v0.3.3`.
- Consolidated the theme orchestration into `beamer-up/beamerthemeUP.sty`, so the supported public `UP` package is now the real canonical implementation entry rather than a thin wrapper over `beamerthemeUU.sty`.
- Reduced `beamer-up/beamerthemeUU.sty` to a deprecated compatibility wrapper that forwards options to `beamerthemeUP.sty` and preserves migration guidance for older `\usetheme{UU}` material.
- Updated the public onboarding copy and the checked-in showcase wording in `beamer-up/main.tex` so `beamerthemeUP.sty` is described as the canonical theme entry and `beamerthemeUU.sty` only as legacy compatibility.
- Added a companion version note to capture the implementation-surface consolidation, rationale, and compile-validation notes for this patch-level release.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace remained cleanup candidates before release packaging.

## v0.3.2

### Added or Changed
- Bumped the root public documentation baseline from `v0.3.0` to `v0.3.2` for a docs-only archive-reorganization release.
- Reorganized the historical public version trail so the earlier `v0.0.x`, `v0.1.x`, and `v0.2.x` narratives moved into grouped archive buckets instead of crowding the live documentation surface.
- Kept the active `v0.3.x` narratives near the current release trail, including the current baseline narrative, the `v0.3.0` reconciliation follow-up, the pending `v0.3.1` readiness narrative, and a companion archive-reorganization note.
- Updated `README.md` and `SECURITY.md` so the public repo layout and supported-version matrix match the reorganized version-doc trail.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace remained cleanup candidates before release packaging.

## v0.3.0 Reconciliation Follow-Up

### Added or Changed
- Normalized the root public documentation version markers back to `v0.3.0` so the published baseline matched the approved requirements state while one human approval gate still remained open.
- Kept the release-readiness note as the tracked compile, screenshot, packaging, and human-review handoff artifact without treating it as a published `v0.3.1` baseline.
- Kept `repo/images/project_screen.png` and the aligned README or usage wording as current supporting evidence for the pending readiness review rather than as a separate approved public release.
- Left the pending `v0.3.1` follow-up narrative in the public version trail rather than treating it as the current approved baseline.
- Added a companion reconciliation note to explain the `v0.3.0` baseline normalization and the pending status of the release-readiness follow-up materials.

### For Deletion
- Generated local LaTeX build outputs from the bundled showcase workspace remained cleanup candidates before release packaging.

## v0.3.0

### Added or Changed
- Bumped the root public documentation baseline from `v0.2.0` to `v0.3.0`.
- Expanded `beamer-up/main.tex` from a showcase-only deck into the checked-in starter template for thesis defenses, class reports, and research talks while preserving the supported public `UP` loader path and the existing title-page, special-frame, bibliography, and content-surface coverage.
- Added a bundled quick-start, migration, compile, provenance, and distribution-scope guide for the current baseline.
- Updated `README.md` and `CONTRIBUTING.md` so the public onboarding contract and contributor guidance both point to the new starter-template plus usage-guide baseline.
- Updated `SECURITY.md` so the supported-version matrix follows the `v0.3.0` public baseline.
- Added a companion version note so the public version trail records the starter-template and usage-guide release.

### For Deletion
- Generated local LaTeX build outputs and local compile-validation artifacts remained cleanup candidates before release packaging.

## v0.2.0

### Added or Changed
- Bumped the root public documentation baseline from `v0.1.4` to `v0.2.0`.
- Reconciled the root README status, roadmap, and next-action wording to the current planning reality: identity/governance, brownfield understanding, public `UP` interface migration, and visual adaptation are in place, while showcase expansion and distribution readiness remain open.
- Preserved the current checked-in title-page baseline in the public docs, including multiline-safe metadata layout and explicit-linebreak-safe conference affiliations.
- Updated `SECURITY.md` so the supported-version matrix follows the `0.2.x` public baseline.
- Added a companion version note so the public version trail records the `0.2.0` documentation reconciliation release.

### For Deletion
- Generated local LaTeX build outputs and local title-page verification preview PNGs remained cleanup candidates before release packaging.

## v0.1.4

### Added or Changed
- Reworked the conference-affiliation row formatter in `beamer-up/beamerinnerthemeUU.sty` so explicit `\\` line breaks inside `\addinstitute{n}{...}` stay inside the same hanging-indent text column instead of resetting to the left margin.
- Updated `beamer-up/main.tex` to exercise the manual-linebreak conference-affiliation case directly in the bundled multi-author title-page example.
- Updated `README.md`, `CHANGELOG.md`, and added a companion version note so the public version trail distinguishes the explicit-linebreak follow-up from the earlier automatic-wrap repair.

### For Deletion
- Generated local LaTeX build outputs and local title-page verification preview PNGs remained cleanup candidates before release packaging.

## v0.1.3

### Added or Changed
- Reworked `beamer-up/beamerinnerthemeUU.sty` so the title-page content stack grows within a bounded vertical region, preserving the cover composition when multiline metadata is added.
- Added a one-line lower buffer to the title-page content region so the single-author and multi-author covers no longer hug the bottom edge after the multiline layout fix.
- Replaced the multi-author affiliation `tabular` path with hanging-indent paragraph rows so long conference affiliations wrap inside the slide and continuation lines align after the affiliation number.
- Updated `beamer-up/main.tex`, `README.md`, `CHANGELOG.md`, and added a companion version note so the showcase and public docs reflect the multiline subtitle/institute stress cases and the title-page metadata-flow repair.

### For Deletion
- Generated local LaTeX build outputs and local title-page verification preview PNGs remained cleanup candidates before release packaging.

## v0.1.2

### Added or Changed
- Sanitized the root public docs so they no longer reference ignored internal planning paths or specific ignored local LaTeX artifact names.
- Refreshed `repo/images/project_screen.png` to reflect the current public showcase surface used by the repository front page.
- Updated `README.md`, `CHANGELOG.md`, and added a companion version note so the public version trail reflects the screenshot refresh and docs sanitization pass.

### For Deletion
- Generated local LaTeX build outputs for the bundled showcase deck remained cleanup candidates before release packaging.

## v0.1.1

### Added or Changed
- Refined `beamer-up/beamerinnerthemeUU.sty` so the light-surface title page now carries a subtle `UPForestGreen` gradient wash.
- Updated `beamer-up/main.tex` to replace the inherited title-slide `v1.0.0` marker with `v0.1.1` and shortened the subtitle copy to "A \LaTeX\ presentation template for the UP System."
- Updated `README.md` and added a companion version note so the root documentation trail reflects the checked-in cover-page baseline and showcase metadata.

### For Deletion
- Generated local LaTeX verification outputs for the bundled showcase deck remained cleanup candidates before release packaging.

## v0.1.0

### Added or Changed
- Bumped the public root documentation baseline from `v0.0.31` to `v0.1.0`.
- Reconciled `README.md`, `CHANGELOG.md`, `CONTRIBUTING.md`, and `SECURITY.md` with the approved planning and requirements baseline.
- Removed stale cross-project changelog content so the root changelog now reflects `beamer-up` only.
- Tightened public wording so `UP` is the supported public loader and any remaining `UU` names are described only as implementation or migration detail.
- Added a companion version note to preserve the versioned public-docs trail for this release.

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
- Added the versioned public-docs trail to explain each step of the early migration and visual adaptation work.

### For Deletion
- Generated local showcase build outputs from early migration and validation work remained cleanup candidates.
