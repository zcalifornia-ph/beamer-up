# Usage Guide

## Purpose

This guide explains the supported public `beamer-up` workflow for presenters and contributors who want to start from the checked-in UP-themed template without reading the internal repository workflow artifacts.

## Quick Start

1. Clone the repository and move into the bundled theme workspace.
   ```sh
   git clone https://github.com/zcalifornia-ph/beamer-up.git
   cd beamer-up/beamer-up
   ```
2. Compile the checked-in showcase and starter template.
   ```sh
   latexmk -pdf main.tex
   ```
3. If `latexmk` is unavailable, use the fallback sequence.
   ```sh
   pdflatex main.tex
   biber main
   pdflatex main.tex
   pdflatex main.tex
   ```
4. Copy the theme files and `logos/` directory into your own presentation project, or install them into your local TeX tree if that better matches your workflow.

## Supported Public Loader

Use the supported public loader only:

```tex
\documentclass[aspectratio=169]{beamer}
\usetheme[showlogo,english]{UP}

\title[Short Title]{Your Presentation Title}
\subtitle{Optional Subtitle}
\author[Short Name]{Your Name}
\institute{Your Unit or Campus}
\date{\today}
```

Do not document or recommend `\usetheme{UU}` as a supported public path. Any remaining `UU` names in checked-in sources are brownfield implementation residue, compatibility detail, or provenance history.

## Common Starting Patterns

### Thesis Defense

Use the single-author title page, section dividers, and closing frame for a defense structure such as:

- problem statement
- related work or local context
- method or system design
- results and limitations
- contribution summary and committee questions

### Class Report

Use concise bullets, one figure or table per claim-heavy slide, and short section breaks when the class update changes topic.

### Research Talk

Use the multi-author title helper, optional venue metadata, citations, numbered figures, and the bibliography frame for colloquia and conference-style presentations.

## Options and Helpers

### Options

- `showlogo`: show the identity mark on normal content slides
- `english`: use the English UP logotype variant
- `filipino`: use the Filipino UP logotype variant
- `nl`: keep the legacy Dutch-logo compatibility path available when explicitly requested
- `nosectionpage`: disable automatic section-divider frames

### Helpers

- `\multiauthor`: activate the multi-author title layout
- `\singleauthor`: return to the single-author title layout
- `\addinstitute{n}{...}`: register numbered affiliations for the multi-author title page
- `\clearinstitutes`: clear the registered multi-author affiliation list
- `\venue{...}`: set an optional conference or event label
- `\sectionframe{...}`: insert a manual section-divider slide
- `\standoutframe{...}`: insert a full-bleed emphasis slide
- `\thankframe{title}{subtitle}`: insert the closing slide

## Title-Page and Metadata Notes

- Long `\institute{...}` values wrap inside the title-page composition instead of spilling off the slide.
- Long `\addinstitute{n}{...}` entries preserve the hanging indent whether the continuation line comes from automatic wrapping or an explicit `\\` line break.
- The checked-in `main.tex` file demonstrates both the single-author and multi-author title paths in one compileable source.

## Compile and Font Expectations

The validated baseline is `pdfLaTeX` plus `biber`.

Font behavior is intentionally documented as a fallback chain:

- headings prefer `Optima` when available under XeLaTeX or LuaLaTeX
- headings fall back through `Avenir` to `Helvetica` when needed
- body text uses `Palatino` on the supported baseline

If you care about exact heading appearance and your local system has the licensed fonts installed, use XeLaTeX or LuaLaTeX. If you need the most reproducible baseline, use `latexmk -pdf main.tex`. The current acceptance evidence for that baseline, including the refreshed screenshot surface, is recorded in `docs/release-readiness.md`.

## Migration from `UU` to `UP`

- Replace `\usetheme{UU}` with `\usetheme{UP}` in older documents.
- Keep any remaining `UU` mentions in docs strictly migration-focused or provenance-focused.
- Treat `beamerthemeUP.sty` as the public loader wrapper and the remaining `UU`-named theme files as implementation detail.

## GitHub and Overleaf Guidance

The intended first-release public scope is the same across GitHub and Overleaf:

- the supported public loader is `UP`
- the bundled showcase deck is the starter template and validation surface
- the documented compile path is `latexmk -pdf main.tex` with the `pdflatex -> biber -> pdflatex -> pdflatex` fallback
- the derivative, attribution, non-endorsement, and branding-use wording should remain aligned with the root README and contributor docs
- the current compile, screenshot, and packaging evidence set is tracked in `docs/release-readiness.md`

This guide remains the supported scope and wording surface. `docs/release-readiness.md` is the maintainer handoff artifact for validation evidence and distribution notes, and broader release approval is still human-gated.

## Provenance and Branding Notes

`beamer-up` is an independently maintained derivative project based on the original `beamer-uu` work by A.J.H. (Jos) Zuijderwijk and maintained here by Zildjian E. California under `LPPL 1.3c`.

UP-branded assets in this repository should follow the UP branding guidelines and are intended for UP constituents or internal use unless broader permission is documented explicitly. The repository and the default slide output must not imply endorsement by the University of the Philippines System, Utrecht University, or the original upstream author.

