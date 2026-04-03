# Version v0.2.0 Documentation

## Title
Published the `v0.2.0` Public Baseline and Reconciled the Root Docs to the Current Planning State

## Quick Diagnostic Read

This release is a documentation-baseline bump tied to the current checked-in theme state.
It does four concrete things:

- publishes `v0.2.0` as the root public documentation baseline,
- aligns the README wording to the current planning reality,
- keeps the current title-page fixes visible in the documented public baseline,
- updates the supported-version statement in `SECURITY.md`.

## One-Sentence Objective

Make the public root docs describe the current `beamer-up` reality accurately without overstating release readiness or reopening already completed migration work.

## Why This Version Matters

The repository no longer sits at the same maturity level as the earlier `0.1.x` docs trail.

The checked-in project already has:

- the public `UP` loader,
- the derivative/governance baseline,
- the brownfield understanding needed for safe changes,
- the current UP-directed visual system,
- the repaired multiline title-page behavior, including explicit conference-affiliation line breaks.

But the remaining work is still real:

- broader showcase coverage,
- validation evidence,
- distribution-ready packaging guidance.

That means the docs should not behave as if the project is still in the earlier patch-baseline stage, and they also should not pretend first broader release readiness is done.

`v0.2.0` marks that middle state clearly.

## Plan A / Plan B

### Plan A (Recommended)

1. Bump the public root-doc version marker to `v0.2.0`.
2. Reconcile README status language to the current planning baseline.
3. Keep the open release-readiness work explicit in roadmap and next-action sections.
4. Update the security support matrix to match the new baseline.
5. Record the reconciliation in a new versioned docs note.

### Plan B

1. Leave the docs on `v0.1.4`.
2. Continue stacking narrow patch notes without acknowledging the broader milestone shift.

Plan B is simpler, but it makes the public release trail harder to read and less truthful about the current state.

## System View

```text
current checked-in theme baseline
  -> public UP interface already active
  -> visual adaptation already active
  -> title-page multiline fixes already active
  -> release-readiness work still open
  -> root docs should describe exactly that state
```

## Artifact Map

### Root docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `SECURITY.md`

### Versioned public docs added in this version

- `docs/version-0-2-0-docs.md`

### Governance docs reviewed but not changed

- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) Why `v0.2.0` is the right public-doc baseline

The current checked-in repository is beyond the earlier "narrow patch fix" posture.

The public docs now need to describe a project that already has:

- a stable supported loader,
- a coherent derivative identity,
- a functioning UP-directed theme surface,
- a more mature title-page system than the earlier `0.1.x` notes implied.

At the same time, the repository still has an obvious unfinished area:

- showcase and distribution readiness.

So this update treats `v0.2.0` as the clearer public milestone:
not "finished release packaging," but also not merely "another small patch note."

## 2) The README now separates completed work from remaining work more clearly

The previous README already contained much of the right information, but the version marker lagged the current maturity level.

This version keeps the important project facts and makes the status line more legible:

- completed enough for a `0.2.0` public baseline,
- still actively moving toward showcase expansion and distribution readiness,
- not reopening the naming or visual-system migration as if those were still the main blockers.

That distinction matters because contributors and users need to know whether the next work is:

- another branding rewrite,
- or validation/packaging/release-polish work.

Right now it is the latter.

## 3) The current title-page behavior remains part of the documented public baseline

The root docs still need to reflect the real checked-in title-page behavior.

That includes:

- multiline-safe single-author metadata,
- multiline-safe multi-author metadata,
- explicit-linebreak-safe conference affiliations.

This version keeps that state visible in the README instead of letting the version bump flatten it away into vague wording.

## 4) The supported-version statement now matches the new baseline

`SECURITY.md` previously marked `0.1.x` as the supported public range.

That was now stale relative to the requested version bump.

This version updates the table so:

- `0.2.x` is the supported public line,
- `0.1.x` and older or unpublished snapshots are not.

That keeps the security and maintenance posture consistent with the public docs baseline.

## Validation

Validation for this release was a documentation reconciliation pass against the current checked-in repository state.

Checked:

- the root README version marker and status summary,
- the changelog baseline and top release entry,
- the security support matrix,
- the roadmap and immediate-next-actions wording,
- the current checked-in title-page behavior and theme-state claims against the live working tree.

## Pitfalls and Debugging Notes

### 1) A version bump should not exaggerate readiness

Moving from `0.1.4` to `0.2.0` does not mean the project is "finished."
It means the public baseline has moved forward enough that a broader milestone marker is clearer.

### 2) Public docs should distinguish completed migration work from remaining release work

If those get mixed together, contributors can waste time reopening already settled migration surfaces instead of finishing validation and packaging.

### 3) Internal planning artifacts can inform public docs without being exposed

The public wording should reflect the planning truth, but it should not leak hidden or gitignored planning paths into the root documentation.

## Practice Task

Open `README.md` and answer these three questions without checking any internal planning files:

1. What is the supported public loader?
2. What title-page multiline behavior is currently supported?
3. What work still remains before the broader public release cycle?

If the README answers all three cleanly, the docs are doing their job.

## Next 24-72 Hours

1. Expand the showcase deck with more real academic use cases.
2. Capture broader compile-validation evidence across common TeX environments.
3. Finalize the GitHub and Overleaf distribution-ready packaging notes for the current public baseline.
