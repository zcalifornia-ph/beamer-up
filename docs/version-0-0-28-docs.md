# Version v0.0.28 Documentation

## Title
Normalized the Public Root Cleanup Notes Without Changing the Theme Implementation

## Quick Diagnostic Read

This version is a docs-only reconciliation release.
It does four concrete things:

- bumps the public root docs from `v0.0.27` to `v0.0.28`,
- keeps the current checked-in title-page implementation baseline unchanged,
- rewrites the root changelog cleanup notes so they no longer name ignored local build-output paths directly,
- records that public-docs cleanup in the versioned release-note set.

## One-Sentence Objective

Make the root public docs comply with the repository's docs-task rule that ignored local build outputs should not be named directly in the public markdown files.

## Why This Version Matters

`v0.0.27` already documented the current title-page implementation correctly.
The remaining inconsistency was narrower and purely documentary:

- the root `CHANGELOG.md` still listed exact ignored build-output file paths under multiple `For Deletion` sections.

That matters because the repo task rules explicitly say the public root docs should not expose ignored-path details.
This version fixes that without pretending a new theme implementation milestone happened.

## Plan A / Plan B

### Plan A (Recommended)

1. Read `CHANGELOG.md`.
2. Find the historical `For Deletion` sections that named exact ignored local build outputs.
3. Replace those with generic cleanup language that still preserves the release-history meaning.
4. Bump the root version markers and add this version note.

### Plan B

1. Compare `v0.0.27` and `v0.0.28` in the root docs.
2. Confirm that the theme behavior summary stays the same.
3. Confirm that the cleanup notes are still present, but no longer expose ignored local build-output paths directly.

## System View

```text
checked-in theme baseline stays the same
  -> public root docs are reconciled to docs-task policy
  -> ignored build-output cleanup notes become generic
  -> version marker advances for the docs-only release
```

The important point is that the implementation surface did not change here.
Only the public documentation behavior changed.

## Artifact Map

### Public docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-28-docs.md`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

### Theme implementation intentionally unchanged in this version

- `beamer-up/beamerthemeUP.sty`
- `beamer-up/beamerthemeUU.sty`
- `beamer-up/beamercolorthemeUU.sty`
- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerouterthemeUU.sty`
- `beamer-up/main.tex`

## Detailed Walkthrough

## 1) This is a docs-only release, not a new theme pass

The checked-in theme implementation remains the same as the already documented `v0.0.27` baseline.
That includes:

- the light-surface title-page treatment,
- the bold subtitle,
- the maroon divider and venue/date separator accents,
- the forest-green conference affiliation markers,
- the refreshed showcase metadata.

This version does not claim new `.sty` behavior.
It only reconciles the root public docs around the repository's documentation constraints.

## 2) The root changelog now avoids naming ignored local build outputs directly

The actual inconsistency was in the root `CHANGELOG.md`.
Multiple historical `For Deletion` sections still named exact ignored local build-output paths directly.

This version normalizes those entries so they still communicate the cleanup state, but do so generically:

- generated local showcase build outputs remain cleanup candidates,
- extra local verification outputs remain cleanup candidates when relevant,
- temporary preview or scratch artifacts already tracked in public docs remain described only where they are not part of the ignored local build-output set.

That keeps the public release notes useful without exposing ignored-path detail that the repo workflow explicitly asks us to avoid.

## 3) The README now publishes this as a documentation reconciliation milestone

The root `README.md` now advances to `v0.0.28` and explicitly notes that:

- the theme implementation baseline is still the current `v0.0.27` title-page polish state,
- the root public docs now keep cleanup notes generic rather than naming ignored local build-output paths directly.

That is the honest scope boundary for this release.

## 4) Governance docs were reviewed and left unchanged on purpose

`SECURITY.md`, `CONTRIBUTING.md`, and `CODE_OF_CONDUCT.md` already matched repo reality.

Changing them here would have added noise without improving accuracy.
Leaving them untouched is the correct move for a narrow public-docs cleanup release.

## Validation Notes

This version is documentation-only.
No new theme compilation was required for the release itself.

The latest implementation verification already reflected in the root docs remains:

- the April 3, 2026 `pdflatex main.tex` validation pass from `beamer-up/`,
- with `latexmk -pdf main.tex` still documented as the recommended full build path.

## Pitfalls and Debugging Notes

### 1) A docs-only version should say clearly that the code did not change

If the implementation surface is unchanged, the release note set should not imply a new styling milestone.

### 2) Cleanup notes are still valid even when made generic

The repo rules do not say to hide cleanup state.
They say not to expose ignored-path detail in the public root docs.
The right fix is generic cleanup wording, not deleting the cleanup notes entirely.

### 3) Historical release notes can drift into policy violations

Even if older release entries were accurate at the time, a later docs-policy pass may still need to normalize their wording.

## Practice Task

Read the root `CHANGELOG.md` and verify:

1. the release history still tells you what kind of cleanup existed,
2. the ignored local build-output paths are no longer named directly in the public root changelog,
3. the current implementation milestone remains clearly attributable to `v0.0.27`.

Self-check:

- you should be able to explain why `v0.0.28` is docs-only,
- you should be able to point to the exact policy issue it fixes,
- you should be able to say clearly that the theme `.sty` files and showcase deck did not change in this release.

## Next 24-72 Hours

1. Remove or archive the current local generated outputs after review if they are no longer needed.
2. Continue release-packaging and broader validation work for the first public release.
3. Keep future public root cleanup notes generic whenever they refer to ignored local build outputs.
