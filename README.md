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
    <strong>An unofficial beamer theme for the University of the Philippines System.</strong>
    <br />
    Version: v0.0.2
    <br />
    Status: independently maintained derivative work with brownfield and governance baselines established; public interface migration to <code>UP</code> is pending.
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
    <li><a href="#contributing">Contributing</a></li>
    <li><a href="#license">License</a></li>
    <li><a href="#contact">Contact</a></li>
    <li><a href="#acknowledgments">Acknowledgments</a></li>
  </ol>
</details>

## About The Project

`beamer-up` is an unofficial University of the Philippines System Beamer theme initiative and an independent derivative work that began from the original `beamer-uu` structure and design approach. It now maintains its own project identity, repository governance, and release path for students, researchers, and faculty across the UP System.

This derivative work is maintained in this repository by Zildjian E. California. It preserves attribution to the original `beamer-uu` developer, A.J.H. (Jos) Zuijderwijk, and reflects the confirmed license basis in `LICENSE.txt`: the LaTeX Project Public License `LPPL 1.3c`. `beamer-up` should be identified as its own maintained derivative work rather than as the original `beamer-uu` release or a Utrecht University publication.

### Current Status

- `beamer-up` is maintained as its own derivative distribution by Zildjian E. California.
- Public documentation, issue handling, and repository governance apply to `beamer-up`, not to the original `beamer-uu` project.
- `beamer-up` does not claim Utrecht University affiliation, Utrecht branding compliance, or Utrecht logo usage as part of its public project identity.
- Brownfield reverse-engineering artifacts for the inherited theme implementation now live under `beamer-up/ai-dlc-docs/design-artifacts/U-B/`.
- The naming, attribution, and branding-governance source of truth for the upcoming `UP` migration now lives at `beamer-up/docs/identity-governance.md`.
- Some internal file names and implementation identifiers still reflect the historical source lineage; they remain compatibility details and attribution anchors rather than the current public branding of the project.
- The theme files in this repository are distributed under `LPPL 1.3c`; logo and institutional-brand usage may still involve separate constraints outside the software license.

### Public Naming Contract

- Canonical project identity: `beamer-up`
- Approved first-release public theme identifier: `UP`
- Current `UU` identifiers in the checked-in working tree are transitional brownfield details until the public-interface migration lands.
- First-release public docs must not present `UU` as the retained long-term supported theme alias.

### Branding and Distribution Guidance

- GitHub and Overleaf distribution surfaces must identify `beamer-up` as an independently maintained derivative based on `beamer-uu`.
- UP-branded assets or template packages should follow the UP branding guidelines and are intended for UP constituents/internal use unless broader permission is documented explicitly.
- Public wording must not imply official UP System endorsement, Utrecht University ownership of this derivative, or upstream continuity.
- The current wording baseline for these surfaces is recorded in `beamer-up/docs/identity-governance.md`.

### Built With

* [![LaTeX][LaTeX]][LaTeX-url]
* [![XeLaTeX][XeLaTeX]][XeLaTeX-url]
* [![Beamer][Beamer]][Beamer-url]
* [![BibLaTeX][BibLaTeX]][BibLaTeX-url]
* [![TikZ / PGF][TikZ]][TikZ-url]
* [![Biber][Biber]][Biber-url]

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Repository Layout

```text
beamer-up/
  ai-dlc-docs/
    design-artifacts/
  docs/
    identity-governance.md
  beamerthemeUU.sty
  beamerinnerthemeUU.sty
  beamerouterthemeUU.sty
  beamercolorthemeUU.sty
  logos/
  main.tex
  references.bib
  REQUIREMENTS.md
repo/images/
  project_screen.png
docs/
  version-0-0-2-docs.md
```

The theme source currently remains in the `beamer-up/` subdirectory. The checked-in implementation still loads as `UU` because the public-interface migration has not yet been completed.
The approved first-release public theme identifier is `UP`; current `UU` names in the working tree are transitional brownfield state only and should be read together with the migration guidance in `beamer-up/docs/identity-governance.md`.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Getting Started

### Prerequisites

- A TeX distribution with Beamer, PGF/TikZ, BibLaTeX, and Biber available.
- `latexmk` is recommended for local compilation.
- Optional font packages `merriweather` and `opensans` for the intended typographic look. The theme falls back to Palatino and the default sans-serif family if they are unavailable.

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
3. If `latexmk` is unavailable, run the manual sequence for the bundled bibliography example.
   ```sh
   pdflatex main.tex
   biber main
   pdflatex main.tex
   pdflatex main.tex
   ```
4. Reuse the theme files and `logos/` directory in your own presentation project, or install them into a local TeX tree as needed. If you redistribute a modified version, keep the provenance and license context intact.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Usage

The current working tree still exposes inherited `UU` identifiers in the theme interface. This snippet documents the present brownfield state only; the approved first-release public contract is `UP`, and `UU` is not intended to remain the supported long-term public alias once the migration lands.

```tex
\documentclass[aspectratio=169]{beamer}
\usetheme[showlogo]{UU}

\title[Short Title]{Your Presentation Title}
\subtitle{Optional Subtitle}
\author[Short Name]{Your Name}
\institute{Your Unit or Campus}
\date{\today}
```

Useful options and helpers already present in the baseline:

- `showlogo` to show the small corner logo on content slides.
- `nl` as a legacy upstream option that remains in the implementation.
- `nosectionpage` to suppress automatic section divider slides.
- `\multiauthor`, `\addinstitute{}`, and `\venue{}` for conference-style title slides.
- `\sectionframe{}`, `\standoutframe{}`, and `\thankframe{}{}` for common presentation transitions.

Migration-note requirements for first-release docs:

- switch public examples to `\usetheme{UP}` once the interface migration lands
- label any remaining `UU` example as transitional brownfield behavior only
- keep derivative attribution and the UP branding-use disclaimer aligned across GitHub and Overleaf distribution surfaces

These inherited identifiers are implementation details, not statements of project affiliation, branding policy, or upstream support.
If you adapt the theme further, keep attribution to the original `beamer-uu` work, mark your modifications clearly, avoid implying upstream or institutional endorsement, and audit any logo or branding assets before redistributing them. See `beamer-up/docs/identity-governance.md` for the wording baseline that downstream interface and packaging work must satisfy.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Roadmap

- [x] Capture brownfield static and dynamic models for the inherited `UU` implementation.
- [x] Establish the naming, attribution, and branding-governance baseline for the `UP` migration.
- [ ] Implement the public `\usetheme{UP}` entry path and publish the user-facing migration notes.
- [ ] Expand the example deck for common UP use cases such as thesis defenses, class reports, and research talks.
- [ ] Document TeX-tree installation and packaging guidance for broader reuse.
- [ ] Preserve explicit attribution, release provenance, and legal clarity for the derivative foundation.

See the [open issues](https://github.com/zcalifornia-ph/beamer-up/issues) for proposed improvements and open questions.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## Contributing

Contributions are welcome, especially around documentation, example slides, legacy-interface cleanup, and theme polish. See `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, and `SECURITY.md` for workflow, conduct, and reporting expectations.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

## License

The `beamer-up` theme files in this repository are an independent derivative work based on `beamer-uu` and are distributed under the LaTeX Project Public License `LPPL 1.3c`.
See `LICENSE.txt` for the full license text.

The maintainer of this repository's derivative distribution is Zildjian E. California.
If you redistribute a modified version, keep attribution clear, document the nature of your changes prominently, identify the result clearly as a modified derivative, and avoid implying support or endorsement from the original author, Utrecht University, or this repository's maintainers.
Institutional names, logos, and other brand assets may still be subject to separate usage or trademark constraints. UP-branded assets should follow the UP branding guidelines and are intended for UP constituents/internal use unless broader permission is documented explicitly.

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
[XeLaTeX]: https://img.shields.io/badge/XeLaTeX-0E7490?style=for-the-badge&logo=latex&logoColor=white
[XeLaTeX-url]: https://www.overleaf.com/learn/latex/XeLaTeX
[Beamer]: https://img.shields.io/badge/Beamer-1F2937?style=for-the-badge&logo=latex&logoColor=white
[Beamer-url]: https://ctan.org/pkg/beamer
[BibLaTeX]: https://img.shields.io/badge/BibLaTeX-2563EB?style=for-the-badge&logo=latex&logoColor=white
[BibLaTeX-url]: https://ctan.org/pkg/biblatex
[TikZ]: https://img.shields.io/badge/TikZ%20%2F%20PGF-0F766E?style=for-the-badge&logo=latex&logoColor=white
[TikZ-url]: https://ctan.org/pkg/pgf
[Biber]: https://img.shields.io/badge/Biber-7C3AED?style=for-the-badge&logo=latex&logoColor=white
[Biber-url]: https://ctan.org/pkg/biber
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: https://linkedin.com/in/zcalifornia
[product-screenshot]: repo/images/project_screen.png


