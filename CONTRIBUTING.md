# Contributing

Thanks for contributing to `beamer-up`.
This repository is an unofficial University of the Philippines System Beamer theme initiative, independently maintained by Zildjian E. California, and derived from the `beamer-uu` baseline under `LPPL 1.3c`.
The supported public theme loader is `UP`; any remaining `UU` naming in the tree is brownfield implementation residue or historical/internal detail rather than the intended public contract.
Contributions should improve `beamer-up` as its own maintained project while preserving attribution clarity, clear modification history, and defensible branding decisions.

## Values Framework

Contributions should support these working values:

- leadership through transparent, constructive collaboration
- professionalism through ethical practice and accurate attribution
- expertise through strong technical, design, and documentation quality
- inquiry through evidence, testing, and open learning
- service through useful outcomes for students, researchers, and faculty
- diversity through inclusive and rights-respecting participation
- collaboration through interdisciplinary and cross-functional teamwork
- sustainability through maintainable and responsible engineering

## Licensing and Attribution

- By submitting a contribution, you agree that your changes may be distributed with this work under `LPPL 1.3c`.
- Keep attribution to the original `beamer-uu` basis and to later contributors accurate.
- When you modify upstream-derived theme files, clearly describe the nature of the change so recipients can distinguish your derivative from upstream material.
- Do not represent `beamer-up` or any modified distribution as the unmodified upstream theme, and do not imply support or endorsement that does not exist.
- Treat `beamer-up` as an independent derivative project; do not reintroduce Utrecht-branded positioning, logo policy claims, or statements that this repository follows Utrecht University branding guidance.
- Institutional names, logos, and brand assets may require separate permission or policy compliance beyond the software license.

## Naming and Branding Contract

- Public project identity remains `beamer-up`.
- Approved first-release public theme identifier is `UP`.
- Current `UU` identifiers in checked-in sources are brownfield implementation residue; do not introduce new public-facing `UU` expectations unless you are documenting migration history explicitly.
- When you mention inherited `UU` behavior, direct readers to `UP` as the supported loader and do not present a legacy `UU` wrapper or loader path as part of the maintained public interface.
- GitHub release text, repository docs, and Overleaf descriptions that mention UP-branded assets must preserve derivative provenance, non-endorsement wording, and the internal-use branding disclaimer when applicable.
- If your change affects branding, attribution, or packaged assets, keep the corresponding governance or inventory notes in sync as part of the same change set.

## Before You Start

- Review open issues and pull requests to avoid duplicate work.
- Open an issue first for substantial branding, packaging, or public-interface changes.
- Keep changes focused and easy to review.
- Preserve clear attribution to the original `beamer-uu` work and do not remove or obscure license context unless maintainers explicitly direct otherwise.
- Do not switch new public examples, quick starts, screenshots, or migration guidance back to `\usetheme{UU}`.
- Keep `README.md`, `docs/usage-guide.md`, and `docs/release-readiness.md` aligned when you change public quick-start, compile-validation, migration, or distribution wording.
- If you modify distributed theme components, record the change clearly in the file, pull request, or companion documentation.
- Do not imply support, sponsorship, or endorsement from the original author, Utrecht University, the University of the Philippines System, or repository maintainers unless maintainers explicitly approve that wording.
- If you add or replace logos, fonts, or institutional assets, make sure you have the right to use and redistribute them.
- If you add, replace, remove, or repackage logo assets, include provenance, redistribution basis, and disclaimer impact in the same change.
- Confirm your contribution aligns with `CODE_OF_CONDUCT.md` and `SECURITY.md`.

## Recommended Contribution Areas

- Visual-system adaptation and cleanup that reduce remaining Utrecht-facing language or styling where it can be done safely.
- Documentation and onboarding improvements for local TeX users.
- Example slide decks and showcase content for common academic use cases.
- Theme cleanup, macro polish, and compatibility fixes in the `.sty` files.
- Attribution, provenance, and release-packaging clarity for derivative assets.

## Validation Expectations

- Compile the showcase deck before opening a pull request.
  ```sh
  cd beamer-up
  latexmk -pdf main.tex
  ```
- If `latexmk` is unavailable, use the manual compile sequence:
  ```sh
  pdflatex main.tex
  biber main
  pdflatex main.tex
  pdflatex main.tex
  ```
- Include screenshots, PDF excerpts, or visual diffs when your change affects slide output.
- Note any font or package assumptions needed to reproduce the result.
- Do not commit generated local build artifacts from LaTeX compilation.

## Pull Requests

Open a pull request containing:

- the problem statement or motivation
- a short summary of the approach
- validation evidence such as compile output, screenshots, or PDF comparisons
- any risks, tradeoffs, or compatibility notes
- attribution or licensing notes when assets, branding, or upstream-derived material changed
- a short description of any modification notices or provenance cues needed for LPPL-compliant redistribution
- any governance, inventory, or release-note updates required by the change

## Branch Naming

- Use kebab-case.
- Start with a Conventional Commit type.
- Keep names concise and descriptive.

Example:

```text
docs/init-repo-governance
```

## Commit Conventions

Use Conventional Commits.
Examples:

```text
feat: add conference title page helper
fix: correct section divider spacing
docs: initialize project governance docs
```

Common types:

- `feat`
- `fix`
- `docs`
- `refactor`
- `test`
- `chore`

## Merge Strategy

Use short-lived branches and squash before merge unless project maintainers specify otherwise.

- Keep each pull request scoped to one logical change.
- Use a final squashed commit message that clearly describes the full change.
- Ensure requested review changes and validation steps are resolved before merge.

## Security Reporting

Do not report vulnerabilities in public issues.
Follow `SECURITY.md` for coordinated disclosure.

## Community Conduct

Participation requires compliance with `CODE_OF_CONDUCT.md`.
