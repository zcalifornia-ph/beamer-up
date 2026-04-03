<a id="readme-top"></a>

<p align="center">
  <a href="https://github.com/zcalifornia-ph/beamer-up/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/zcalifornia-ph/beamer-up.svg?style=for-the-badge" alt="Contributors" />
  </a>
  <a href="https://github.com/zcalifornia-ph/beamer-up/network/members">
    <img src="https://img.shields.io/github/forks/zcalifornia-ph/beamer-up.svg?style=for-the-badge" alt="Forks" />
  </a>
  <a href="https://github.com/zcalifornia-ph/beamer-up/stargazers">
    <img src="https://img.shields.io/github/stars/zcalifornia-ph/beamer-up.svg?style=for-the-badge" alt="Stargazers" />
  </a>
  <a href="https://github.com/zcalifornia-ph/beamer-up/issues">
    <img src="https://img.shields.io/github/issues/zcalifornia-ph/beamer-up.svg?style=for-the-badge" alt="Issues" />
  </a>
  <a href="LICENSE.txt">
    <img src="https://img.shields.io/badge/License-LPPL%201.3c-7AC70C?style=for-the-badge" alt="License: LPPL 1.3c" />
  </a>
  <a href="https://linkedin.com/in/zcalifornia">
    <img src="https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555" alt="LinkedIn" />
  </a>
</p>

[![beamer-up screen shot][product-screenshot]](https://github.com/zcalifornia-ph/beamer-up)

<div align="center">
  <h3 align="center">beamer-up</h3>

  <p align="center">
    <strong>An unofficial Beamer theme initiative for the University of the Philippines System.</strong>
    <br />
    Version: v1.0.0
    <br />
    Status: first public release of an independently maintained derivative work with a supported public <code>UP</code> theme loader, a canonical <code>beamerthemeUP.sty</code> implementation entry backed by active <code>UP</code>-named subthemes, and a checked-in showcase that doubles as a starter template.
    <br />
    <a href="https://github.com/zcalifornia-ph/beamer-up"><strong>Explore the repository »</strong></a>
    <br />
    <br />
    <a href="repo/images/project_screen.png">View Screenshot</a>
    &middot;
    <a href="https://github.com/zcalifornia-ph/beamer-up/issues">Report Bug</a>
    &middot;
    <a href="https://github.com/zcalifornia-ph/beamer-up/issues">Request Feature</a>
  </p>
</div>

<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#current-status">Current Status</a></li>
        <li><a href="#public-naming-contract">Public Naming Contract</a></li>
        <li><a href="#supported-first-release-scope">Supported First-Release Scope</a></li>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li><a href="#repository-layout">Repository Layout</a></li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
      </ul>
    </li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#roadmap">Roadmap</a></li>
    <li><a href="#immediate-next-actions">Immediate Next Actions</a></li>
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About The Project

`beamer-up` is an unofficial University of the Philippines System Beamer theme initiative and an independently maintained derivative work that began from the original `beamer-uu` structure and design approach. It now has its own public project identity, governance baseline, and release path for students, researchers, and faculty across the UP System.

This derivative work is maintained in this repository by Zildjian E. California. It preserves attribution to the original `beamer-uu` developer, A.J.H. (Jos) Zuijderwijk, and follows the license basis recorded in `LICENSE.txt`: the LaTeX Project Public License `LPPL 1.3c`. `beamer-up` should be identified as its own maintained derivative work rather than as the original `beamer-uu` release or an official University of the Philippines System publication.

### Current Status

- `v1.0.0` is the current supported public release for this repository.
- The supported public loader is `\usetheme{UP}`.
- `beamerthemeUP.sty` owns the canonical theme implementation directly and loads the active `beamercolor`, `beamerinner`, and `beamerouter` `UP` subtheme files.
- No legacy `UU` wrapper or loader file is part of the maintained first-release surface.
- The checked-in showcase deck under `beamer-up/` now doubles as a starter template for thesis defenses, class reports, and research talks.
- The showcase still exercises title pages, section-divider slides, standout slides, thank-you slides, optional-logo behavior, bibliography rendering, and multi-author metadata flow through the supported `UP` path.
- This README and the checked-in starter deck are the public onboarding surface for the first release.
- Historical `0.x` preparation-cycle narratives are preserved internally as release-trace material without changing the current public contract.
- The checked-in title-page layout keeps multiline single-author and multi-author metadata inside a bounded cover composition, including wrapped long-form conference affiliations whose continuation lines stay in the same hanging-indent column for both automatic wraps and explicit `\\` line breaks.
- The current checked-in visual system uses the UP core palette `#8E1537`, `#005740`, `#FFB81D`, `#231F20`, with runtime-selected English and Filipino UP logo paths for the supported presentation surfaces.
- The recommended compile command is `latexmk -pdf main.tex` from `beamer-up/`; the documented fallback is `pdflatex`, `biber`, `pdflatex`, `pdflatex`.
- The supported typography baseline is Palatino for body text plus a tiered heading fallback of Optima -> Avenir -> Helvetica depending on engine and local font availability.
- The approved first-release scope is complete, and the final first-release readiness gate was approved and closed on April 3, 2026.
- First-release validation evidence, screenshot proof, and packaging notes are already part of the maintained release record rather than an open approval handoff.
- `beamer-up` does not imply endorsement by the University of the Philippines System, Utrecht University, or A.J.H. (Jos) Zuijderwijk.
- UP-branded assets in this repository should follow the UP branding guidelines and are intended for UP constituents or internal use unless broader permission is documented explicitly.

### Public Naming Contract

- Canonical project identity: `beamer-up`
- Supported public theme identifier: `UP`
- Public docs and examples should point users to `UP`, not `UU`
- Any remaining `UU` names in the repository are limited to legacy implementation residue, inherited asset basenames, or historical provenance markers

### Supported First-Release Scope

- checked-in theme source under `beamer-up/`
- checked-in showcase and starter deck at `beamer-up/main.tex`
- root `README.md`, `CHANGELOG.md`, and the governance docs as the public quick-start, release, and policy surfaces
- supported GitHub and Overleaf wording for the `UP` entry path and branding disclaimer posture
- validation evidence and distribution-ready packaging notes are already closed for the first release baseline

### Built With

* [![LaTeX][LaTeX]][LaTeX-url]
* [![pdfLaTeX][pdfLaTeX]][pdfLaTeX-url]
* [![Beamer][Beamer]][Beamer-url]
* [![BibLaTeX][BibLaTeX]][BibLaTeX-url]
* [![TikZ / PGF][TikZ]][TikZ-url]
* [![Biber][Biber]][Biber-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Repository Layout

```text
beamer-up/
  README.md
  CHANGELOG.md
  CODE_OF_CONDUCT.md
  CONTRIBUTING.md
  SECURITY.md
  LICENSE.txt
  repo/
    images/
      project_screen.png
  beamer-up/
    beamerthemeUP.sty
    beamercolorthemeUP.sty
    beamerinnerthemeUP.sty
    beamerouterthemeUP.sty
    main.tex
    references.bib
    logos/
```

Public-facing docs intentionally omit ignored workflow scaffolding, internal planning/traceability artifacts, legacy-loader residue that is no longer part of the maintained public contract, editor-local files, and local build artifacts.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

### Prerequisites

**Required:**

- A TeX distribution with `pdfLaTeX`, Beamer, PGF/TikZ, BibLaTeX, and Biber available.
- `latexmk` is recommended for local compilation.

**Typography (tiered fallback):**

| Priority | Font | Use | Availability |
| --- | --- | --- | --- |
| 1 (preferred) | Optima | Titles and headings | Proprietary; pre-installed on macOS; licensed on some Windows systems |
| 2 (alternative) | Avenir | Titles and headings | Proprietary; common on macOS and some Windows systems |
| 3 (fallback) | Helvetica | Titles and headings | Widely available across all platforms |
| Body text | Palatino | Body copy | Included in all major TeX distributions |

**Recommended compilation modes:**

```sh
# XeLaTeX or LuaLaTeX for Optima when the font is installed locally
latexmk -pdf -pdflatex="xelatex" main.tex
latexmk -pdf -pdflatex="lualatex" main.tex

# pdfLaTeX baseline
latexmk -pdf main.tex
```

### Installation

1. Clone the repository and move into the theme workspace.
   ```sh
   git clone https://github.com/zcalifornia-ph/beamer-up.git
   cd beamer-up/beamer-up
   ```
2. Compile the showcase deck with the recommended command.
   ```sh
   latexmk -pdf main.tex
   ```
3. If `latexmk` is unavailable, use the documented fallback sequence.
   ```sh
   pdflatex main.tex
   biber main
   pdflatex main.tex
   pdflatex main.tex
   ```
4. Reuse the theme files and `logos/` directory in your own presentation project, or install them into a local TeX tree as needed. The root docs and checked-in starter deck describe the supported loader, compile flow, and branding posture. If you redistribute a modified version, keep attribution, derivative provenance, license context, and non-endorsement wording intact.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

The supported public loader is `UP`:

```tex
\documentclass[aspectratio=169]{beamer}
\usetheme[showlogo,english]{UP}

\title[Short Title]{Your Presentation Title}
\subtitle{Optional Subtitle}
\author[Short Name]{Your Name}
\institute{Your Unit or Campus}
\date{\today}
```

For a fuller walkthrough, inspect the checked-in starter deck at `beamer-up/main.tex` alongside the public contract in this README.

Supported public use cases currently covered by the tracked docs and showcase include:

- thesis defenses
- class reports
- research talks and colloquia

Supported user-facing options and helpers currently exercised by the checked-in showcase include:

- Options: `showlogo`, `english`, `filipino`, `nosectionpage`
- Title helpers: `\multiauthor`, `\singleauthor`, `\addinstitute`, `\clearinstitutes`, `\venue`
- Special frames: `\sectionframe`, `\standoutframe`, `\thankframe`

Title-page behavior note:

- Long `\institute{...}` values and long `\addinstitute{n}{...}` conference affiliations wrap inside the title-page content block instead of overrunning the slide.
- Multi-line conference affiliations continue after the affiliation number with a hanging indent whether the second line is created by automatic wrapping or by an explicit `\\` inside the affiliation text.

Migration note:

- If you have older material that still uses `\usetheme{UU}`, update it to `\usetheme{UP}`.
- Do not document or recommend `UU` as a supported public loader.
- Remaining `UU` identifiers in the repository exist for brownfield continuity, inherited asset naming, or historical provenance and should be treated as internal detail.

Compile and distribution note:

- Recommended compile command: `latexmk -pdf main.tex` from `beamer-up/`.
- Documented fallback command chain: `pdflatex`, `biber`, `pdflatex`, `pdflatex`.
- GitHub and Overleaf surfaces should describe the same supported `UP` entry path, derivative provenance, and branding-use disclaimer posture.
- Current validation evidence, refreshed screenshot proof, and distribution-readiness notes are already part of the first-release record.

Branding note:

- The shipped UP-branded assets are for derivative theme use within the repository's current governance posture.
- Use of UP names, logos, and other marks should follow UP branding guidance and any separate permission requirements outside `LPPL 1.3c`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Roadmap

- [x] Establish the derivative naming, attribution, disclaimer, and asset-governance baseline.
- [x] Reverse engineer the inherited theme structure and compile behavior.
- [x] Define the public `UP` entry-point design and migration policy.
- [x] Implement the public `\usetheme{UP}` entry path and update the public usage contract.
- [x] Define the UP visual-system mapping for palette, typography, logo handling, and decorative rules.
- [x] Apply the approved UP-directed slide-surface styling across the theme and showcase deck.
- [x] Expand the showcase deck into a starter template for thesis defenses, class reports, and research talks.
- [x] Consolidate public usage, migration, and distribution-scope guidance in the root public docs and checked-in starter materials.
- [x] Finalize validation evidence and distribution-ready packaging notes for GitHub and Overleaf.
- [x] Close the first-release readiness and approval gate for broader distribution handoff.
- [ ] Broaden multi-engine validation beyond the current supported baseline.
- [ ] Continue safe cleanup of inherited internal `UU` identifiers where that does not change the public `UP` contract.
- [ ] Expand the starter deck and packaging notes for more academic presentation patterns after the first release.

See the [open issues](https://github.com/zcalifornia-ph/beamer-up/issues) for proposed improvements and open questions.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Immediate Next Actions
1. Decide whether the broader public package should remain pdfLaTeX-first only or add wider XeLaTeX and LuaLaTeX validation evidence.
2. Continue removing inherited internal `UU` identifiers where that cleanup is safe and does not alter the public `UP` contract.
3. Keep GitHub and Overleaf distribution text aligned with the same provenance, disclaimer, and asset-governance posture used for the first release.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributing

Contributions are welcome, especially around documentation, example slides, visual-system adaptation, compatibility cleanup, and theme polish. See `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, and `SECURITY.md` for workflow, conduct, and reporting expectations.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

The `beamer-up` theme files in this repository are an independent derivative work based on `beamer-uu` and are distributed under the LaTeX Project Public License `LPPL 1.3c`. See `LICENSE.txt` for the full license text.

If you redistribute a modified version, keep attribution clear, identify the result clearly as a modified derivative, and avoid implying support or endorsement from the original author, Utrecht University, the University of the Philippines System, or this repository's maintainers.

Institutional names, logos, and other brand assets may still be subject to separate usage or trademark constraints. UP-branded assets should follow the UP branding guidelines and are intended for UP constituents or internal use unless broader permission is documented explicitly.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contact

Maintainer: Zildjian E. California - [@zcalifornia_](https://twitter.com/zcalifornia_) - zecalifornia@up.edu.ph

Profiles: [LinkedIn](https://linkedin.com/in/zcalifornia) · [ORCID](https://orcid.org/0009-0002-2357-7606) · [ResearchGate](https://www.researchgate.net/profile/Zildjian-California)

Project Link: [https://github.com/zcalifornia-ph/beamer-up](https://github.com/zcalifornia-ph/beamer-up)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

- A.J.H. (Jos) Zuijderwijk for the original `beamer-uu` work and the derivative foundation it provided.
- Students, researchers, and faculty across the UP System who motivate a reusable local Beamer theme.
- The Beamer, PGF/TikZ, BibLaTeX, and broader LaTeX communities that make derivative theme work practical.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

[contributors-shield]: https://img.shields.io/github/contributors/zcalifornia-ph/beamer-up.svg?style=for-the-badge
[contributors-url]: https://github.com/zcalifornia-ph/beamer-up/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/zcalifornia-ph/beamer-up.svg?style=for-the-badge
[forks-url]: https://github.com/zcalifornia-ph/beamer-up/network/members
[stars-shield]: https://img.shields.io/github/stars/zcalifornia-ph/beamer-up.svg?style=for-the-badge
[stars-url]: https://github.com/zcalifornia-ph/beamer-up/stargazers
[issues-shield]: https://img.shields.io/github/issues/zcalifornia-ph/beamer-up.svg?style=for-the-badge
[issues-url]: https://github.com/zcalifornia-ph/beamer-up/issues
[LaTeX]: https://img.shields.io/badge/LaTeX-008080?style=for-the-badge&logo=latex&logoColor=white
[LaTeX-url]: https://www.latex-project.org/
[pdfLaTeX]: https://img.shields.io/badge/pdfLaTeX-0E7490?style=for-the-badge&logo=latex&logoColor=white
[pdfLaTeX-url]: https://www.overleaf.com/learn/latex/PdfLaTeX
[Beamer]: https://img.shields.io/badge/Beamer-1F2937?style=for-the-badge&logo=latex&logoColor=white
[Beamer-url]: https://ctan.org/pkg/beamer
[BibLaTeX]: https://img.shields.io/badge/BibLaTeX-2563EB?style=for-the-badge&logo=latex&logoColor=white
[BibLaTeX-url]: https://ctan.org/pkg/biblatex
[TikZ]: https://img.shields.io/badge/TikZ%20%2F%20PGF-0F766E?style=for-the-badge&logo=latex&logoColor=white
[TikZ-url]: https://ctan.org/pkg/pgf
[Biber]: https://img.shields.io/badge/Biber-7C3AED?style=for-the-badge&logo=latex&logoColor=white
[Biber-url]: https://ctan.org/pkg/biber
[product-screenshot]: repo/images/project_screen.png

