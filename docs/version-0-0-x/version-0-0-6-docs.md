# Version v0.0.6 Documentation

## Title
Approved Brownfield Runtime Baseline and Drafted `UP` Entry-Point Migration Plan for `beamer-up`

## Quick Diagnostic Read

This version does not yet ship `beamerthemeUP.sty` or change the bundled demo from `UU` to `UP`.
What it does is narrow the next implementation step and make the public docs accurate again:

- the brownfield static and dynamic baselines are now approved,
- the `UP` entry-point migration policy is drafted and scoped,
- the root public docs now describe `beamer-up` instead of stale unrelated project content,
- the next concrete implementation step is clearer and smaller.

## One-Sentence Objective

Turn the approved brownfield understanding into a concrete public-interface migration plan and update the public-facing repository docs to match that state.

## Why This Version Matters

Before this version, the repo had two real documentation problems:

- the public root `README.md` did not describe `beamer-up` at all,
- the next interface milestone was implied rather than captured as a concrete migration policy.

That is a bad handoff point for contributors. They can see that `UP` is the intended identity, but they still have to guess how the migration should be executed.

This version fixes that by documenting the current truth:

- today the implementation still loads through `UU`,
- tomorrow the supported loader should be `UP`,
- the bridge between those two states has now been planned deliberately.

## Plan A / Plan B

### Plan A (Recommended)

1. Read the updated root `README.md`.
2. Read `CHANGELOG.md` for the short release summary.
3. Read this version note to understand why the next step is implementation rather than more discovery.

### Plan B

1. Open `beamer-up/main.tex` and confirm the current `\usetheme{UU}` reality.
2. Read the roadmap and immediate-next-actions sections in `README.md`.
3. Move straight into the next bolt once the migration policy is approved.

## System View

The project now has a cleaner progression:

```text
approved governance baseline
  -> approved brownfield structural + runtime baseline
  -> drafted public UP entry-point migration plan
  -> next implementation bolt adds the UP loader and migration notes
  -> later visual and packaging work build on that stable contract
```

This matters because it separates three different concerns that were easy to blur together before:

- understanding the inherited implementation,
- deciding the public interface contract,
- actually changing the code.

Only the first two are complete in this version.

## Artifact Map

### Updated public docs

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-6-docs.md`

### Current public implementation surface

- `beamer-up/main.tex`
- `beamer-up/beamerthemeUU.sty`
- `beamer-up/beamercolorthemeUU.sty`
- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerouterthemeUU.sty`
- `beamer-up/logos/`

### Current milestone outcome

- brownfield baselines are approved,
- `UP` migration policy is drafted,
- `B-UC-02` is the next implementation step after policy approval.

## Detailed Walkthrough

## 1) The brownfield runtime baseline is now formally usable downstream

Earlier work already modeled the inherited theme statically and dynamically.
This version matters because that runtime model is now treated as approved downstream context rather than as an unresolved prerequisite.

In practical terms, contributors no longer need to reopen baseline discovery before starting the public loader migration.

## 2) The public interface question is now narrowed to one deliberate migration step

The drafted migration policy sets a disciplined direction:

- `UP` becomes the canonical public loader,
- existing options and helper commands stay stable,
- any surviving `UU` loader becomes deprecated compatibility rather than a coequal public contract,
- direct `UU` subtheme-loading is not the supported first-release path,
- deeper color-token and visual cleanup stay out of this bolt.

That is the right scope boundary. It keeps the public interface change small enough to implement and review cleanly.

## 3) The root public README now matches the actual repository

The old root `README.md` described a different project entirely.
That kind of drift is worse than missing documentation because it actively misleads contributors, reviewers, and future maintainers.

This version replaces that mismatch with:

- the current derivative identity,
- the approved naming contract,
- the honest present-tense `UU` runtime state,
- the planned `UP` target,
- the next implementation actions.

## 4) This version still does not claim code-level `UP` support

That limit is intentional.
The docs now say exactly what the repo can and cannot do today:

- yes, `UP` is the approved public target,
- no, the checked-in theme does not yet compile through `\usetheme{UP}`,
- yes, the next bolt is now well-defined enough to implement that change.

This avoids the common failure mode where documentation promises a migration that the code has not yet delivered.

## 5) One deletion candidate was recorded instead of being silently removed

`test.tmp` was left in place to respect the repo rule against deleting files during task execution.
This version records it in `CHANGELOG.md` under `For Deletion` so the user can remove it manually later.

## Validation and Evidence

Evidence used for this version includes:

- the approved brownfield static and dynamic baseline state,
- the current checked-in `UU` usage surface in `beamer-up/main.tex`,
- the absence of a shipped `beamerthemeUP.sty` file in the current tree,
- the newly drafted migration policy that narrows the next implementation bolt,
- the public-doc consistency review across `README.md`, `CHANGELOG.md`, and the version notes.

This version is a planning-and-docs milestone, not a code-interface milestone.

## Practice Task

Open the updated `README.md` and answer these three questions without checking internal maintainer records:

1. What loader works today in the checked-in demo?
2. What loader is intended to become the supported public contract?
3. What is the next implementation step after review?

If you can answer all three quickly, the public docs are doing their job.

## Self-Check

You understood this version if you can explain:

- why approving the runtime baseline matters before interface migration,
- why `UP` implementation is not yet done,
- why keeping helper and option semantics stable makes the next bolt safer.

## Next 24-72 Hours

1. Review and approve the drafted `UP` migration policy.
2. Implement the canonical `UP` loader and any explicit `UU` deprecation behavior.
3. Update the showcase deck and public snippets to use `UP`.
4. Compile the supported `UP` path and record migration evidence.
