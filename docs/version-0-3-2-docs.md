# Version v0.3.2 Documentation

## Title
Archived the Historical Public Version Docs into Series-Based Folders

## Quick Diagnostic Read

This release does not change the supported `UP` loader, the starter-template baseline, or the compile workflow.
It does four concrete things:

- publishes `v0.3.2` as a docs-only archive-reorganization baseline,
- moves the older `v0.0.x`, `v0.1.x`, and `v0.2.x` version narratives into grouped archive folders under `docs/`,
- keeps the active `v0.3.x` narratives and public quick-start surfaces at the root of `docs/`,
- updates the root docs so users can understand the new version-trail layout without opening internal workflow files.

## One-Sentence Objective

Keep the public documentation trail easier to navigate by grouping older version narratives into series-based archive folders while preserving the current `v0.3.x` baseline and follow-up materials in the most visible location.

## Why This Version Matters

The root `docs/` directory had become harder to scan because every historical version note from the early migration and visual-adaptation work still lived beside the active public surfaces.
That made it more difficult to distinguish:

- current public onboarding docs,
- active `v0.3.x` baseline and follow-up narratives,
- older historical notes that still matter for traceability but are no longer the first things a reader should see.

`v0.3.2` fixes that navigation problem without pretending there is a new theme release or a new readiness decision.

The public contract is still the same:

- supported loader: `UP`,
- current starter-template baseline: the checked-in `beamer-up/main.tex` plus `docs/usage-guide.md`,
- pending readiness evidence: `docs/release-readiness.md` and `docs/version-0-3-1-docs.md`,
- human approval gate for broader release-readiness follow-on: still intact.

## Plan A / Plan B

### Plan A (Recommended)

1. Group older version narratives by release series.
2. Leave the active `v0.3.x` materials at the root of `docs/`.
3. Update root docs so the archive structure is visible and understandable.
4. Preserve the readiness follow-up narrative as pending context rather than burying it inside the historical archive.

### Plan B

1. Keep every historical version note flattened at the root of `docs/`.
2. Force readers to scan older migration-era notes before finding the active public surfaces.
3. Delay documentation cleanup until a later release.

Plan B is lower effort, but it makes the public docs noisier and weakens the version-trail signal.

## System View

```text
public docs root
  -> README.md
  -> docs/usage-guide.md
  -> docs/release-readiness.md
  -> docs/version-0-3-0-docs.md
  -> docs/version-0-3-0-reconciliation-docs.md
  -> docs/version-0-3-1-docs.md
  -> docs/version-0-3-2-docs.md

historical archive bands
  -> docs/version-0-0-x/
  -> docs/version-0-1-x/
  -> docs/version-0-2-x/
```

Think of this as a two-tier doc layout:

- root `docs/` for the active public story,
- grouped archive folders for older but still useful history.

## Artifact Map

### Root docs updated in this version

- `README.md`
- `CHANGELOG.md`
- `SECURITY.md`

### New public docs added in this version

- `docs/version-0-3-2-docs.md`

### Historical docs reorganized in this version

- `docs/version-0-0-x/*`
- `docs/version-0-1-x/*`
- `docs/version-0-2-x/*`

### Active public docs intentionally kept at `docs/` root

- `docs/usage-guide.md`
- `docs/release-readiness.md`
- `docs/version-0-3-0-docs.md`
- `docs/version-0-3-0-reconciliation-docs.md`
- `docs/version-0-3-1-docs.md`

## Detailed Walkthrough

## 1) The docs root now emphasizes the current public story

The most important repository docs for a new reader are still easy to locate:

- the quick-start and migration guide,
- the release-readiness evidence surface,
- the current `v0.3.x` version trail.

That means `docs/` now reads more like the active public front desk and less like a flat dump of every version note ever written.

## 2) Older version narratives are preserved, not discarded

The early `v0.0.x`, `v0.1.x`, and `v0.2.x` narratives still matter because they explain:

- the brownfield migration path,
- the early UP visual adaptation work,
- the earlier documentation and title-page follow-ups,
- the steps that led to the current starter-template baseline.

This version keeps that history intact, but re-homes it into grouped archive folders so the history remains available without overpowering the current docs root.

## 3) The pending `v0.3.1` readiness narrative stays visible on purpose

`docs/version-0-3-1-docs.md` is not treated as the approved public baseline, but it is still active context for the current readiness story.

That is why this release does not archive it with the older series.
The active `v0.3.x` materials remain at the root of `docs/` until maintainers intentionally decide the series is historical enough to archive as a group.

## 4) The root docs now explain the archive shape directly

`README.md` now shows the grouped archive folders in the repository layout and explicitly tells readers where the older version notes live.

`SECURITY.md` was updated as well so the supported-version matrix follows the new public documentation baseline instead of lagging behind on `0.3.0`.

`CHANGELOG.md` now records this release as a docs-only archive-reorganization pass and preserves the earlier `v0.3.0` reconciliation note as separate history.

## Validation

Validation for this release was documentation-structure review rather than a new compile run.

Confirmed points:

1. The historical version notes for `v0.0.x`, `v0.1.x`, and `v0.2.x` now exist in grouped folders under `docs/`.
2. The active `v0.3.x` materials remain at the root of `docs/`.
3. `README.md`, `CHANGELOG.md`, and `SECURITY.md` now describe the same baseline and archive shape.
4. The bundled LaTeX workspace still contains generated local build outputs, so changelog cleanup notes remain warranted.

## Pitfalls and Debugging Notes

### 1) Archive reorganization is not the same as a new theme feature release

This version improves documentation navigation.
It does not change the supported loader, macros, palette, compile path, or starter-template content.

### 2) Older version notes should stay accessible

Do not solve docs clutter by deleting the historical version trail.
This repository values traceability, and the archive folders preserve that history while reducing noise.

### 3) Active and archival docs should not be mixed casually

Once grouped archives exist, future version-trail changes should keep the active series easy to find and move older series deliberately rather than flattening everything back into one directory again.

## Practice Task

Open `README.md` and the `docs/` directory, then answer these four questions:

1. Which version is the current approved public documentation baseline?
2. Where would you look for a `v0.1.3` narrative now?
3. Which `v0.3.x` files still remain at the root of `docs/`?
4. Which file still records the pending release-readiness follow-up?

If those answers are obvious, the archive reorganization worked.

## Next 24-72 Hours

1. Add the new grouped archive folders and their moved version notes to the next manual commit.
2. Decide whether a future `v0.3.x` or `v0.4.x` milestone should eventually get its own archive band once the active series grows.
3. Keep future root-doc updates aligned so the README layout, changelog, and supported-version matrix continue to tell the same story.
