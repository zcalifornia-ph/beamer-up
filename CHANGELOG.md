# Changelog

Status: current repo milestone `v0.0.22`; the supported `UP` loader and checked-in UP-directed divider, header, and closing-slide treatments remain compile-validated, the repaired thank-page stack now lowers the UP footer slot further to create a more clearly separated Utrecht-like gap beneath the contribution text, and the bundled references example continues to cite the UP Visual Identity Guide 2017 directly instead of the inherited Utrecht branding URL while release-ready packaging plus broader public validation notes remain open work.

## Unreleased

### Added or Changed
- None yet.

### For Deletion
- None yet.

## v0.0.22

### Added or Changed
- Updated `beamer-up/beamerouterthemeUU.sty` so the repaired centered `\thankframe` stack now lowers the visible UP footer block by reducing the fixed post-logo bottom spacing from `0.95cm` to `0.10cm`, creating more separation between the GitHub link and the footer logo/logotype.
- Kept the current UP thank-page title, divider, contribution block, exact horizontal white English/Filipino footer assets, `\raisebox{0cm}` logo wrapper, and existing trim-plus-height rules unchanged while narrowing this follow-up specifically to the footer slot's final resting position.
- Revalidated the affected closing slide on April 2, 2026 with `pdflatex main.tex` from `beamer-up/`, plus page-23 text extraction confirming that the `Feedback?` slide still renders after the footer-slot lowering pass.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-22-docs.md` so the public docs reflect the final thank-page footer-position adjustment.

### For Deletion
- `beamer-up/main.aux`, `beamer-up/main.bbl`, `beamer-up/main.bcf`, `beamer-up/main.blg`, `beamer-up/main.log`, `beamer-up/main.nav`, `beamer-up/main.out`, `beamer-up/main.pdf`, `beamer-up/main.run.xml`, `beamer-up/main.snm`, `beamer-up/main.toc`, and `beamer-up/main.vrb` (generated showcase build artifacts from local thank-page footer-slot verification).
- `beamer-up/thankpage-spacing-v021.svg` (temporary local SVG export still present from thank-page spacing review).

## v0.0.21

### Added or Changed
- Updated `beamer-up/beamerouterthemeUU.sty` so the repaired centered `\thankframe` stack keeps the footer logo at the same size but removes the extra `\raisebox{0.35cm}` lift, letting the UP closing mark sit slightly lower again and restoring a larger text-to-logo gap closer to the inherited Utrecht closing-slide rhythm.
- Kept the current UP thank-page title, divider, contribution block, exact horizontal white English/Filipino footer assets, and existing trim-plus-height rules unchanged while narrowing this follow-up specifically to footer spacing harmony.
- Revalidated the affected closing slide on April 2, 2026 with `pdflatex main.tex` from `beamer-up/`, plus page-23 text extraction and a page-23 SVG export confirming that the `Feedback?` slide still renders after the footer-spacing adjustment.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-21-docs.md` so the public docs reflect the lowered footer resting position.

### For Deletion
- `beamer-up/main.aux`, `beamer-up/main.bbl`, `beamer-up/main.bcf`, `beamer-up/main.blg`, `beamer-up/main.log`, `beamer-up/main.nav`, `beamer-up/main.out`, `beamer-up/main.pdf`, `beamer-up/main.run.xml`, `beamer-up/main.snm`, `beamer-up/main.toc`, and `beamer-up/main.vrb` (generated showcase build artifacts from local thank-page spacing verification).
- `beamer-up/thankpage-spacing-v021.svg` (temporary local SVG export generated to review the adjusted thank-page footer spacing).

## v0.0.20

### Added or Changed
- Updated `beamer-up/references.bib` so the bundled branding reference now cites `UP Visual Identity Guide 2017` from the UP-hosted PDF instead of the earlier Utrecht corporate-identity URL.
- Updated `beamer-up/main.tex` so the references slide now cites `upvig2017`, keeping the showcase text and the rendered bibliography entry aligned with the UP guide rather than the inherited Utrecht metadata.
- Revalidated the references slide on April 2, 2026 with `pdflatex main.tex`, `biber main`, and two additional `pdflatex main.tex` passes from `beamer-up/`, plus page-24 text extraction confirming that the rendered `[3]` entry now resolves to `University of the Philippines. UP Visual Identity Guide 2017.`
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-20-docs.md` so the public docs reflect the corrected bibliography source.

### For Deletion
- `beamer-up/main.aux`, `beamer-up/main.bbl`, `beamer-up/main.bcf`, `beamer-up/main.blg`, `beamer-up/main.log`, `beamer-up/main.nav`, `beamer-up/main.out`, `beamer-up/main.pdf`, `beamer-up/main.run.xml`, `beamer-up/main.snm`, `beamer-up/main.toc`, and `beamer-up/main.vrb` (generated showcase build artifacts from local bibliography-source verification).

## v0.0.19

### Added or Changed
- Updated `beamer-up/beamerouterthemeUU.sty` so `\thankframe` now uses a stable centered frame stack instead of the earlier fragile overlay-only layout, restoring the visible title, divider, and contribution text on the thank page.
- Kept the exact bundled horizontal white English and Filipino UP footer-logo assets, the existing language-specific trim boxes, and the dedicated `\@upclosinglogoheight` footer scale, while raising the rendered footer mark slightly with a small `\raisebox{0.35cm}` offset.
- Revalidated the affected closing slide on April 2, 2026 with `pdflatex main.tex` from `beamer-up/`, plus page-23 text extraction and SVG inspection confirming that `Feedback?`, the contribution block, and the UP footer lockup now render together and that the footer mark sits higher than before.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-19-docs.md` so the public docs reflect the repaired thank-page layout and the raised footer-logo slot.

### For Deletion
- Generated local LaTeX build outputs currently present in `beamer-up/` remain cleanup candidates before release packaging.
- `beamer-up/closing-filipino-test.log` remains a scratch compile log that can be removed after review.
- `beamer-up/preview-page-23-baseline-23.png` (temporary local raster render from baseline thank-page verification).
- `beamer-up/preview-page-23-current-23.png` (temporary local raster render from the broken intermediate thank-page verification).
- `beamer-up/thankpage-baseline.svg` (temporary local SVG export used to trace the pre-fix thank-page geometry).
- `beamer-up/thankpage-fixed.svg` (temporary local SVG export used to confirm the repaired thank-page geometry).

## v0.0.18

### Added or Changed
- Updated `beamer-up/beamerouterthemeUU.sty` so the non-`nl` `\thankframe` footer logo now uses a dedicated `\@upclosinglogoheight` constant set to `1.10cm` instead of the earlier inline `0.74cm` include height.
- Enlarged the exact horizontal white English and Filipino UP closing-slide footer logos so their perceived size reads closer to the inherited Utrecht University feedback-page footer mark while preserving the existing trim boxes, language selection, and legacy `nl` fallback path.
- Revalidated the affected closing slide on April 2, 2026 with `pdflatex main.tex` from `beamer-up/` plus rendered closing-slide inspection confirming that the larger UP footer mark still fits cleanly inside the page.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-18-docs.md` so the public docs reflect the larger feedback-page footer logo baseline.

### For Deletion
- Generated local LaTeX build outputs currently present in `beamer-up/` remain cleanup candidates before release packaging.
- `beamer-up/closing-filipino-test.log` remains a scratch compile log that can be removed after review.

## v0.0.17

### Added or Changed
- Updated `README.md` version markers and status text to publish this as the `v0.0.17` documentation-reconciliation release for the current checked-in `beamer-up` baseline.
- Corrected the `README.md` repository layout summary so it reflects the actual root structure (`docs/`, `repo/images/`, and the nested `beamer-up/` theme workspace) instead of the earlier mixed path listing.
- Refreshed the `README.md` validation note to the latest recorded April 2, 2026 targeted divider-verification pass while keeping `latexmk -pdf main.tex` as the recommended full build command.
- Added `docs/version-0-0-17-docs.md` as the detailed narrative note for this docs-only release.
- Left `SECURITY.md`, `CONTRIBUTING.md`, and `CODE_OF_CONDUCT.md` unchanged because their current governance language already matches repo reality.

### For Deletion
- Generated local LaTeX build outputs currently present in `beamer-up/` remain cleanup candidates before release packaging.
- `beamer-up/closing-filipino-test.log` remains a scratch compile log that can be removed after review.

## v0.0.16

### Added or Changed
- Updated `beamer-up/beamerinnerthemeUU.sty` so the automatic section-divider page now uses the plain current section title token `\secname` instead of the hyperlinked Beamer `\insertsectionhead` wrapper.
- Corrected the remaining automatic section-divider visibility issue so the section title now renders as visible white text on the maroon divider surface, matching the manual `\sectionframe` treatment more closely.
- Preserved the existing UP maroon-and-gold divider layout while narrowing this fix specifically to the automatic section-page text token and styling path.
- Revalidated the affected section divider on April 2, 2026 with `pdflatex main.tex` from `beamer-up/` plus local text extraction and rendered-page inspection confirming that `Getting Started` is visible again on the automatic divider slide.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-16-docs.md` so the public docs reflect the matched automatic/manual divider text treatment and the final verification state.

### For Deletion
- None from this task context.

## v0.0.15

### Added or Changed
- Updated `beamer-up/beamerouterthemeUU.sty` so the non-`nl` closing-slide footer keeps the exact `up-horizontal-logo-with-white-engtype.png` and `up-horizontal-logo-with-white-tagtype.png` files but now trims each one to tighter language-specific visible bounds.
- Corrected the final footer-logo render by replacing the earlier still-imperfect crop with trim values derived from the actual nontransparent logo region and by retuning the closing-slide footer anchor plus rendered height.
- Preserved the inherited beamer-uu-style closing-slide layout, the existing `english` / `filipino` selection rule, and the legacy `nl` fallback while narrowing this change specifically to the remaining footer-logo clipping defect.
- Revalidated the affected closing slide on April 2, 2026 with `pdflatex main.tex` from `beamer-up/` plus direct rendered-page inspection confirming that the full `University of the Philippines` footer wordmark is now visible.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-15-docs.md` so the public docs reflect the tighter visible-bounds footer crop and the final closing-slide verification state.

### For Deletion
- `beamer-up/preview-page-23-current-23.png` (temporary local PDF page render used to confirm the footer was still clipped before the final crop correction).
- `beamer-up/preview-page-23-fixed-23.png` (temporary local PDF page render generated during an intermediate footer-offset and size adjustment that still did not fully solve the clipping).
- `beamer-up/preview-page-23-seq-23.png` (temporary local PDF page render generated from a sequential rebuild while isolating whether the preview had been rendered from the latest PDF).
- `beamer-up/preview-page-23-cropfix-23.png` (temporary local PDF page render used to confirm the final tighter footer crop shows the full visible UP wordmark).

## v0.0.14

### Added or Changed
- Updated `beamer-up/beamerouterthemeUU.sty` so the non-`nl` closing-slide footer now uses the exact `up-horizontal-logo-with-white-engtype.png` and `up-horizontal-logo-with-white-tagtype.png` files again rather than the temporary composed fallback.
- Replaced the earlier overly tight closing-slide trim box with a safer crop and switched the footer logo sizing to a smaller `height`-based include so the full horizontal UP mark stays visible above the bottom edge.
- Preserved the inherited beamer-uu-style closing-slide layout and the existing `english` / `filipino` selection rule while narrowing this fix specifically to footer-logo rendering.
- Revalidated the affected closing slide on April 2, 2026 with `pdflatex main.tex` from `beamer-up/` and a local rendered page preview after the footer-logo sizing and crop adjustment.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-14-docs.md` so the public docs reflect that the footer now uses the exact horizontal white UP files without cropping out the visible lockup.

### For Deletion
- `beamer-up/preview-page-23-horizontal-23.png` (temporary local PDF page render used to confirm the horizontal white UP closing-slide logo stayed inside the footer area after the trim and height adjustment).

## v0.0.13

### Added or Changed
- Updated `beamer-up/beamerinnerthemeUU.sty` so automatic section-divider slides now use Beamer's populated `\insertsectionhead` token, restoring visible section titles while preserving the current UP maroon-and-gold divider surface.
- Updated `beamer-up/beamerouterthemeUU.sty` so `\thankframe` now follows the inherited beamer-uu feedback-page layout more closely, with the title first, the divider beneath it, centered contribution text below, and a bottom-centered logo slot.
- Added and/or promoted horizontal and vertical UP source-logo variants under `beamer-up/logos/`, and wired the non-`nl` closing-slide path to the selected `up-horizontal-logo-with-white-engtype.png` or `up-horizontal-logo-with-white-tagtype.png`.
- Revalidated the affected surfaces on April 1, 2026 with `latexmk -pdf main.tex` from `beamer-up/`, plus local text-extraction and page-render checks confirming the automatic section title is present again.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-13-docs.md` so the public docs reflect the restored divider behavior and the language-aware UP closing-slide lockup.

### For Deletion
- `beamer-up/main.aux`, `beamer-up/main.bbl`, `beamer-up/main.bcf`, `beamer-up/main.blg`, `beamer-up/main.fdb_latexmk`, `beamer-up/main.fls`, `beamer-up/main.log`, `beamer-up/main.nav`, `beamer-up/main.out`, `beamer-up/main.pdf`, `beamer-up/main.run.xml`, `beamer-up/main.snm`, `beamer-up/main.toc`, and `beamer-up/main.vrb` (generated showcase build artifacts from local verification of the divider and closing-slide changes).
- `beamer-up/preview-page-4-04.png` (temporary local PDF page render used to confirm the automatic section-divider title was visible again).
- `beamer-up/closing-filipino-test.log` (scratch local compile log generated while probing the Filipino closing-slide path).

## v0.0.12

### Added or Changed
- Updated `beamer-up/beamerouterthemeUU.sty` so the non-`nl` content-slide `showlogo` path now composes the UP lineshot seal beside the selected UP logotype instead of rendering only the standalone wordmark.
- Scaled the UP header seal and tightened the lockup spacing so the composed English and Filipino content-slide lockups stay inside the header band and do not drop into the gold rule.
- Added separate English and Filipino header wordmark widths so the visible text height reads more consistently against the seal while preserving the legacy `nl` Dutch-logo compatibility branch unchanged.
- Revalidated the affected header surfaces on April 1, 2026 with `latexmk -pdf main.tex` and higher-resolution local PDF page renders from `beamer-up/` after the lockup-sizing change.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-12-docs.md` so the public docs reflect the current UP header-lockup behavior.

### For Deletion
- `beamer-up/logos/up-logo-lineshot-on-white-preview.png` (temporary local white-background preview used to inspect the lineshot seal before composing the header lockup).
- `beamer-up/logos/up-logotype-eng-black-on-white-preview.png` (temporary local white-background preview used to inspect the English wordmark source before composing the header lockup).
- `beamer-up/logos/up-logotype-tag-black-on-white-preview.png` (temporary local white-background preview used to inspect the Filipino wordmark source before composing the header lockup).
- `beamer-up/preview-page-3-hi.png` (temporary high-resolution local PDF page render used to inspect the outline-slide header lockup).
- `beamer-up/preview-page-3-hi-topright.png` (temporary cropped high-resolution local render used to inspect the outline-slide top-right header lockup).
- `beamer-up/preview-page-6-hi.png` (temporary high-resolution local PDF page render used to inspect the content-slide header lockup).
- `beamer-up/preview-page-6-hi-topright.png` (temporary cropped high-resolution local render used to inspect the content-slide top-right header lockup).

## v0.0.11

### Added or Changed
- Updated `beamer-up/beamerouterthemeUU.sty` so the UP content-slide `showlogo` wordmark now anchors against Beamer's right content margin instead of a fixed page-edge offset.
- Preserved the legacy `nl` Dutch-logo compatibility branch while tightening the English and Filipino UP logotype placement so the visible right edge matches the right-side block margin on content slides.
- Revalidated the content-slide header placement on April 1, 2026 with `latexmk -pdf main.tex` and local PDF page renders from `beamer-up/` after the alignment change.
- Updated `README.md`, `CHANGELOG.md`, and added `docs/version-0-0-11-docs.md` so the public docs reflect the refined UP wordmark alignment behavior.

### For Deletion
- `beamer-up/preview-page-4.png` (temporary local PDF page render used to inspect the section divider during alignment checks).
- `beamer-up/preview-page-5.png` (temporary local PDF page render used to inspect the usage slide during alignment checks).
- `beamer-up/preview-page-6.png` (temporary local PDF page render used to inspect the content-slide wordmark alignment against the right content margin).
- `beamer-up/preview-page-7.png` (temporary local PDF page render used to inspect the manual section-divider slide during alignment checks).


## v0.0.10

### Added or Changed
- Added selectable UP logotype language variants in `beamer-up/beamerthemeUU.sty`, with `english` as the default and `filipino` as the `Unibersidad ng Pilipinas` switch while preserving `nl` as the Dutch compatibility path.
- Updated `beamer-up/beamerinnerthemeUU.sty` and `beamer-up/beamerouterthemeUU.sty` so the selected UP logotype is reused on content, title, and thank-you slides with light-surface and dark-surface variants where available.
- Added runtime-cropped UP logotype assets under `beamer-up/logos/` so the theme can place the new wordmarks consistently without depending on the large transparent source canvases.
- Corrected the active UP palette in `beamer-up/beamercolorthemeUU.sty` to the official core values `#8E1537`, `#005740`, `#FFB81D`, `#231F20`, promoted `UPYellow` as the canonical accent token, and kept `UPGold` only as a compatibility alias.
- Updated `beamer-up/main.tex` and `README.md` usage notes to document the `english` / `filipino` theme options and the revised logo behavior.
- Updated the root docs and `docs/version-0-0-10-docs.md` so the public release note set now reflects the current logo-source, runtime-asset, corrected-palette, and temporary inspection-artifact state alongside the root release notes.
- Revalidated the supported compile path on April 1, 2026: `latexmk -pdf main.tex` succeeds from `beamer-up/` after the new logo-option work.

### For Deletion
- `beamer-up/logos/up-logotype-eng-black-preview.png` (temporary local inspection composite generated while checking logo visibility on a background).
- `beamer-up/logos/up-logotype-eng-white-preview.png` (temporary local inspection composite generated while checking logo visibility on a background).
- `beamer-up/logos/uu-logo-en-black-render.png` (temporary local rasterized comparison output for the inherited Utrecht logo).
- `beamer-up/logos/uu-logo-en-rgb-render.png` (temporary local rasterized comparison output for the inherited Utrecht logo).
- `beamer-up/preview-page-1.png` (temporary local PDF page render used to inspect the title slide).
- `beamer-up/preview-page-3.png` (temporary local PDF page render used to inspect the outline slide).
- `beamer-up/preview-page-23.png` (temporary local PDF page render used to inspect the thank-you slide).

## v0.0.9

### Added or Changed
- Implemented the approved UP-directed slide styling across the checked-in theme by updating `beamer-up/beamercolorthemeUU.sty`, `beamer-up/beamerinnerthemeUU.sty`, `beamer-up/beamerouterthemeUU.sty`, and `beamer-up/beamerthemeUU.sty`.
- Replaced the inherited Utrecht-led palette with UP maroon, forest green, gold, spot black, and compatible tint tokens while preserving legacy `UU*` color aliases only for controlled compatibility.
- Shifted the supported typography baseline to Palatino body text plus a Helvetica-style sans hierarchy for titles, frame titles, subtitles, and footlines under the documented `pdfLaTeX` workflow.
- Reworked title, section-divider, standout, thank-you, footline, and table-of-contents surfaces so the public `UP` loader now renders a coherent UP-directed visual system.
- Updated the bundled showcase deck in `beamer-up/main.tex` to demonstrate the new palette, revised typography guidance, UP-context academic examples, and the current option/helper behavior.
- Revalidated the supported compile path on April 1, 2026: `latexmk -pdf main.tex` succeeds from `beamer-up/` with the public `UP` loader.
- Reconciled the root `README.md`, root `CHANGELOG.md`, and added `docs/version-0-0-9-docs.md` so the public repo docs now match the implemented styling milestone.

### For Deletion
- `beamer-up/main.bcf` (generated bibliography control file from local showcase compilation).
- `beamer-up/main.fls` (generated `latexmk` file list from local showcase compilation).
- `beamer-up/main.log` (generated TeX log from local showcase compilation).
- `beamer-up/main.pdf` (generated showcase PDF build artifact).
- `beamer-up/main.run.xml` (generated bibliography/runtime metadata artifact).
- `beamer-up/main.synctex.gz` (generated editor sync artifact).
- `beamer-up/main.toc` (generated table-of-contents artifact).
- `beamer-up/main.vrb` (generated Beamer verbatim cache artifact).

## v0.0.8

### Added or Changed
- Drafted the `U-D` visual-direction baseline for `beamer-up`, including a concrete UP palette, typography hierarchy, logo strategy, and decorative-rule set for title, section, content, standout, and closing-slide surfaces.
- Recorded contrast and readability guidance for the mapped visual system, including the explicit rejection of white-on-gold text and the approval of high-contrast maroon, forest-green, gold, and dark-text pairings.
- Updated `README.md` to move the public project state to `v0.0.8`, document that the visual-system mapping is drafted, and position the next bolt as template styling rather than interface migration.
- Added `docs/version-0-0-8-docs.md` as the public narrative note for this visual-direction planning milestone.

### For Deletion
- Generated LaTeX build artifacts and logo-conversion outputs from local showcase compilation were recorded for later cleanup rather than deleted in place.

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
- Temporary local scratch artifacts created during editing were intentionally left out of the public project surface.

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
