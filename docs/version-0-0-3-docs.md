# Version v0.0.3 Documentation

## Title
Asset Governance and Review-State Closure for `beamer-up`

## Quick Diagnostic Read

This version still does not change the public runtime interface from `UU` to `UP`.
What it adds is the release-control layer that the previous baseline still lacked:

- an asset inventory that classifies every current file under `beamer-up/logos/`,
- a package-surface baseline for GitHub and Overleaf distributions,
- closure of the previously approved `B-UA-01` review state,
- a clearer separation between brownfield runtime assets, generated outputs, and candidate future UP assets.

## One-Sentence Objective

Make the repository able to describe its current and future logo assets truthfully before later tasks package or replace them.

## Why This Version Matters

Without this version, later packaging or migration work would still be guessing about:

- which logo files are current runtime dependencies,
- which files are only compile-generated outputs,
- which `up-*` assets are merely candidates and not yet release-ready,
- what GitHub and Overleaf package surfaces must say about those assets.

This version removes that ambiguity and closes the earlier naming-review gate at the same time.

## Plan A / Plan B

### Plan A (Recommended)

1. Read `beamer-up/docs/asset-governance.md`.
2. Read `beamer-up/docs/traceability/U-A/b-ua-02-traceability.md`.
3. Read `beamer-up/ai-dlc-docs/design-artifacts/U-A/adr/b-ua-02-adr.md`.
4. Read `beamer-up/REQUIREMENTS.md` around `B-UA-01` and `B-UA-02`.

### Plan B

1. Read the updated root `README.md` for the public-facing posture.
2. Read `CHANGELOG.md` for the version summary.
3. Use this document as the bridge between the summary and the deeper governance artifacts.

## System View

The repository now has four layers of understanding for the theme:

- public project posture: root docs such as `README.md`, `CONTRIBUTING.md`, `SECURITY.md`, and `CODE_OF_CONDUCT.md`,
- implementation-state analysis: `beamer-up/ai-dlc-docs/design-artifacts/U-B/*`,
- identity and migration-governance contract: `beamer-up/docs/identity-governance.md`,
- asset-governance and package-surface contract: `beamer-up/docs/asset-governance.md`.

Think of it as:

```text
current code and assets
  -> brownfield models explain what exists
  -> identity governance defines what the project should say about itself
  -> asset governance defines what can be shipped and how it must be described
  -> later build and packaging tasks use all three to migrate safely from UU to UP
```

## Artifact Map

### New or materially updated governance artifacts

- `beamer-up/docs/asset-governance.md`
- `beamer-up/docs/traceability/U-A/b-ua-02-traceability.md`
- `beamer-up/ai-dlc-docs/design-artifacts/U-A/adr/b-ua-02-adr.md`
- `beamer-up/ai-dlc-docs/design-artifacts/U-A/domain-design.md`
- `beamer-up/ai-dlc-docs/design-artifacts/U-A/logical-design.md`

### Review-state closure artifacts

- `beamer-up/REQUIREMENTS.md`
- `beamer-up/docs/traceability/U-A/b-ua-01-traceability.md`
- `beamer-up/ai-dlc-docs/design-artifacts/U-A/adr/b-ua-01-adr.md`

### Updated public/root docs

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `docs/version-0-0-3-docs.md`

## Detailed Walkthrough

## 1) Asset inventory is now explicit

`beamer-up/docs/asset-governance.md` defines the fields every institutional or branded asset must carry:

- path,
- format,
- current role,
- observed usage,
- provenance-note status,
- release eligibility,
- required disclaimer surfaces,
- release-note expectation.

That means later package decisions no longer have to guess from filenames alone.

## 2) Current `logos/` files are now classified by real behavior

The inventory distinguishes four states:

- `brownfield-runtime-source`,
- `brownfield-runtime-path-unvalidated`,
- `generated-output`,
- `candidate-up-asset`.

In practice, this means:

- English `UU` EPS files are recorded as currently observed runtime inputs,
- Dutch `nl` EPS files are recorded as code-reachable but not yet observed in compile evidence,
- `*-eps-converted-to.pdf` files are recorded as generated outputs,
- `up-*` PNG files are recorded as candidate future UP assets rather than approved release contents.

## 3) GitHub and Overleaf packaging rules are now coupled to the inventory

The new surface matrix defines what public/package surfaces must preserve:

- derivative provenance,
- non-endorsement posture,
- UP branding-guidelines/internal-use wording,
- truthful description of which assets are actually bundled.

This makes later deployment and packaging review measurable instead of purely editorial.

## 4) `B-UA-01` is now formally closed

You had already approved the naming/disclaimer baseline.
This version writes that approval back into the durable artifacts:

- `beamer-up/REQUIREMENTS.md` now closes `B-UA-01`,
- `b-ua-01-traceability.md` now records the approval date,
- `b-ua-01-adr.md` now marks the decision as approved.

That removes the mismatch where the repo state lagged behind the actual approval state.

## 5) `B-UA-02` is implemented but intentionally still open at review

`beamer-up/REQUIREMENTS.md` now shows `B-UA-02` with:

- design complete,
- implementation complete,
- test/documentation complete,
- review still open.

That is the correct workflow boundary for this version: the baseline exists, but downstream packaging should still wait for explicit maintainer approval.

## Validation and Evidence

Evidence collected in this version includes:

- source inspection of `beamerthemeUU.sty`, `beamerinnerthemeUU.sty`, `beamerouterthemeUU.sty`, and `main.tex`,
- existing `main.log` and `main.fls` evidence showing the observed EPS runtime path and generated PDF outputs,
- repository consistency searches for GitHub/Overleaf wording, asset-state vocabulary, provenance, and disclaimer text,
- inventory coverage checks confirming every current file under `beamer-up/logos/` appears in `beamer-up/docs/asset-governance.md`.

This version did not require a new LaTeX compile because it changed governance and release-state documentation, not runtime behavior.

## Open Gate

- `B-UA-02` still requires maintainer approval of the asset-governance baseline before downstream packaging or migration work should treat it as closed.

## Next 24-72 Hours

1. Review and approve the `B-UA-02` asset-governance baseline.
2. Use the new inventory as the release gate for any GitHub or Overleaf packaging work.
3. Keep the inventory current if any logo is added, replaced, removed, or promoted toward release packaging.