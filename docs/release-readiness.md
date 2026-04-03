# Release Readiness

## Status

- Unit: `U-E`
- Bolt: `B-UE-02`
- Evidence captured on: `2026-04-03`
- Current state: implementation, validation, and documentation are complete; human approval is still required before bolt closure and before `deploy.task` or `ops.task` proceeds.

## Evidence Surfaces

- Checked-in starter deck: `beamer-up/main.tex`
- Preferred compile evidence: `beamer-up/main.log`, `beamer-up/main.pdf`
- Manual fallback compile evidence: `beamer-up/main.log`, `beamer-up/main.pdf`
- Public screenshot surface: `repo/images/project_screen.png`
- Public guidance surfaces: `README.md`, `docs/usage-guide.md`
- Governance surfaces: `beamer-up/docs/identity-governance.md`, `beamer-up/docs/asset-governance.md`

## Acceptance Checklist

| ID | Result | Evidence |
| --- | --- | --- |
| `T-01` | pass | `latexmk -pdf main.tex` succeeded from `beamer-up/` with exit code `0`; `main.log` records `Output written on main.pdf (28 pages, 1157911 bytes).` and `main.pdf` exists at 1,157,911 bytes. |
| `T-02` | pass | the documented fallback chain `pdflatex -> biber -> pdflatex -> pdflatex` succeeded from `beamer-up/` with exit code `0`; the final `main.log` and `main.pdf` remain in sync after the acceptance run. |
| `T-04` | pass | the compiled deck still exercises the supported feature surfaces present in `main.tex`: `\usetheme[showlogo,english]{UP}`, `\multiauthor`, `\singleauthor`, `\sectionframe`, `\standoutframe`, `\thankframe`, and `\printbibliography`; the final PDF remains 28 pages. |
| `T-05` | pass | `project_screen.png` was refreshed from the final `main.pdf`; the supported English path uses UP runtime assets observed in `main.log`/`main.fls`, and `main.tex` no longer contains visible Utrecht-branded presentation copy. |
| `T-06` | pass | `B-UE-02` did not change the theme source; the current screenshot and unchanged UP-directed slide system remain consistent with the readability and contrast decisions already approved in `U-D`, while the remaining `Underfull \hbox` warnings are confined to documentation-heavy slides and remain non-blocking. |
| `T-07` | pass | `README.md`, `docs/usage-guide.md`, `docs/release-readiness.md`, `CONTRIBUTING.md`, and `beamer-up/main.tex` preserve derivative attribution, non-endorsement wording, and the UP branding-use disclaimer posture. |
| `T-08` | pass | the supported English runtime path now has observed asset evidence for `logos/up-logotype-eng-runtime-black.png`, `logos/up-inline-logo-eng-runtime-black.png`, `logos/up-inline-lineshot-eng-runtime-black.png`, and `logos/up-horizontal-logo-with-white-engtype.png`; the readiness notes below tie those assets back to the governance disclaimer baseline. |
| `T-09` | pass | user-facing docs still direct older users from `\usetheme{UU}` to `\usetheme{UP}` and treat remaining `UU` names as migration or implementation detail only. |
| `T-10` | pass | `README.md`, `docs/usage-guide.md`, and this readiness artifact now describe the same supported `UP` entry path, compile posture, provenance wording, and GitHub/Overleaf distribution notes. |

## Compile Evidence

### Preferred path

Command run from `beamer-up/`:

```sh
latexmk -pdf main.tex
```

Observed outcome:

- exit code `0`
- `main.log` records `Output written on main.pdf (28 pages, 1157911 bytes).`
- final artifact timestamps after the acceptance run:
  - `beamer-up/main.pdf`: `2026-04-03 16:08:07`
  - `beamer-up/main.log`: `2026-04-03 16:08:07`

### Documented fallback path

Commands run from `beamer-up/`:

```sh
pdflatex -interaction=nonstopmode main.tex
biber main
pdflatex -interaction=nonstopmode main.tex
pdflatex -interaction=nonstopmode main.tex
```

Observed outcome:

- exit code `0`
- final `main.pdf` and `main.log` remained current after the manual sequence
- no additional blockers were introduced by the fallback path

## Visual and Screenshot Evidence

- `repo/images/project_screen.png` was regenerated from the final `main.pdf` on `2026-04-03 16:08:39`.
- The refreshed screenshot now matches the checked-in starter template title slide instead of the older pre-template screenshot.
- The final deck continues to render the single-author title page, multi-author title page, section-divider slide, standout slide, closing slide, and bibliography frame from one compileable source.

## Asset-Governance Evidence

The supported first-release English runtime path currently observes these UP assets in compile evidence:

| Asset path | Role in the supported path | Evidence |
| --- | --- | --- |
| `beamer-up/logos/up-logotype-eng-runtime-black.png` | content-slide/header logotype path | referenced in `beamerthemeUU.sty`; observed in `main.fls` |
| `beamer-up/logos/up-inline-logo-eng-runtime-black.png` | title-page runtime lockup | referenced in `beamerthemeUU.sty`; observed in `main.log` and `main.fls` |
| `beamer-up/logos/up-inline-lineshot-eng-runtime-black.png` | section/header lineshot lockup | referenced in `beamerouterthemeUU.sty`; observed in `main.log` and `main.fls` |
| `beamer-up/logos/up-horizontal-logo-with-white-engtype.png` | closing-slide lockup | referenced in `beamerouterthemeUU.sty`; observed in `main.log` and `main.fls` |

Additional notes:

- The legacy Dutch `nl` path still points at inherited `UU` EPS assets and remains compatibility-only, not part of the supported first-release proof surface.
- UP-branded assets remain subject to the repository's derivative, non-endorsement, and internal-use disclaimer posture documented in `README.md`, `docs/usage-guide.md`, `CONTRIBUTING.md`, and `beamer-up/main.tex`.

## GitHub and Overleaf Distribution Notes

The intended first-release public scope remains the same across GitHub and Overleaf:

- the supported public loader is `UP`
- the bundled showcase deck is the starter template and validation surface
- the documented compile path is `latexmk -pdf main.tex` with the `pdflatex -> biber -> pdflatex -> pdflatex` fallback
- the derivative, attribution, non-endorsement, and branding-use wording must remain aligned with `README.md`, `docs/usage-guide.md`, and `CONTRIBUTING.md`
- the refreshed screenshot surface for public documentation is `repo/images/project_screen.png`

This bolt records the distribution-readiness notes and evidence package only. It does not itself publish a GitHub release or an Overleaf package.

## Non-Blocking Warnings

The final acceptance run still reports these non-blocking warnings:

- `hyperref` warns about the title-page spacing token in the PDF string metadata.
- `hyperref` warns that `pdfauthor` is reused when the deck intentionally switches between single-author and multi-author title pages.
- `main.log` records several `Underfull \hbox` warnings on documentation-heavy slides.
- MiKTeX emits local `log4cxx` access warnings for its user-profile logging path, but all required compile and screenshot commands still completed successfully.

## Deployment-Check Handoff

- `DCHK-01`: ready for human review because source, docs, screenshot, disclaimers, and validation evidence are now packaged together.
- `DCHK-02`: ready for human review because the documented GitHub and Overleaf wording now points to the same supported `UP` path and compile baseline.
- `DCHK-03`: ready for human review because the supported-path UP runtime assets and disclaimer posture are now recorded in one readiness surface.
- `DCHK-04`: ready for human review because the public docs still point users from `UU` to `UP` and keep remaining `UU` names migration- or implementation-scoped.
