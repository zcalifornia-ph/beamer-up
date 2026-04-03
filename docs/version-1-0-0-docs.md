# Version v1.0.0 Documentation

## Title
Published the First Supported Public Release and Removed Legacy UU Surfaces

## Quick Diagnostic Read

This release turns the checked-in repository into the first supported public release.
It does seven concrete things:

- publishes `v1.0.0` as the first supported public release baseline,
- adds full LPPL 1.3c license headers to all distributed theme source files,
- removes the legacy `beamerthemeUU.sty` compatibility wrapper from the maintained surface,
- removes the inherited `UU_logo_*.eps` asset files from the repository,
- removes the `nl` Dutch-logo compatibility option from the supported public contract,
- refreshes the showcase deck with UP-themed sample metadata and a v1.0.0 title marker,
- restores the original Tai 1994 bibliography entry behind the `tai1994mathematical` cite key.

## One-Sentence Objective

Ship the first public release of `beamer-up` as a clean, attribution-complete, legacy-free derivative that presents only the maintained `UP` surface to users and contributors.

## Why This Version Matters

The earlier `v0.4.0` baseline accurately described the repository's implementation state and the closed readiness gate, but the repository still carried several legacy surfaces that belonged to the migration era rather than the release era:

- the deprecated `UU` wrapper file still existed in the tree,
- the inherited Utrecht EPS logo files still occupied the asset directory,
- the `nl` option still appeared in public docs and theme code even though it was no longer part of the first-release scope,
- the source files carried short-form attribution comments instead of full LPPL 1.3c license headers,
- the showcase deck still used placeholder metadata and an older version marker,
- the bibliography entry behind `tai1994mathematical` had been temporarily swapped to a different source during an earlier docs pass.

`v1.0.0` closes all of those gaps at once.

The public contract is now cleaner:

- supported loader: `UP` only,
- active implementation: `beamerthemeUP.sty` plus the `UP`-named subtheme files,
- legacy wrapper: removed,
- legacy assets: removed,
- legacy option: removed,
- license headers: full LPPL 1.3c text in every distributed source file,
- showcase: UP-themed sample metadata with a v1.0.0 title marker,
- bibliography: restored to the original Tai 1994 paper.

## Plan A / Plan B

### Plan A (Recommended)

1. Add full LPPL 1.3c license headers to all `.sty` files, `main.tex`, and `references.bib`.
2. Delete the legacy `beamerthemeUU.sty` wrapper file.
3. Delete the inherited `UU_logo_*.eps` asset files.
4. Remove the `nl` option declaration and all `nl` branching logic from the theme code.
5. Update the showcase deck title, metadata, and sample authors to UP-themed values.
6. Restore the original Tai 1994 bibliography entry.
7. Update the public docs to reflect the v1.0.0 baseline and the removed legacy surfaces.
8. Refresh the repository screenshot from the updated deck.

### Plan B

1. Keep the legacy wrapper and assets in place for historical traceability.
2. Keep the `nl` option documented for users who might still need it.
3. Delay the full license headers until a later cleanup pass.

Plan B preserves more history, but it makes the first public release carry migration residue that the approved requirements baseline no longer requires.

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
      -> english / filipino logo paths
      -> no nl option

removed legacy surfaces
  -> beamerthemeUU.sty (deleted)
  -> UU_logo_EN_BLACK.eps (deleted)
  -> UU_logo_EN_RGB.eps (deleted)
  -> UU_logo_NL_RGB.eps (deleted)
  -> UU_logo_NL_ZWART.eps (deleted)
  -> nl option (removed from code and docs)
```

## Artifact Map

### Theme files updated in this version

- `beamer-up/beamerthemeUP.sty`
- `beamer-up/beamercolorthemeUP.sty`
- `beamer-up/beamerinnerthemeUP.sty`
- `beamer-up/beamerouterthemeUP.sty`
- `beamer-up/main.tex`
- `beamer-up/references.bib`

### Theme files deleted in this version

- `beamer-up/beamerthemeUU.sty`
- `beamer-up/logos/UU_logo_EN_BLACK.eps`
- `beamer-up/logos/UU_logo_EN_RGB.eps`
- `beamer-up/logos/UU_logo_NL_RGB.eps`
- `beamer-up/logos/UU_logo_NL_ZWART.eps`

### Root docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `SECURITY.md`
- `CONTRIBUTING.md`

### Public asset updated in this version

- `repo/images/project_screen.png`

### New public version-note file added in this version

- `docs/version-1-0-0-docs.md`

## Detailed Walkthrough

## 1) Full LPPL 1.3c license headers now appear in every distributed source file

The earlier source files carried short-form attribution comments that identified the derivative project, the upstream author, and the branding disclaimer.

This version replaces those short headers with full LPPL 1.3c license text in:

- `beamerthemeUP.sty`
- `beamercolorthemeUP.sty`
- `beamerinnerthemeUP.sty`
- `beamerouterthemeUP.sty`
- `main.tex`
- `references.bib`

Each header now includes:

- copyright notice for Zildjian E. California,
- derivative provenance from the original `beamer-uu` work by A.J.H. (Jos) Zuijderwijk,
- the full LPPL 1.3c license reference and URL,
- the maintained status and current maintainer contact path,
- the list of files that make up the work,
- the branding-use disclaimer for UP assets.

That matters because the first public release should carry complete license context rather than abbreviated attribution notes.

## 2) The legacy UU wrapper file is removed

`beamerthemeUU.sty` existed as a deprecated compatibility bridge that forwarded options to `beamerthemeUP.sty` and emitted a deprecation warning.

This version deletes that file entirely.

The removal is safe because:

- the public docs already directed users to `UP` only,
- the showcase deck no longer referenced `UU`,
- the approved first-release scope no longer included a legacy compatibility surface.

Users with older decks that still load `\usetheme{UU}` will now get a clear compile error instead of a deprecation warning, which is the correct behavior for a first release that has moved past the migration bridge.

## 3) The inherited UU logo EPS files are removed

The repository still carried the original Utrecht EPS logo files:

- `UU_logo_EN_BLACK.eps`
- `UU_logo_EN_RGB.eps`
- `UU_logo_NL_RGB.eps`
- `UU_logo_NL_ZWART.eps`

These files were inherited from the `beamer-uu` baseline and were no longer referenced by any active theme code path after the `nl` option was removed.

This version deletes them entirely.

That cleans the asset directory of legacy institutional marks that the first release no longer needs, ships, or documents.

## 4) The nl option is removed from the supported public contract

The `nl` Dutch-logo compatibility option previously appeared in:

- `beamerthemeUP.sty` option declarations,
- logo-path selection logic,
- header and closing-slide branching code,
- public docs and option lists.

This version removes `nl` from all of those surfaces:

- the `\DeclareOption{nl}` line is removed,
- the `\if@UUnl` boolean and its branches are removed,
- the header logo code no longer has an `nl` branch,
- the closing slide no longer has an `nl` branch,
- the README, usage docs, and showcase option lists no longer mention `nl`.

The theme now has only two language variants:

- `english` (default),
- `filipino`.

That simplifies the public contract and removes a code path that the first release no longer supports.

## 5) The showcase deck now uses UP-themed sample metadata

The earlier showcase deck still carried placeholder author names and an older version marker.

This version updates `beamer-up/main.tex` so:

- the title now reads "Beamer Theme for UP" with a `v1.0.0` marker,
- the subtitle now describes the template as "A LaTeX slide template for the University of the Philippines System",
- the single-author example now uses a UP-themed author name and institute,
- the multi-author example now uses Gomburza (Gómez, Burgos, Zamora) as the sample authors with UP Diliman and UP Mindanao affiliations,
- the venue line now reads "UP System Research Colloquium 2026",
- the `nl` option is removed from the theme-options slide,
- the GitHub/Overleaf distribution bullet is removed from the compile-and-distribution slide since that guidance now lives in the root docs.

That makes the checked-in deck read as a first-release showcase rather than a migration-era demo.

## 6) The bibliography entry behind tai1994mathematical is restored

An earlier docs pass had temporarily swapped the `tai1994mathematical` cite key to a different source for a bibliography demonstration.

This version restores the original Tai 1994 paper entry:

- author: Tai, Mary M,
- title: "A mathematical model for the determination of total area under glucose tolerance and other metabolic curves",
- journal: Diabetes care,
- volume, number, pages, year, and publisher restored.

That keeps the bibliography example aligned with the actual cite key name and the original showcase intent.

## 7) The single-author date/venue line now renders in maroon bold

The inner theme template now renders the single-author date and venue metadata line in `UPMaroon` with bold weight instead of `UPBlack` regular weight.

That gives the cover-page metadata stronger visual emphasis on the light-surface title page.

## 8) The public docs now describe the v1.0.0 baseline

The root README, CHANGELOG, SECURITY, and CONTRIBUTING files now all reflect:

- `v1.0.0` as the current supported public release,
- the removed legacy surfaces (UU wrapper, UU logos, nl option),
- the full LPPL license headers in source files,
- the refreshed showcase metadata,
- the closed first-release readiness and approval gate.

The repository screenshot at `repo/images/project_screen.png` was also refreshed from the updated deck.

## Validation

Validation for this version focused on release-surface completeness and behavioral continuity.

Confirmed points:

1. All distributed `.sty` files, `main.tex`, and `references.bib` now carry full LPPL 1.3c license headers.
2. The legacy `beamerthemeUU.sty` wrapper file is deleted.
3. The inherited `UU_logo_*.eps` files are deleted.
4. The `nl` option is removed from theme code, docs, and showcase option lists.
5. The showcase deck compiles through the supported `UP` path with the updated metadata.
6. The bibliography entry behind `tai1994mathematical` is restored to the original Tai 1994 paper.
7. The public docs describe `v1.0.0` as the first supported public release.

## Pitfalls and Debugging Notes

### 1) Older decks that still load \usetheme{UU} will now fail to compile

The legacy wrapper is deleted. Users must update older material to `\usetheme{UP}`.

### 2) The nl option no longer exists

Any deck that previously passed `nl` as a theme option will now receive an "unused global option" warning from Beamer instead of activating a Dutch logo path.

### 3) Full license headers are larger than short attribution comments

The LPPL 1.3c text adds roughly 25-30 lines to each source file. That is intentional for a first public release.

## Practice Task

Open the updated showcase deck and the root README, then answer these four questions:

1. What is the supported public loader?
2. Which legacy files were removed in this release?
3. What happens if an older deck still tries to load `\usetheme{UU}`?
4. Which license governs the distributed theme files?

If those answers are obvious from the public docs and source headers, the first-release surface is documented well enough.

## Next 24-72 Hours

1. Decide whether any external packaging notes, release text, or Overleaf instructions outside the repository still mention the deleted `UU` files or the `nl` option.
2. Continue removing inherited internal `UU` identifiers from macro names and asset basenames where that cleanup is safe and does not change the public `UP` contract.
3. Broaden multi-engine validation beyond the current pdfLaTeX baseline if XeLaTeX and LuaLaTeX evidence should become part of the public release record.
