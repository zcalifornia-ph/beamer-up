# Version v0.3.4 Documentation

## Title
Aligned the Active Subtheme Filenames with the Supported `UP` Namespace

## Quick Diagnostic Read

This release does not change the supported public loader, the public options, or the starter-template workflow.
It does five concrete things:

- publishes `v0.3.4` as a patch-level filename-migration release,
- switches the active color, inner, and outer subtheme filenames from inherited `UU` names to `UP` names,
- updates the canonical loader and the renamed package declarations so the implementation matches the on-disk filenames,
- updates the current public docs and starter-template file tables so they no longer point at deleted subtheme filenames,
- revalidates the checked-in deck through the documented `latexmk` path after the filename migration.

## One-Sentence Objective

Make the active implementation filenames match the supported `UP` public namespace so the codebase, file tree, and live docs all describe the same theme surface.

## Why This Version Matters

`v0.3.3` made `beamerthemeUP.sty` the true canonical implementation entry, but the active color, inner, and outer subtheme files were still named with inherited `UU` identifiers.

Once those files were renamed on disk, the repository needed a full follow-through:

- the canonical loader still had to be updated to request the new `UP` subthemes,
- the renamed files still had to advertise the correct `UP` package identities,
- the README, usage guide, readiness notes, and starter-template file table still had to stop pointing at filenames that no longer existed.

`v0.3.4` closes that remaining mismatch.

The public contract stays intentionally simple:

- users still load the theme with `\usetheme{UP}`,
- `beamerthemeUP.sty` remains the canonical public entry,
- `beamercolorthemeUP.sty`, `beamerinnerthemeUP.sty`, and `beamerouterthemeUP.sty` are now the active implementation files,
- `beamerthemeUU.sty` remains only as legacy compatibility for older `\usetheme{UU}` material.

## Plan A / Plan B

### Plan A (Recommended)

1. Keep the renamed `UP` subtheme filenames.
2. Update `beamerthemeUP.sty` to load them directly.
3. Update the renamed files so their package identities match their filenames.
4. Update the current docs and starter-template references.
5. Recompile the checked-in deck to confirm the supported path still works.

### Plan B

1. Keep the filesystem rename only.
2. Leave `beamerthemeUP.sty` loading the deleted `UU` subtheme names.
3. Leave package declarations and docs pointing at the old filenames.

Plan B preserves none of the practical benefits of the rename and risks breaking normal theme loading immediately.

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

legacy compatibility path
  -> \usetheme{UU}
  -> beamerthemeUU.sty
      -> deprecation warning
      -> option forwarding
      -> RequirePackage{beamerthemeUP}
```

Think of this release as namespace alignment for the live implementation surface.
The public entry point was already `UP`; now the active subtheme filenames match that same namespace too.

## Artifact Map

### Theme files updated in this version

- `beamer-up/beamerthemeUP.sty`
- `beamer-up/beamercolorthemeUP.sty`
- `beamer-up/beamerinnerthemeUP.sty`
- `beamer-up/beamerouterthemeUP.sty`

### Root and public docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `SECURITY.md`
- `docs/usage-guide.md`
- `docs/release-readiness.md`
- `beamer-up/main.tex`

### New public version-note file added in this version

- `docs/version-0-3-4-docs.md`

## Detailed Walkthrough

## 1) `beamerthemeUP.sty` now loads the renamed `UP` subthemes directly

The canonical public loader now requests:

- `\usecolortheme{UP}`
- `\useinnertheme{UP}`
- `\useoutertheme{UP}`

That means normal `\usetheme{UP}` loading now resolves through the renamed files instead of still expecting the deleted `UU` subtheme basenames.

## 2) The renamed subtheme files now advertise matching `UP` package identities

The renamed files were not only moved at the filesystem level.
Their own source headers and `\ProvidesPackage{...}` declarations now identify:

- `beamercolorthemeUP`
- `beamerinnerthemeUP`
- `beamerouterthemeUP`

That matters because the package identity should match the file that Beamer is actually loading.

## 3) The current docs and starter template now stop pointing at deleted filenames

The rename affected multiple live documentation surfaces:

- the repository layout in `README.md`,
- the migration note in `docs/usage-guide.md`,
- the compile-evidence/runtime-reference table in `docs/release-readiness.md`,
- the file-overview table inside `beamer-up/main.tex`.

All of those now point to the `UP`-named subtheme files and current runtime references rather than the removed `UU` filenames.

## 4) The release trail now distinguishes `v0.3.3` from `v0.3.4`

`v0.3.3` remains the implementation-surface consolidation release where `beamerthemeUP.sty` became the real canonical entry.

`v0.3.4` is the next patch-level step:

- the active subtheme filenames now align with that canonical `UP` namespace,
- the release trail no longer folds the filename migration into the earlier ownership-consolidation release,
- the supported-version matrix in `SECURITY.md` now follows the new root baseline.

## 5) The supported compile path was revalidated after the rename

The checked-in starter deck was rebuilt from `beamer-up/` using:

```powershell
latexmk -pdf main.tex
```

Observed result:

- compile completed successfully with exit code `0`,
- final output: `main.pdf`,
- reported output size: `1,157,907` bytes,
- reported page count: `28`.

The log shows the normal supported path loading:

- `beamerthemeUP.sty`
- `beamercolorthemeUP.sty`
- `beamerinnerthemeUP.sty`
- `beamerouterthemeUP.sty`

That is the key validation point for this release.

## Validation

Validation for this version focused on filename alignment and behavioral continuity.

Confirmed points:

1. `beamerthemeUP.sty` now requests the `UP`-named subthemes directly.
2. The renamed subtheme files now provide `UP` package identities.
3. The current README, usage guide, readiness note, and starter-template file table no longer point at deleted `UU` subtheme filenames.
4. The documented `latexmk` compile path still succeeds for the checked-in starter deck through the supported `UP` path.

Observed non-blocking warnings remained:

- `hyperref` PDF-string warnings,
- repeated `pdfauthor` warnings from title-page metadata changes,
- `Underfull \hbox` warnings on documentation-heavy slides,
- MiKTeX `log4cxx` access warnings for local user-profile logging paths.

These warnings did not block the compile result for this release.

## Pitfalls and Debugging Notes

### 1) This is not a change to the public loader name

Users should still load the theme with `\usetheme{UP}`.
This release aligns internal filenames and package identities with the existing public namespace.

### 2) Renaming files is not enough by itself

If the filesystem rename happens without updating `beamerthemeUP.sty` and the `\ProvidesPackage{...}` declarations, the active theme path becomes inconsistent or broken.

### 3) Current docs must move with the code

Once live files are renamed, the README layout, usage guidance, readiness evidence, and starter-template file table all need to stop naming the deleted files.
Otherwise the repository starts teaching an implementation shape that no longer exists.

## Practice Task

Open these four files and answer the questions without using internal planning notes:

1. Which file should a normal user load to use the theme?
2. Which three files now implement the active color, inner, and outer subthemes?
3. Which file still exists only for legacy `\usetheme{UU}` compatibility?
4. Which compile command confirms the renamed files still work together?

If those answers are obvious from the tracked repository surfaces, the filename migration is documented well enough.

## Next 24-72 Hours

1. Review whether any external packaging notes, release text, or Overleaf instructions outside the repository still mention the deleted `UU` subtheme filenames.
2. Keep historical version notes intact unless there is a deliberate reason to revise archived references.
3. If broader packaging proceeds, keep the public contract centered on `UP` and keep `beamerthemeUU.sty` framed only as legacy compatibility.
