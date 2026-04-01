# Version v0.0.2 Documentation

## Title
Brownfield Baseline and Naming-Governance Lock-In for `beamer-up`

## Quick Diagnostic Read

This version does not yet change the public runtime interface from `UU` to `UP`.
What it does is establish the prerequisites for doing that safely:

- brownfield static and dynamic models for the inherited theme implementation,
- a named governance baseline for identity, attribution, and disclaimer wording,
- public root-doc updates so the repository describes the current migration posture truthfully,
- traceability that links the governance work back to stories, NFRs, risks, and downstream build steps.

## One-Sentence Objective

Make the current Utrecht-derived theme understandable and make the upcoming `UP` rebrand governable before changing the actual user-facing loader and implementation contracts.

## Why This Version Matters

Without this version, later migration work would still be guessing about:

- where the inherited `UU` coupling really lives,
- which wording is approved for derivative attribution and non-endorsement,
- what GitHub and Overleaf distribution text must say when UP-branded assets are shipped,
- which build artifacts are merely observational and should not be treated as source of truth.

This version reduces that ambiguity.

## Plan A / Plan B

### Plan A (Recommended)

1. Read `beamer-up/ai-dlc-docs/design-artifacts/U-B/static-model.md`.
2. Read `beamer-up/ai-dlc-docs/design-artifacts/U-B/dynamic-model.md`.
3. Read `beamer-up/docs/identity-governance.md`.
4. Read `beamer-up/docs/traceability/U-A/b-ua-01-traceability.md`.

### Plan B

1. Read the updated root `README.md` for the public-facing posture.
2. Read `CHANGELOG.md` for the short release summary.
3. Use this document as the detailed bridge between those artifacts and the underlying work.

## System View

The current repository now has three layers of understanding for the theme:

- public project posture: root docs such as `README.md`, `CONTRIBUTING.md`, `SECURITY.md`, and `CODE_OF_CONDUCT.md`,
- implementation-state analysis: `beamer-up/ai-dlc-docs/design-artifacts/U-B/*`,
- migration-governance contract: `beamer-up/docs/identity-governance.md` plus the `U-A` design and traceability artifacts.

Think of it as:

```text
current code and assets
  -> brownfield models explain what exists
  -> governance baseline defines what the project should say about itself
  -> later build tasks use both to migrate safely from UU to UP
```

## Artifact Map

### Brownfield artifacts

- `beamer-up/ai-dlc-docs/design-artifacts/U-B/static-model.md`
- `beamer-up/ai-dlc-docs/design-artifacts/U-B/dynamic-model.md`

### Governance artifacts

- `beamer-up/ai-dlc-docs/design-artifacts/U-A/domain-design.md`
- `beamer-up/ai-dlc-docs/design-artifacts/U-A/logical-design.md`
- `beamer-up/ai-dlc-docs/design-artifacts/U-A/adr/b-ua-01-adr.md`
- `beamer-up/docs/identity-governance.md`
- `beamer-up/docs/traceability/U-A/b-ua-01-traceability.md`

### Updated public/root docs

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`

### Updated implementation metadata surfaces

- `beamer-up/beamerthemeUU.sty`
- `beamer-up/beamercolorthemeUU.sty`
- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerouterthemeUU.sty`
- `beamer-up/main.tex`

## Detailed Walkthrough

## 1) Brownfield modeling was completed first

The inherited theme surface was reverse engineered before more build work continued.
That work captured:

- the current module boundaries,
- the public and private contracts around `UU`,
- how logos, bibliography, fonts, and Beamer subthemes are wired,
- which behaviors are observed versus still inferred.

The important result is not just “we wrote docs.”
The important result is that `U-C` now has a dependency map for the real migration work.

## 2) Naming and disclaimer policy was locked before interface renaming

`beamer-up/docs/identity-governance.md` now states:

- `beamer-up` is the canonical project identity,
- `UP` is the approved first-release public theme identifier,
- `UU` is transitional brownfield state only,
- derivative attribution must name both Zildjian E. California and A.J.H. (Jos) Zuijderwijk,
- UP-branded assets should follow the UP branding guidelines and are intended for UP constituents/internal use unless a broader permission basis is documented.

This is the core contract that later interface, packaging, and distribution work must satisfy.

## 3) Root docs were aligned to that policy

The root `README.md` now:

- moves the version marker to `v0.0.2`,
- describes the current project status more accurately,
- records the approved `UP` public contract without pretending the code migration is already complete,
- expands the repository layout to include the new brownfield/governance artifacts,
- updates the roadmap to reflect what is done and what still follows.

`CHANGELOG.md` now has a concrete `v0.0.2` entry instead of leaving this work only under `Unreleased`.

## 4) Contributor and source metadata were aligned

`CONTRIBUTING.md` now explicitly prevents contributors from reintroducing `UU` as a supported public-facing identity.
The scoped `.sty` files and `main.tex` now carry header text that labels them as legacy-named derivative implementation surfaces rather than as the permanent project identity.
The `\ProvidesPackage` descriptions were also normalized so compile metadata is less misleading.

## 5) Traceability and task state were updated

`beamer-up/REQUIREMENTS.md` marks `B-UA-01` design, implementation, testing, and documentation as done.
The review gate remains open on purpose.
That is correct for the workflow: wording approval is a real validation boundary and should not be silently collapsed into implementation work.

## Validation and Evidence

Evidence collected in this version includes:

- brownfield artifact contents for `U-B`,
- `U-A` design artifacts and ADR,
- traceability for `B-UA-01`,
- repository text searches verifying the presence of maintainer attribution, upstream attribution, `UP` contract wording, transitional `UU` wording, and branding-use disclaimer text.

This version did not require a new LaTeX compile because the runtime behavior was not changed.
The work was governance, traceability, and metadata alignment.

## Deletion Candidates

The following existing files are currently treated as build artifacts or generated observation outputs and were recorded in `CHANGELOG.md` under `For Deletion` rather than deleted:

- `beamer-up/main.bcf`
- `beamer-up/main.fls`
- `beamer-up/main.log`
- `beamer-up/main.pdf`
- `beamer-up/main.run.xml`
- `beamer-up/main.synctex.gz`
- `beamer-up/main.toc`
- `beamer-up/main.vrb`
- `beamer-up/logos/UU_logo_EN_BLACK-eps-converted-to.pdf`
- `beamer-up/logos/UU_logo_EN_RGB-eps-converted-to.pdf`

## Risks and Open Questions

- `B-UA-01` is not fully closed yet because the wording-review gate remains open.
- The actual `UU` to `UP` interface migration still belongs to `U-C`; this version only prepared the ground for it.
- `.gitignore` currently ignores `beamer-up/ai-dlc-docs/`, `beamer-up/docs/`, and `beamer-up/REQUIREMENTS.md`. If those artifacts are intended to ship in version control, the ignore rules will need review or the files will need to be force-added when committing.

## Practice Task / Self-Check

Ask yourself these three questions:

1. Can you explain the difference between the current brownfield state (`UU`) and the approved public contract (`UP`)?
2. Can you point to one source-of-truth file for naming and disclaimer wording?
3. Can you identify which artifacts here are analysis/governance artifacts versus runtime implementation files?

If the answer is yes to all three, this version did its job.

## Next 24-72 Hours

1. Review and approve the `B-UA-01` wording baseline.
2. Execute `build.task beamer-up/ unit u-a bolt b-ua-02` if asset-governance wording is the next priority.
3. Move into `U-C` once the `U-A` governance baseline is accepted, using the `U-B` models as the migration dependency map.
