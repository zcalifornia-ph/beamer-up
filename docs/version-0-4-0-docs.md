# Version v0.4.0 Documentation

## Title
Reconciled the Public Docs to the Approved Requirements Baseline

## Quick Diagnostic Read

This release does not introduce a new theme loader, a new visual system, or a new compile workflow.
It does five concrete things:

- publishes `v0.4.0` as the new public documentation baseline,
- aligns the root public status narrative with the approved requirements baseline,
- makes the README roadmap and next-step language reflect the one remaining open approval gate,
- updates the supported-version policy in `SECURITY.md`,
- normalizes changelog cleanup notes so ignored local build artifacts are described generically.

## One-Sentence Objective

Bring the public repository docs into clean agreement with the approved requirements baseline without overstating release closure that still depends on human approval.

## Why This Version Matters

By the current approved requirements baseline, the repository has already completed the major construction work:

- identity and governance baseline,
- brownfield understanding,
- public `UP` interface migration,
- UP-directed visual adaptation,
- showcase and documentation integration,
- validation-evidence packaging.

What remains open is narrower:

- the human approval gate for `B-UE-02` before deploy or ops follow-up proceeds.

That means the public docs should no longer speak as if the project is still mid-migration across the earlier Units, but they also must not claim that all release-readiness review gates are fully closed.

`v0.4.0` is the reconciliation point for that state.

## Plan A / Plan B

### Plan A (Recommended)

1. Bump the public baseline to `v0.4.0`.
2. Align README status, roadmap, and immediate-next-action text with the approved requirements state.
3. Keep `docs/release-readiness.md` as the human-review evidence handoff for the remaining `B-UE-02` gate.
4. Update the security supported-version matrix to match the new public baseline.
5. Keep ignored local build artifacts out of explicit public cleanup listings.

### Plan B

1. Keep the public docs on the prior `v0.3.5` baseline.
2. Leave roadmap and status wording partially out of sync with the approved requirements state.

Plan B keeps the repository readable, but it weakens traceability between the approved requirements baseline and the public docs that now describe the project.

## System View

```text
approved requirements baseline
  -> Units U-A through U-E implemented
  -> B-UE-01 approved and closed
  -> B-UE-02 implementation complete
  -> B-UE-02 human approval still pending

public docs baseline
  -> README.md
  -> CHANGELOG.md
  -> SECURITY.md
  -> docs/version-0-4-0-docs.md
```

Think of this release as documentation-state reconciliation.
The implementation baseline did not jump forward here; the public explanation of that baseline did.

## Artifact Map

### Public docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `SECURITY.md`

### New public version-note file added in this version

- `docs/version-0-4-0-docs.md`

### Public docs intentionally left unchanged

- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`
- `docs/usage-guide.md`
- `docs/release-readiness.md`

Those files already matched the current public contract closely enough for this reconciliation pass.

## Detailed Walkthrough

## 1) The public baseline now advances from `v0.3.5` to `v0.4.0`

The version markers in the root docs now state that:

- `v0.4.0` is the current public documentation baseline,
- `0.4.0` is the supported version in `SECURITY.md`,
- `docs/version-0-4-0-docs.md` is the new current version note.

This is a docs-reconciliation release rather than a new implementation migration release.

## 2) README status wording now matches the requirements state more directly

Earlier wording correctly described the supported `UP` path and the starter-template baseline, but it summarized the project state at a higher level.

The new wording makes the remaining state more explicit:

- the approved requirements baseline already records Units `U-A` through `U-E` as implemented,
- only the human approval gate for `B-UE-02` remains open before deploy or ops handoff.

That is more precise than continuing to describe the project mainly in terms of earlier migration phases.

## 3) The roadmap now points at the real remaining gate

The root roadmap previously ended with a broader open-ended note about preserving attribution and release clarity.

That concern still matters, but the requirements baseline now identifies a more concrete remaining open item:

- obtain human approval for `B-UE-02` release-readiness evidence.

The roadmap now reflects that exact outstanding gate.

## 4) Immediate next actions now align with the same gate

The root next-step section now tells readers to review the readiness artifact specifically against the remaining `B-UE-02` approval gate.

That keeps the public task framing aligned with the approved requirements state and avoids vague “what’s left?” ambiguity.

## 5) Changelog cleanup notes now follow the docs-task sanitization rule

`docs.task` requires public markdown surfaces to avoid naming ignored local artifacts directly.

This release therefore normalizes the affected changelog cleanup entries so they describe:

- generated local LaTeX build outputs from the bundled showcase workspace

instead of listing ignored filenames or wildcard patterns.

## Validation

Validation for this version focused on documentation-state alignment.

Confirmed points:

1. The root README now uses `v0.4.0` and points the outstanding work at the remaining `B-UE-02` approval gate.
2. The changelog now records `v0.4.0` and no longer names ignored local LaTeX byproducts explicitly in the normalized cleanup entries it touches.
3. The security supported-version matrix now follows `0.4.0`.
4. The public docs do not claim that deploy or ops follow-up is already cleared; they still preserve the human-gated readiness posture.

## Pitfalls and Debugging Notes

### 1) A docs baseline bump is not the same thing as closing every review gate

`v0.4.0` is a public documentation baseline.
It does not mean the remaining human approval gate for `B-UE-02` has been auto-closed.

### 2) Requirements alignment should improve precision, not inflate claims

The correct move is to make the current state more exact:

- major Units are implemented,
- one explicit readiness approval still remains.

That is better than either understating progress or overstating release closure.

### 3) Public docs should not expose ignored local artifact paths casually

Cleanup notes can still be useful without listing ignored generated filenames one by one.

## Practice Task

Open the current public docs and answer these questions:

1. What is the current public documentation baseline version?
2. Which remaining gate is still open before deploy or ops handoff?
3. Which file now records this requirements-alignment reconciliation?
4. Why does the changelog describe local build outputs generically instead of naming ignored files directly?

If those answers are obvious from the public docs alone, this reconciliation did its job.

## Next 24-72 Hours

1. Review `docs/release-readiness.md` against the remaining `B-UE-02` approval gate.
2. Decide whether broader public packaging should stay pdfLaTeX-first only or add wider engine validation evidence.
3. Keep future public version bumps tied to concrete state changes in the approved requirements and readiness baseline rather than to vague momentum.
