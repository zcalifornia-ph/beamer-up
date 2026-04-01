# Contributing

Thanks for contributing to `beamer-up`.
This repository is an unofficial University of the Philippines System Beamer theme initiative, independently maintained by Zildjian E. California, and derived from the `beamer-uu` baseline under `LPPL 1.3c`.
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
- Current `UU` identifiers in checked-in sources are transitional brownfield details; do not introduce new public-facing `UU` expectations unless you label them explicitly as transitional and migration-sensitive.
- When you document current inherited `UU` behavior before the migration lands, pair it with migration-note language toward `UP`.
- GitHub release text, repository docs, and Overleaf descriptions that mention UP-branded assets must include the branding-guidelines/internal-use disclaimer and the non-endorsement posture defined for this derivative.
- Use `beamer-up/docs/identity-governance.md` as the wording baseline for naming, attribution order, and disclaimer language.
- Use `beamer-up/docs/asset-governance.md` as the inventory baseline for shipped logo assets, generated outputs, and package-surface requirements.

## Before You Start
- Review open issues and pull requests to avoid duplicate work.
- Open an issue first for substantial branding, packaging, or public-interface changes.
- Keep changes focused and easy to review.
- Preserve clear attribution to the original `beamer-uu` work and do not remove or obscure license context unless maintainers explicitly direct otherwise.
- If you modify distributed theme components, record the change clearly in the file, pull request, or companion documentation.
- Do not imply support, sponsorship, or endorsement from the original author, Utrecht University, the University of the Philippines System, or repository maintainers unless maintainers explicitly approve that wording.
- If you add or replace logos, fonts, or institutional assets, make sure you have the right to use and redistribute them.
- If you add, replace, remove, or repackage logo assets, update `beamer-up/docs/asset-governance.md` in the same change.
- Confirm your contribution aligns with `CODE_OF_CONDUCT.md` and `SECURITY.md`.

## Recommended Contribution Areas

- Public-interface cleanup that reduces reliance on legacy upstream identifiers where it can be done safely.
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
- any required `beamer-up/docs/asset-governance.md` updates when logo inventories or package surfaces changed

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

