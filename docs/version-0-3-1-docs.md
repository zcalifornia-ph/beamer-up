# Version v0.3.1 Follow-Up Documentation

## Title
Captured the Pending `v0.3.1` Release-Readiness Follow-Up Narrative

## Quick Diagnostic Read

This follow-up captures the current readiness package without treating it as an approved published baseline.
It does six concrete things:

- records the previously drafted `v0.3.1` readiness pass as pending rather than approved,
- adds `docs/release-readiness.md` as the tracked evidence surface for compile, screenshot, asset-governance, and packaging notes,
- refreshes `repo/images/project_screen.png` from the accepted final PDF,
- aligns `README.md`, `docs/usage-guide.md`, and `CONTRIBUTING.md` around that new public evidence surface,
- removes the last Utrecht-named presentation phrase from the checked-in deck copy,
- keeps final bolt closure and any deploy or ops follow-on explicitly human-gated.

## One-Sentence Objective

Make the repository's public starter-template baseline defensible for broader distribution review by packaging compile proof, screenshot proof, and wording alignment into one tracked release-readiness pass without overstating that publication or operational handoff is already complete.

## Why This Version Matters

`v0.3.0` made the checked-in deck usable as a real starter template and added a proper usage guide, but it still left one public-facing gap.
The repository had the right starter surface, yet the compile proof, refreshed screenshot evidence, and GitHub/Overleaf packaging notes were still implied rather than packaged.

The readiness pass closes that documentation gap in evidence terms, but it does not by itself close the approval gap.

The new `docs/release-readiness.md` file gives maintainers and reviewers one place to verify:

- the preferred compile path,
- the fallback compile path,
- the refreshed screenshot surface,
- the supported-path runtime assets,
- the aligned provenance and disclaimer wording,
- the remaining human approval boundary.

That matters because a starter template is easier to trust when the proof surface is explicit instead of scattered across local context or implied from prior task history.

## Plan A / Plan B

### Plan A (Recommended)

1. Publish a tracked release-readiness artifact for the current public baseline.
2. Refresh the screenshot from the accepted final PDF rather than leaving an older front-page image in place.
3. Align the root README, usage guide, and contributor guidance to the new evidence surface.
4. Record the remaining human approval gate explicitly instead of pretending the broader release process is already closed.

### Plan B

1. Keep compile proof and screenshot evidence local-only.
2. Continue relying on the starter-template and usage-guide surfaces without a dedicated readiness artifact.
3. Delay the version bump until a later deploy or ops phase.

Plan B would reduce immediate doc work, but it would keep the public repository less auditable than the actual validation work already completed for `B-UE-02`.

## System View

```text
supported public loader: UP
  -> checked-in starter template under beamer-up/main.tex
  -> public onboarding in README.md and docs/usage-guide.md
  -> public readiness proof in docs/release-readiness.md
  -> refreshed screenshot at repo/images/project_screen.png
  -> final closure still requires human approval before deploy/ops follow-on
```

## Artifact Map

### Root docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`

### New public docs added in this version

- `docs/release-readiness.md`
- `docs/version-0-3-1-docs.md`

### Existing public docs aligned in this version

- `docs/usage-guide.md`

### Checked-in showcase/template surfaces updated in this version

- `beamer-up/main.tex`
- `repo/images/project_screen.png`

## Detailed Walkthrough

## 1) The new readiness artifact makes the validation surface explicit

`docs/release-readiness.md` is the central change in this version.
It packages the evidence that was previously either local, implicit, or spread across task-specific context.

The file now records:

- the Unit and Bolt context (`U-E` / `B-UE-02`),
- the acceptance checklist mapping (`T-01`, `T-02`, `T-04` to `T-10`),
- the preferred `latexmk` compile result,
- the documented fallback `pdflatex -> biber -> pdflatex -> pdflatex` result,
- the refreshed screenshot timestamp,
- the supported English runtime asset evidence,
- the remaining non-blocking warnings,
- the deployment-check handoff status pending human review.

That turns release-readiness from an assumption into a tracked repository artifact.

## 2) The screenshot now matches the real checked-in title slide

The older front-page screenshot no longer matched the current starter-template deck.
This version regenerates `repo/images/project_screen.png` from the final accepted `main.pdf`, so the repository front page now reflects the actual checked-in title slide users compile today.

This matters because screenshot drift quietly weakens trust.
If the screenshot is stale, users cannot tell whether the public docs match the real output.

## 3) Public wording is now aligned around one evidence surface

`README.md` and `docs/usage-guide.md` already described the supported `UP` loader, compile flow, and provenance posture.
The drafted `v0.3.1` follow-up updates both files so they also point directly to `docs/release-readiness.md` for:

- compile proof,
- screenshot proof,
- packaging notes,
- GitHub and Overleaf wording alignment.

`CONTRIBUTING.md` is updated for the same reason.
Contributors are now told to keep `docs/release-readiness.md` aligned whenever public compile-validation or distribution wording changes, so the repo has a clearer anti-drift rule for future changes.

## 4) The last Utrecht-named presentation phrase is removed from deck copy

The checked-in theme still contains inherited `UU`-named implementation files for brownfield continuity, but the public presentation copy should not keep using Utrecht-facing language.

This version removes the remaining presentation phrase that said "Utrecht palette" and replaces it with source-neutral wording.
That keeps the public deck copy aligned with the repository's own derivative-project contract:

- `UP` is the supported public loader,
- inherited `UU` names are implementation or migration detail only,
- public-facing presentation text should not drift back toward Utrecht-branded framing.

## 5) This release still does not claim final public release or deploy closure

This follow-up improves the public audit trail significantly, but it does not silently collapse the human validation boundary.

What remains explicitly human-gated:

- final bolt closure for `B-UE-02`,
- any `deploy.task` follow-on,
- any `ops.task` follow-on,
- broader publishing decisions such as GitHub release packaging or Overleaf release posture.

That boundary is important.
The repository now contains the evidence package, but a human still decides whether that package is sufficient for the next operational step.

## Validation

Validation for this version used the final checked-in deck after the wording cleanup in `beamer-up/main.tex`.

Observed compile paths:

1. Preferred path from `beamer-up/`:
   - `latexmk -pdf main.tex`
2. Documented fallback path from `beamer-up/`:
   - `pdflatex -interaction=nonstopmode main.tex`
   - `biber main`
   - `pdflatex -interaction=nonstopmode main.tex`
   - `pdflatex -interaction=nonstopmode main.tex`

Observed result:

- both paths completed successfully with exit code `0`,
- the final `main.pdf` is 28 pages and 1,157,911 bytes,
- `main.log` records `Output written on main.pdf (28 pages, 1157911 bytes).`,
- `repo/images/project_screen.png` was regenerated from that final PDF on `2026-04-03 16:08:39`.

Non-blocking warnings remained:

- `hyperref` PDF-string metadata warnings,
- repeated `pdfauthor` warnings from intentional title-page mode switches,
- `Underfull \hbox` warnings on content-dense slides,
- MiKTeX local `log4cxx` logging-path warnings.

## Pitfalls and Debugging Notes

### 1) A readiness artifact should not pretend to be a release itself

The new document packages evidence.
It does not mean a GitHub release, Overleaf package, or deploy/ops handoff has already happened.

### 2) Screenshot refresh must follow the accepted final PDF

If the screenshot is regenerated before the final deck wording is settled, the repository front page drifts out of sync again.
This version avoids that by regenerating the PNG after the final accepted compile run.

### 3) Public wording and contributor wording should move together

Once a new public evidence surface exists, contributor guidance should mention it too.
Otherwise, future doc changes tend to update user-facing pages but forget the maintenance rule that keeps them aligned.

## Practice Task

Open `README.md`, `docs/usage-guide.md`, and `docs/release-readiness.md`, then answer these four questions without using internal planning files:

1. What is the supported public loader?
2. What is the recommended compile command?
3. Where is the screenshot/readiness proof recorded?
4. What still requires human approval before deploy or ops follow-on?

If those answers are obvious from the tracked public docs alone, the repository's readiness story is coherent.

## Next 24-72 Hours

1. Decide whether the current evidence package is sufficient to close `B-UE-02`.
2. Decide whether wider XeLaTeX or LuaLaTeX validation belongs in the public release baseline or stays optional.
3. If a GitHub release or Overleaf package is prepared, carry the same provenance, disclaimer, and asset-governance wording forward unchanged unless a human explicitly approves a new posture.
