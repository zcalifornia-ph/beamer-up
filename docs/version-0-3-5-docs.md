# Version v0.3.5 Documentation

## Title
Retired the Legacy `UU` Wrapper from the Current Public Contract

## Quick Diagnostic Read

This patch-level update does not change the supported public loader, the theme options, or the active `UP`-named subtheme files.
It does five concrete things:

- publishes `v0.3.5` as the current public documentation baseline,
- removes current-surface wording that still advertised `beamerthemeUU.sty` as part of the maintained public contract,
- keeps `\usetheme{UP}` through `beamerthemeUP.sty` as the only supported public loader surface,
- updates the README, usage guide, readiness note, starter-template file table, and source header to match that contract,
- preserves older version notes as historical state instead of rewriting them as if the legacy wrapper never existed.

## One-Sentence Objective

Align the current public docs and starter-template surfaces with the maintained `UP`-only contract after retiring the legacy `UU` wrapper from current-facing guidance.

## Why This Version Matters

Earlier `v0.3.x` notes correctly recorded the migration from inherited `UU` naming toward the supported `UP` path, but some current public-facing surfaces still described `beamerthemeUU.sty` as if it were part of the maintained contract.

That wording became the wrong teaching surface once the supported path had already settled on:

- `\usetheme{UP}`,
- `beamerthemeUP.sty`,
- `beamercolorthemeUP.sty`,
- `beamerinnerthemeUP.sty`,
- `beamerouterthemeUP.sty`.

`v0.3.5` closes that current-surface mismatch without erasing the repository's historical version trail.
It does not claim that every remaining `UU`-named artifact has been physically removed from the checkout.

## Plan A / Plan B

### Plan A (Recommended)

1. Keep the supported public contract centered on `UP`.
2. Update current public docs and starter-template references so they stop advertising the legacy wrapper as an active maintained surface.
3. Preserve older version notes as historical evidence rather than rewriting them.
4. Revalidate the checked-in deck through the documented `latexmk` path.

### Plan B

1. Keep the implementation on `UP`.
2. Continue describing a legacy `UU` wrapper as if it were part of the maintained public contract.

Plan B keeps current docs out of sync with the actual supported path and makes migration guidance harder to read.

## System View

```text
supported public path
  -> \usetheme{UP}
  -> beamerthemeUP.sty
      -> \usecolortheme{UP}
      -> \useinnertheme{UP}
      -> \useoutertheme{UP}
      -> beamercolorthemeUP.sty
      -> beamerinnerthemeUP.sty
      -> beamerouterthemeUP.sty

older deck update path
  -> replace \usetheme{UU}
  -> with \usetheme{UP}
```

Think of this release as public-contract cleanup rather than a new theme-loader migration.
The supported path was already `UP`; the current docs now describe only that maintained surface.

## Artifact Map

### Current-surface files updated in this version

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `SECURITY.md`
- `docs/usage-guide.md`
- `docs/release-readiness.md`
- `beamer-up/beamerthemeUP.sty`
- `beamer-up/main.tex`

### New public version-note file added in this version

- `docs/version-0-3-5-docs.md`

### Historical version notes intentionally left intact

- `docs/version-0-3-3-docs.md`
- `docs/version-0-3-4-docs.md`

Those files record earlier repository states and should stay readable as history instead of being retroactively flattened into the new baseline.

## Detailed Walkthrough

## 1) The current public contract now points only at the maintained `UP` surface

The root README, usage guide, and readiness note now all describe the same current public contract:

- load the theme with `\usetheme{UP}`,
- treat `beamerthemeUP.sty` as the public theme entry file,
- treat the `UP`-named color, inner, and outer subthemes as the active implementation surface,
- update older `UU` decks instead of relying on a legacy wrapper path in current docs.

## 2) The checked-in starter template no longer lists the legacy wrapper as a current theme file

The file-overview table in `beamer-up/main.tex` now lists only the active maintained theme surface:

- `beamerthemeUP.sty`
- `beamercolorthemeUP.sty`
- `beamerinnerthemeUP.sty`
- `beamerouterthemeUP.sty`

That keeps the starter template aligned with what new users should actually reuse.

## 3) Source comments now teach migration instead of compatibility

The source header in `beamer-up/beamerthemeUP.sty` and the top comment in `beamer-up/main.tex` now tell readers to update older `\usetheme{UU}` material to `UP`.

That is a better current teaching surface than presenting a legacy wrapper as if it were still part of the maintained public contract.

## 4) Historical release notes remain historical

This version deliberately does not rewrite older `v0.3.3` and `v0.3.4` notes as if those states never happened.

Those notes still explain:

- when `beamerthemeUP.sty` became the canonical implementation entry,
- when the active subtheme filenames moved into the `UP` namespace.

`v0.3.5` adds the next step: current docs and starter-template surfaces now stop surfacing the legacy wrapper as part of the maintained public contract.

## 5) This is current-surface cleanup, not a claim that every legacy artifact is gone

Some inherited `UU` residue can still exist in the tree as implementation carry-over or historical material.

What changed here is narrower and more precise:

- current public docs no longer teach a legacy wrapper as part of the maintained contract,
- the starter template no longer lists it as part of the reuse surface,
- migration guidance now tells users to move older decks to `UP`.

## 6) The supported compile path remains the same

The supported compile command remains:

```powershell
latexmk -pdf main.tex
```

This version does not alter option parsing, active subtheme loading, or the validated `UP`-directed visual system.

## Validation

Validation for this version focused on current-surface contract alignment.

Confirmed points:

1. Current README, usage, readiness, and starter-template surfaces no longer advertise `beamerthemeUU.sty` as part of the maintained public contract.
2. The repository layout and starter-template file table now point at the active `UP`-named implementation surface only.
3. Historical version notes remain intact so the release trail still explains how the migration happened.

## Pitfalls and Debugging Notes

### 1) Do not rewrite history just because the current contract changed

Older version notes should keep describing the state that existed when those versions were published.

### 2) Do not confuse remaining `UU` residue with a supported loader contract

Some inherited `UU` names still exist in internal macros, asset basenames, or historical notes.
That is not the same thing as an active public theme-loader surface.

### 3) The public loader name did not change in this version

Users should still load the theme with `\usetheme{UP}`.
This release removes stale current-surface wording; it does not introduce a new public entry point.

## Practice Task

Open the current public docs and answer these questions:

1. Which file should a normal user load to use the theme?
2. Which three files now implement the active color, inner, and outer subthemes?
3. What should a user do with an older deck that still says `\usetheme{UU}`?
4. Which file records this current public-contract cleanup in the version trail?

If those answers are obvious from the public repository surfaces, the cleanup is documented well enough.

## Next 24-72 Hours

1. Review whether any external GitHub release text, Overleaf description, or packaging note still advertises the legacy wrapper as current.
2. Decide separately whether the legacy file should remain in the tree as internal residue or be removed in a later explicit cleanup step.
3. Keep README, usage, readiness, and starter-template wording aligned whenever the public contract changes again.
