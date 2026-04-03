# Version v0.1.0 Documentation

## Title
Promoted the Public Docs Baseline to v0.1.0 and Reconciled the Root Governance Docs to the Approved Requirements

## Quick Diagnostic Read

This version is a docs-reconciliation release.
It does five concrete things:

- bumps the public root docs from `v0.0.31` to `v0.1.0`,
- realigns `README.md`, `CHANGELOG.md`, `CONTRIBUTING.md`, and `SECURITY.md` with `beamer-up/REQUIREMENTS.md`,
- removes stale cross-project changelog history that no longer belongs to this repository,
- tightens the public naming contract so `UP` is the only supported loader described in public docs,
- keeps the versioned docs trail continuous by adding this note.

## One-Sentence Objective

Make the root documentation truthful, coherent, and releasable as the first `v0.1.0` public docs baseline for `beamer-up`.

## Why This Version Matters

Before this update, the public docs had two structural problems:

- the root version markers still stopped at `v0.0.31`,
- the root changelog still contained stale `VERZOLA` history from a different repository context.

That made the public documentation baseline harder to trust, even though the checked-in `beamer-up` theme sources, requirements, and versioned docs already pointed to a coherent UP-themed derivative project.

This version matters because it turns the public root docs back into a reliable front door:

- the version baseline is now `v0.1.0`,
- the public loader contract is explicitly `UP`,
- the changelog is back to being a `beamer-up` changelog,
- the security and contribution guidance now match the same project contract.

## Plan A / Plan B

### Plan A (Recommended)

1. Read `beamer-up/REQUIREMENTS.md`.
2. Read the public root docs and the latest versioned docs under `docs/`.
3. Compare them against the checked-in theme files under `beamer-up/`.
4. Rewrite the root docs where versioning, project identity, or public contract drifted.
5. Publish a new versioned docs note for the `v0.1.0` docs baseline.

### Plan B

1. Patch only the visible version strings.
2. Leave the mixed-project changelog and softer `UU` wording in place.

Plan B is faster, but it leaves the public docs internally inconsistent.
This release takes Plan A instead.

## System View

```text
beamer-up/REQUIREMENTS.md
  -> approved public contract and current Unit status
  -> root docs must describe that state truthfully
  -> README / CHANGELOG / CONTRIBUTING / SECURITY updated together
  -> docs/version-0-1-0-docs.md records the rationale
```

## Artifact Map

### Public root docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `SECURITY.md`

### Versioned public docs added in this version

- `docs/version-0-1-0-docs.md`

### Public governance docs reviewed but not changed

- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The root README now describes the actual public contract

The previous README still published `v0.0.31` and over-explained several checked-in visual details while softening the public loader boundary around `UU`.

This version keeps the useful public facts but makes the contract sharper:

- `v0.1.0` is the current public docs baseline,
- `\usetheme{UP}` is the supported public loader,
- remaining `UU` names are implementation residue, not the public interface,
- the root docs now point clearly to the checked-in compile path and the current requirements state.

## 2) The root changelog is now a beamer-up changelog again

The old root changelog still contained stale `VERZOLA` entries from a different project context.

That is not a small formatting issue.
It breaks trust in the public release trail.

This version rewrites the root changelog so it now:

- tracks `beamer-up` only,
- starts with a new `v0.1.0` entry,
- preserves the recent `beamer-up` milestones in a cleaner grouped form,
- keeps deletion notes generic rather than naming ignored local build-output paths directly.

## 3) Contribution and security guidance now match the same public interface

The contribution and security docs were already mostly aligned, but they still benefited from two targeted fixes:

- supported-version policy now starts at `0.1.x`,
- wording around `UU` now treats it as migration or implementation detail rather than as a supported public interface.

That matters because governance docs are part of the release surface, not side notes.

## Validation

Validation for this version is documentation-focused:

- `README.md` publishes `v0.1.0`,
- `CHANGELOG.md` no longer mixes in another project's release history,
- `CONTRIBUTING.md` and `SECURITY.md` use the same `UP`-first public contract,
- the new versioned note extends the existing `docs/version-*-docs.md` trail cleanly.

## Pitfalls and Debugging Notes

### 1) A version bump is not just a string replacement

If the root changelog, README, and governance docs disagree about project identity or support boundaries, changing only one visible version string is not enough.

### 2) Historical implementation residue is not the same thing as public support

A repository can still contain `UU`-named files without documenting `UU` as a supported public loader.
Public docs should describe the supported contract, not every brownfield detail as if it were part of the release promise.

### 3) Mixed-project history in a root changelog is a release-surface bug

It makes public provenance harder to trust.
The fix is to rewrite the changelog around the current repository, not to preserve irrelevant history for its own sake.

## Practice Task

Open `README.md` and `CHANGELOG.md` side by side.

Self-check:

- both now identify `v0.1.0` as the current public baseline,
- both clearly describe `UP` as the supported public loader,
- neither needs the reader to infer which project the docs actually belong to.

## Next 24-72 Hours

1. Run the next round of showcase and environment validation for Unit `U-E`.
2. Document GitHub and Overleaf distribution readiness once the evidence set is complete.
3. Keep future root-doc version bumps paired with a new `docs/version-*-docs.md` note so the public trail stays coherent.
