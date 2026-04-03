# Version v0.3.0 Documentation

## Title
Published the `v0.3.0` Starter-Template and Usage-Guide Baseline

## Quick Diagnostic Read

This release turns the checked-in repository from a documented showcase into a more usable public starting point.
It does five concrete things:

- publishes `v0.3.0` as the new public documentation baseline,
- promotes `beamer-up/main.tex` into the tracked starter template for common UP academic talk formats,
- adds `docs/usage-guide.md` as the public quick-start and migration guide,
- aligns `README.md`, `CONTRIBUTING.md`, and `SECURITY.md` to that new baseline,
- records the compile-validation posture for the updated deck.

## One-Sentence Objective

Make the checked-in `beamer-up` repository usable as a real starter surface for UP presentations while keeping the supported public contract centered on `\usetheme{UP}` and preserving derivative provenance, disclaimer, and branding guidance.

## Why This Version Matters

The earlier `v0.2.0` baseline accurately described the repository's identity, migration status, and visual direction, but it still left an onboarding gap.
A new user could see that the theme was real, but still had to infer how to start a thesis defense, class report, or research talk from the showcase source.

`v0.3.0` closes that gap.

The bundled `main.tex` file is now intentionally framed as both:

- a compile-validation surface for the checked-in theme, and
- a starter template for common UP academic presentation patterns.

The new `docs/usage-guide.md` complements that by pulling the public quick-start, migration, compile expectations, and GitHub/Overleaf wording into one tracked guide.

## Plan A / Plan B

### Plan A (Recommended)

1. Treat the showcase deck as the public starter template.
2. Publish one public usage guide that explains the supported `UP` loader, migration posture, and compile workflow.
3. Update the root docs and governance wording so contributors and users follow the same public contract.
4. Keep release-readiness work explicit as a later step rather than pretending packaging proof is already finished.

### Plan B

1. Leave the deck as a showcase-only artifact.
2. Continue splitting quick-start and migration details across README fragments and internal context.
3. Delay a version bump until release-readiness proof is complete.

Plan B is lower effort in the short term, but it keeps the public onboarding surface weaker than the checked-in repository now deserves.

## System View

```text
supported public loader: UP
  -> checked-in deck demonstrates the public interface
  -> checked-in deck now also acts as the starter template
  -> usage guide explains quick start, migration, compile, and distribution wording
  -> release-readiness evidence and packaging proof remain later work
```

## Artifact Map

### Root docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `SECURITY.md`

### New public docs added in this version

- `docs/usage-guide.md`
- `docs/version-0-3-0-docs.md`

### Checked-in showcase/template surface updated in this version

- `beamer-up/main.tex`

## Detailed Walkthrough

## 1) `main.tex` now serves two public roles

Before this version, the checked-in deck primarily read as a showcase of the current theme behavior.
That was still useful, but it left some uncertainty about how much of the file was demonstration-only and how much was intended as a reusable starting point.

This release makes that intent explicit.

The checked-in source now demonstrates starter patterns for:

- thesis defenses,
- class reports,
- research talks and colloquia.

It still keeps the important validation surfaces visible:

- the supported `UP` theme loader,
- the multi-author title path,
- title-page wrapping behavior,
- section-divider frames,
- standout and thank-you frames,
- figures, tables, code, diagrams, and bibliography flow.

That means the same file now helps both maintainers and end users.

## 2) The new usage guide consolidates the public onboarding contract

`docs/usage-guide.md` exists to prevent README sprawl while still keeping the public entry path explicit.

The guide now covers:

- the supported `\usetheme{UP}` entry path,
- common starting patterns for academic talks,
- supported options and helper macros,
- title-page and metadata behavior,
- compile and font expectations,
- migration from `UU` to `UP`,
- GitHub and Overleaf wording expectations,
- derivative provenance and branding notes.

That makes the root README easier to scan while still giving users a concrete, tracked reference page.

## 3) Root governance docs now match the starter-template baseline

The root README now describes `v0.3.0` rather than `v0.2.0` as the current public documentation baseline.
It also treats showcase/docs integration as completed baseline work rather than as a future aspiration.

`CONTRIBUTING.md` was updated for the same reason.
Contributors are now told directly to keep `README.md` and `docs/usage-guide.md` aligned whenever public quick-start, migration, or distribution wording changes.

`SECURITY.md` was updated as well so the supported-version matrix is not left behind on the earlier baseline.

## 4) This release still does not claim full release-readiness proof

`v0.3.0` improves the public starting surface substantially, but it does not close the remaining release-readiness work.

The following still remain later tasks:

- broader compile-evidence collection,
- screenshot or PDF-based release evidence,
- final GitHub and Overleaf distribution-ready packaging proof.

That boundary matters because the docs should be more usable now without overstating the project's distribution maturity.

## Validation

Validation for this version used the updated checked-in deck and the documented compile workflow.

Observed compile path:

1. `latexmk -pdf main.tex` was attempted first from `beamer-up/`.
2. The validated fallback sequence was then used successfully:
   - `pdflatex -interaction=nonstopmode main.tex`
   - `biber main`
   - `pdflatex -interaction=nonstopmode main.tex`
   - `pdflatex -interaction=nonstopmode main.tex`

Result:

- `main.pdf` was generated successfully at 28 pages.
- The working tree now contains generated local build outputs and compile-validation artifacts that should not be committed as release materials.

Non-blocking warnings remained in the local compile log, including:

- `hyperref` PDF-string warnings,
- repeated `pdfauthor` warnings from title-page mode switches,
- several `Underfull \hbox` warnings on documentation-heavy slides,
- MiKTeX logging warnings in the local environment.

## Pitfalls and Debugging Notes

### 1) A starter template should still preserve validation value

Turning the checked-in deck into a starter template should not remove the stress cases that make it valuable for theme verification.
This version keeps both goals in the same file.

### 2) Public docs should point to one supported loader only

The repository may still contain `UU`-named implementation files for brownfield continuity, but public onboarding must continue to direct users to `UP`.

### 3) A version bump should reflect a real public-surface improvement

This is not just a wording cleanup.
The repository now offers a clearer reusable entry point plus a dedicated guide, which is why `v0.3.0` is a better fit than another narrow patch marker.

## Practice Task

Open `README.md`, `docs/usage-guide.md`, and `beamer-up/main.tex`, then answer these three questions without using any internal planning artifacts:

1. What is the supported public loader?
2. Which three common academic use cases now have starter guidance?
3. What release-readiness work is still intentionally left for later?

If those answers are easy to extract, the public onboarding contract is doing its job.

## Next 24-72 Hours

1. Capture broader compile logs, PDF references, and visual review artifacts for the current baseline.
2. Reconcile GitHub and Overleaf packaging wording against the asset-governance and disclaimer baseline.
3. Decide which release-readiness artifacts should be retained publicly and which should stay local-only.
