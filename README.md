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
    Version: v0.0.16
    <br />
    Status: independently maintained derivative work; the supported public <code>UP</code> loader is implemented and compile-validated, the checked-in theme now restores visible automatic section-divider titles, keeps the UP divider surface aligned across manual and automatic section pages, matches the automatic divider text treatment to the manual <code>\sectionframe</code> white-title rendering, and uses the exact horizontal white English/Filipino UP closing-slide logo files with language-specific footer crops derived from the visible logo bounds so the full mark stays visible on the beamer-uu-style feedback-page layout while still leaving release-ready packaging plus broader public validation notes in progress.
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

`beamer-up` is an unofficial University of the Philippines System Beamer theme initiative and an independent derivative work that began from the original `beamer-uu` structure and design approach. It now maintains its own project identity, governance posture, and release path for students, researchers, and faculty across the UP System.

This derivative work is maintained in this repository by Zildjian E. California. It preserves attribution to the original `beamer-uu` developer, A.J.H. (Jos) Zuijderwijk, and reflects the confirmed license basis in `LICENSE.txt`: the LaTeX Project Public License `LPPL 1.3c`. `beamer-up` should be identified as its own maintained derivative work rather than as the original `beamer-uu` release or a Utrecht University publication.

### Current Status

- `beamer-up` is maintained as its own derivative distribution by Zildjian E. California.
- Public documentation, issue handling, and repository governance apply to `beamer-up`, not to the original `beamer-uu` project.
- `beamer-up` does not claim Utrecht University affiliation, Utrecht branding compliance, or official UP System endorsement as part of its public project identity.
- The bundled showcase deck was revalidated locally on April 1, 2026 with `latexmk -pdf main.tex` from `beamer-up/`.
- The supported public loader is `\usetheme{UP}`.
- Direct `\usetheme{UU}` loading is retained only as deprecated compatibility while internal legacy names are phased down carefully.
- The checked-in theme now applies the corrected official UP core palette `#8E1537`, `#005740`, `#FFB81D`, `#231F20`, and the corresponding slide treatments across title, section, content, standout, and closing-slide surfaces.
- The supported compile baseline is `pdfLaTeX` with `biber`; `latexmk` is the recommended entry command.
- **Typography now implements a tiered fallback per UP typeface guidelines:** Palatino for body text, with Optima (preferred) → Avenir → Helvetica for headings depending on engine and availability. XeLaTeX or LuaLaTeX enables Optima on systems where it is installed; pdfLaTeX defaults to Helvetica.
- The default `showlogo` path now uses a content-slide UP lineshot-seal plus logotype lockup, with `english` as the default language variant and `filipino` available for `Unibersidad ng Pilipinas`; the non-`nl` lockup is scaled to stay inside the header band and anchored to the right content margin, while the `nl` option remains a legacy Dutch-logo compatibility path.
- Automatic section-divider slides now render the active section title again as plain white divider text, and manual `\sectionframe` dividers continue to share that same UP maroon-and-gold surface treatment.
- Title slides keep the selected UP white wordmark variant, while `\thankframe` now follows the inherited beamer-uu closing-slide geometry more closely and switches between the exact bundled horizontal white English and Filipino UP lockups using tighter language-specific trims based on the visible logo bounds so the full footer mark stays inside the page; the `nl` compatibility branch keeps its legacy fallback behavior.
- Some file names, helper names, and color tokens still reflect historical `UU` lineage; they are compatibility details rather than the intended long-term public brand.
- The theme files in this repository are distributed under `LPPL 1.3c`; institutional names, logos, and other brand assets may still involve separate usage constraints outside the software license.

### Public Naming Contract

- Canonical project identity: `beamer-up`
- Approved first-release public theme identifier: `UP`
- Current `UU` identifiers in the checked-in working tree are legacy compatibility details rather than the supported public interface
- Public docs must not present `UU` as the retained long-term supported theme alias

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
  beamerthemeUP.sty
  beamerthemeUU.sty
  beamercolorthemeUU.sty
  beamerinnerthemeUU.sty
  beamerouterthemeUU.sty
  logos/
  main.tex
  references.bib
docs/
  version-0-0-2-docs.md
  version-0-0-3-docs.md
  version-0-0-4-docs.md
  version-0-0-5-docs.md
  version-0-0-6-docs.md
  version-0-0-7-docs.md
  version-0-0-8-docs.md
  version-0-0-9-docs.md
  version-0-0-10-docs.md
  version-0-0-11-docs.md
  version-0-0-12-docs.md
  version-0-0-13-docs.md
  version-0-0-14-docs.md
  version-0-0-15-docs.md
  version-0-0-16-docs.md
  repo/images/
  project_screen.png
```

The checked-in implementation now loads through `UP`, while legacy `UU` loader support remains only as explicit deprecated compatibility. Maintainer-only workflow artifacts are intentionally omitted from this public layout summary.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

### Prerequisites

**Required:**
- A TeX distribution with `pdfLaTeX`, Beamer, PGF/TikZ, BibLaTeX, and Biber available.
- `latexmk` is recommended for local compilation.

**Typography (tiered fallback):**
The theme implements a tiered font strategy per UP typeface guidelines:

| Priority | Font | Use | Availability |
| --- | --- | --- | --- |
| 1 (preferred) | Optima | Titles and headings | Proprietary; pre-installed on macOS; licensed on some Windows systems |
| 2 (alternative) | Avenir | Titles and headings | Proprietary; common on macOS and some Windows systems |
| 3 (fallback) | Helvetica | Titles and headings | Widely available across all platforms |
| Body text | Palatino | Body copy | Included in all major TeX distributions |

**For UP guidelines compliance (Optima headings):**
- **macOS:** Optima is pre-installed. Use XeLaTeX or LuaLaTeX:
  ```sh
  latexmk -pdf -pdflatex="xelatex" main.tex
  ```
- **Windows:** Optima requires a commercial license from Monotype. If licensed and installed, use XeLaTeX or LuaLaTeX as above.
- **Linux:** Optima is not freely available. Use the fallback (Helvetica) or purchase a license.
- **All platforms (free baseline):** The default pdfLaTeX compilation uses Helvetica, which is fully functional and matches the UP guidelines for unofficial materials.

**Recommended compilation for best typography:**
```sh
# XeLaTeX (Optima if available, otherwise Avenir, then Helvetica)
latexmk -pdf -pdflatex="xelatex" main.tex

# LuaLaTeX (same fallback chain)
latexmk -pdf -pdflatex="lualatex" main.tex

# pdfLaTeX (Helvetica fallback, works everywhere)
latexmk -pdf main.tex
```

The theme automatically detects your engine and available fonts, logging which font is selected during compilation.

### Installation

1. Clone the repository and move into the theme workspace.
   ```sh
   git clone https://github.com/zcalifornia-ph/beamer-up.git
   cd beamer-up/beamer-up
   ```
2. Compile the showcase deck.
   ```sh
   latexmk -pdf main.tex
   ```
   This is the preferred and currently revalidated command path for the bundled showcase deck.
3. If `latexmk` is unavailable, run the manual sequence for the bundled bibliography example.
   ```sh
   pdflatex main.tex
   biber main
   pdflatex main.tex
   pdflatex main.tex
   ```
4. Reuse the theme files and `logos/` directory in your own presentation project, or install them into a local TeX tree as needed. If you redistribute a modified version, keep attribution, license context, provenance clarity, and non-endorsement wording intact.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

The supported public loader is now `UP`:

```tex
\documentclass[aspectratio=169]{beamer}
\usetheme[showlogo,english]{UP}

\title[Short Title]{Your Presentation Title}
\subtitle{Optional Subtitle}
\author[Short Name]{Your Name}
\institute{Your Unit or Campus}
\date{\today}
```

Migration expectations now in effect:

- `UP` is the supported public loader.
- Existing options `showlogo`, `english`, `filipino`, `nl`, and `nosectionpage` are supported on the public loader.
- Existing helper commands such as `\multiauthor`, `\singleauthor`, `\addinstitute`, `\clearinstitutes`, `\venue`, `\sectionframe`, `\standoutframe`, and `\thankframe` are expected to remain available.
- `showlogo` renders the bundled UP content-slide header lockup by default; `english` selects `University of the Philippines`, `filipino` selects `Unibersidad ng Pilipinas`, and `nl` switches to the legacy Dutch-logo compatibility path.
- Automatic section pages now render the active section title again using the same visible plain-white title treatment as manual `\sectionframe{...}` pages, and both stay visually matched to that same rule-above-title divider treatment.
- `\thankframe{...}{...}` keeps the same interface, but the UP path now follows the inherited beamer-uu feedback-page rhythm more closely and swaps between the exact bundled horizontal white English and Filipino UP lockups; `nl` keeps its legacy compatibility fallback.
- The current UP runtime uses cropped logo copies inside `beamer-up/logos/` for header/title surfaces and tighter language-specific trim-plus-height rules for the closing-slide horizontal logo files so the selected footer mark stays fully visible instead of dropping below the page edge.
- On content slides, the English and Filipino UP header lockups now pair the lineshot seal with the selected wordmark, fit inside the header band, and align the overall lockup to the same right margin used by the main content blocks; the `nl` compatibility logo keeps its legacy corner placement.
- The default visual system now uses UP maroon `#8E1537`, forest green `#005740`, yellow `#FFB81D`, and spot black `#231F20` across the checked-in showcase and theme templates.
- Any remaining `UU` compatibility path should be treated as a deprecated bridge rather than a coequal public alias.
- Direct `UU` subtheme loading remains an internal compatibility detail, not part of the intended public first-release contract.

These inherited identifiers are implementation details, not statements of project affiliation, branding policy, or upstream support.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Roadmap

- [x] Establish the derivative naming, attribution, disclaimer, and asset-governance baseline.
- [x] Reverse engineer the inherited theme structure and compile behavior.
- [x] Draft the public `UP` entry-point design and migration policy.
- [x] Implement the public `\usetheme{UP}` entry path and publish the user-facing migration notes.
- [x] Draft the UP visual-system mapping for palette, typography, logo handling, and decorative rules.
- [x] Implement the approved UP-directed slide-surface styling across the theme and showcase deck.
- [ ] Expand the showcase deck for common UP use cases such as thesis defenses, class reports, and research talks.
- [ ] Document release packaging and distribution guidance for broader reuse.
- [ ] Preserve explicit attribution, release provenance, and legal clarity for the derivative foundation.

See the [open issues](https://github.com/zcalifornia-ph/beamer-up/issues) for proposed improvements and open questions.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Immediate Next Actions

1. Prepare the validation evidence and distribution-ready packaging notes for the first release.
2. Expand the showcase deck for common UP use cases such as thesis defenses, class reports, and research talks.
3. Reconcile the public release docs and packaging guidance around the updated visual system.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributing

Contributions are welcome, especially around documentation, example slides, visual-system adaptation, legacy-compatibility cleanup, and theme polish. See `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, and `SECURITY.md` for workflow, conduct, and reporting expectations.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

The `beamer-up` theme files in this repository are an independent derivative work based on `beamer-uu` and are distributed under the LaTeX Project Public License `LPPL 1.3c`.
See `LICENSE.txt` for the full license text.

The maintainer of this repository's derivative distribution is Zildjian E. California.
If you redistribute a modified version, keep attribution clear, document the nature of your changes prominently, identify the result clearly as a modified derivative, and avoid implying support or endorsement from the original author, Utrecht University, or this repository's maintainers.
Institutional names, logos, and other brand assets may still be subject to separate usage or trademark constraints. UP-branded assets should follow the UP branding guidelines and are intended for UP constituents or internal use unless broader permission is documented explicitly.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contact

Maintainer: Zildjian E. California - [@zcalifornia_](https://twitter.com/zcalifornia_) - zecalifornia@up.edu.ph

Profiles: [LinkedIn](https://linkedin.com/in/zcalifornia) · [ORCID](https://orcid.org/0009-0002-2357-7606) · [ResearchGate](https://www.researchgate.net/profile/Zildjian-California)

Project Link: [https://github.com/zcalifornia-ph/beamer-up](https://github.com/zcalifornia-ph/beamer-up)

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Acknowledgments

- A.J.H. (Jos) Zuijderwijk for the original `beamer-uu` work and permission to pursue the derivative path that led to `beamer-up`.
- The upstream `beamer-uu` design and structure for providing the historical foundation of this separate maintained project.
- Students, researchers, and faculty across the UP System who motivate a reusable local Beamer theme.

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
