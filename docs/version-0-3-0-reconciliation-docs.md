# Version v0.3.0 Reconciliation Documentation

## Title
Reconciled the Root Public Docs Back to the Approved `v0.3.0` Baseline

## Quick Diagnostic Read

This follow-up does not publish a new public release.
It does four concrete things:

- keeps `v0.3.0` as the current approved public documentation baseline,
- reclassifies `docs/release-readiness.md` as a human-gated follow-up evidence artifact rather than a published baseline,
- corrects the root docs so they no longer overstate `v0.3.1` as already published,
- preserves the existing readiness materials and screenshot evidence as pending review context.

## One-Sentence Objective

Make the root documentation match the approved requirements state by restoring `v0.3.0` as the current public baseline while leaving the `B-UE-02` readiness evidence visible but explicitly unapproved.

## Why This Follow-Up Matters

The repo already contained useful readiness materials:

- `docs/release-readiness.md`,
- `repo/images/project_screen.png`,
- the detailed `docs/version-0-3-1-docs.md` narrative.

But the approved requirements state still says `B-UE-02` is waiting on human approval before closure and before deploy or ops work proceeds.

That means treating `v0.3.1` as a published public baseline would overstate the repository's current approved status.

This follow-up fixes that mismatch.

## Plan A / Plan B

### Plan A (Recommended)

1. Keep the approved public baseline at `v0.3.0`.
2. Treat readiness evidence as a pending follow-up artifact until human approval is granted.
3. Update the root docs and version trail so they describe that boundary honestly.

### Plan B

1. Leave the root docs at `v0.3.1`.
2. Assume readiness evidence equals publication.
3. Let the public docs outrun the approved requirements state.

Plan B is simpler in the moment, but it weakens traceability and approval discipline.

## System View

```text
approved public baseline: v0.3.0
  -> README.md
  -> CHANGELOG.md
  -> SECURITY.md
pending readiness follow-up:
  -> docs/release-readiness.md
  -> docs/version-0-3-1-docs.md
  -> repo/images/project_screen.png
approval gate still open:
  -> REQUIREMENTS.md B-UE-02 review checkbox remains unchecked
```

## Artifact Map

### Root docs updated in this follow-up

- `README.md`
- `CHANGELOG.md`
- `SECURITY.md`

### Related version-trail docs updated in this follow-up

- `docs/version-0-3-1-docs.md`
- `docs/version-0-3-0-reconciliation-docs.md`

### Evidence surfaces preserved but not promoted to baseline

- `docs/release-readiness.md`
- `repo/images/project_screen.png`

## Detailed Walkthrough

## 1) The root docs now match the approval state again

The biggest correction is simple:

- `README.md` now says the current approved public baseline is `v0.3.0`,
- `CHANGELOG.md` now says the same thing,
- `SECURITY.md` now supports `0.3.0` explicitly instead of a broader `0.3.x` claim.

That change lines the public docs back up with the approval gate recorded in `REQUIREMENTS.md`.

## 2) Readiness evidence is preserved without being overstated

This follow-up does not remove or hide the readiness materials.

Instead, it keeps them visible as pending context:

- compile evidence remains in `docs/release-readiness.md`,
- the refreshed screenshot remains at `repo/images/project_screen.png`,
- the longer readiness narrative remains under `docs/version-0-3-1-docs.md`.

The change is in classification, not deletion.
Those materials are now treated as follow-up evidence awaiting approval rather than as proof that a new public baseline is already published.

## 3) The `v0.3.1` narrative is now framed honestly

Before this reconciliation, `docs/version-0-3-1-docs.md` still read like a completed release note.

That created a documentation mismatch:

- root docs said one thing after the normalization,
- the detailed version note said something stronger.

This follow-up keeps the file in the public version trail, but reframes it as a pending readiness narrative tied to the still-open human review gate.

## 4) Cleanup candidates are now recorded because they actually exist

`commit.task` requires build-artifact cleanup notes when those files exist.

They do exist in the bundled showcase workspace right now, including generated local LaTeX outputs such as:

- `main.pdf`,
- `main.log`,
- `cover-check.pdf`,
- related compile byproducts.

Per repo rules, this follow-up does not delete them.
It only records them as cleanup candidates in `CHANGELOG.md`.

## Validation

Validation for this follow-up was documentation consistency review rather than a new compile run.

Confirmed points:

1. `README.md`, `CHANGELOG.md`, and `SECURITY.md` now point to `v0.3.0` as the approved baseline.
2. `REQUIREMENTS.md` still records `B-UE-02` as awaiting human approval.
3. `docs/release-readiness.md` remains available as evidence without being promoted to the approved baseline.
4. Local LaTeX build artifacts are present and therefore belong in the changelog cleanup notes.

## Pitfalls and Debugging Notes

### 1) Evidence is not the same as approval

A repo can have compile proof, screenshots, and packaging notes without those materials automatically becoming the approved public release state.

### 2) Version-trail docs must agree with root docs

If a detailed version note says a release is published while the root docs say the approval gate is still open, users get two incompatible stories.

### 3) Cleanup notes should follow actual file presence

If local LaTeX build outputs exist, the changelog should record them as cleanup candidates.
The repo rule is to report them, not delete them.

## Practice Task

Open these four files and answer one question from each:

1. `README.md`: what is the current approved public baseline?
2. `CHANGELOG.md`: what is still pending in Unreleased?
3. `SECURITY.md`: which version is explicitly supported?
4. `REQUIREMENTS.md`: what approval gate is still open for `B-UE-02`?

If the answers line up cleanly, the reconciliation worked.

## Next 24-72 Hours

1. Decide whether the recorded readiness evidence is sufficient to close `B-UE-02`.
2. If approval is granted later, promote the readiness materials consistently in both the root docs and the version trail.
3. Clean local LaTeX build artifacts when release packaging or workspace cleanup is appropriate.
