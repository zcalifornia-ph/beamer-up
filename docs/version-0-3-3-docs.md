# Version v0.3.3 Documentation

## Title
Consolidated the Canonical Theme Implementation into `beamerthemeUP.sty`

## Quick Diagnostic Read

This version does not change the supported public loader, the public options, or the starter-template compile workflow.
It does five concrete things:

- publishes `v0.3.3` as a patch-level implementation-surface consolidation release,
- moves the actual theme orchestration from `beamerthemeUU.sty` into `beamerthemeUP.sty`,
- keeps `beamerthemeUU.sty` only as a deprecated compatibility wrapper for older `\usetheme{UU}` material,
- updates the showcase and public docs so `beamerthemeUP.sty` is no longer described as a wrapper,
- revalidates the checked-in deck through the documented `latexmk` path after the consolidation.

## One-Sentence Objective

Make the supported public `UP` package the real canonical implementation surface instead of a delegating shim, while preserving the older `UU` path only as explicit compatibility.

## Why This Version Matters

Before this version, the public contract already said that `UP` was the supported theme identifier, but the code still delegated the actual work through `beamerthemeUU.sty`.
That left an internal mismatch:

- the public docs treated `UP` as canonical,
- the actual orchestration still lived behind the legacy `UU` file,
- the checked-in showcase and guide text still had to explain `beamerthemeUP.sty` as a wrapper.

`v0.3.3` closes that mismatch without widening the change into a broad filename migration or a namespace rewrite.

The result is simpler and easier to explain:

- `\usetheme{UP}` remains the supported loader,
- `beamerthemeUP.sty` now owns the implementation directly,
- `beamerthemeUU.sty` remains only as deprecated compatibility for older material.

## Plan A / Plan B

### Plan A (Recommended)

1. Move the existing orchestration logic into `beamerthemeUP.sty`.
2. Keep the `UU` entry point only as a compatibility wrapper that forwards options and warns on direct legacy use.
3. Update the public wording so the docs and showcase match the new file responsibilities.
4. Recompile the checked-in deck to confirm that the supported `UP` path still works.

### Plan B

1. Keep `beamerthemeUP.sty` as a wrapper.
2. Keep the implementation concentrated in `beamerthemeUU.sty`.
3. Continue documenting a public/internal mismatch for readers and contributors.

Plan B preserves behavior, but it leaves the codebase harder to reason about because the supported public package is not the file that actually owns the theme behavior.

## System View

```text
supported public path
  -> \usetheme{UP}
  -> beamerthemeUP.sty
      -> option parsing
      -> subtheme loading
      -> listings / bibliography / font setup
      -> logo-path selection
      -> hyperref styling

legacy compatibility path
  -> \usetheme{UU}
  -> beamerthemeUU.sty
      -> deprecation warning
      -> option forwarding
      -> RequirePackage{beamerthemeUP}
```

Think of this release as an ownership correction rather than a feature expansion.
The visible public contract stays the same, but the canonical file now truly owns the behavior it represents.

## Artifact Map

### Theme files updated in this version

- `beamer-up/beamerthemeUP.sty`
- `beamer-up/beamerthemeUU.sty`

### Public-facing files aligned in this version

- `README.md`
- `CHANGELOG.md`
- `SECURITY.md`
- `docs/usage-guide.md`
- `beamer-up/main.tex`

### New public version-note file added in this version

- `docs/version-0-3-3-docs.md`

## Detailed Walkthrough

## 1) `beamerthemeUP.sty` now owns the actual theme behavior

The option parsing, subtheme loading, listings setup, bibliography setup, font-selection logic, logo-path selection, caption settings, navigation-symbol suppression, and `hyperref` color setup now live in `beamer-up/beamerthemeUP.sty`.

That means the supported public package now directly matches what users are told to load.
The canonical loader is no longer just a facade over a legacy-named file.

## 2) `beamerthemeUU.sty` is now an explicit compatibility bridge

The legacy file is still present because the repository rules for this workspace do not allow deleting whole files in this task flow, and older user material may still load `\usetheme{UU}`.

Its responsibility is now intentionally narrow:

- accept legacy options,
- forward them to `beamerthemeUP.sty`,
- emit a deprecation warning for direct `UU` usage,
- stop pretending to be a coequal implementation surface.

This is a cleaner separation than the previous wrapper model.

## 3) The docs and showcase now describe the file split accurately

The public usage guide and the checked-in showcase previously described `beamerthemeUP.sty` as a wrapper and `beamerthemeUU.sty` as the implementation entry.

After the consolidation:

- `docs/usage-guide.md` now describes `beamerthemeUP.sty` as the public theme entry file,
- the file-overview table in `beamer-up/main.tex` now describes `beamerthemeUP.sty` as the canonical public theme entry,
- the root README and version trail now document the new ownership model as part of the approved public baseline.

That removes avoidable explanatory friction for users and contributors.

## 4) The supported compile path was revalidated after the consolidation

The checked-in starter deck was rebuilt from `beamer-up/` using:

```powershell
latexmk -pdf -interaction=nonstopmode main.tex
```

Observed result:

- compile completed successfully with exit code `0`,
- final output: `main.pdf`,
- reported output size: `1,157,907` bytes,
- reported page count: `28`.

The compile still exercised the supported public `UP` path rather than a direct `UU` load, which is the important validation point for this release.

## Validation

Validation for this version focused on ownership and behavioral continuity.

Confirmed points:

1. `beamerthemeUP.sty` now contains the previously delegated orchestration logic.
2. `beamerthemeUU.sty` now acts only as a compatibility wrapper with a deprecation warning.
3. `docs/usage-guide.md` and `beamer-up/main.tex` no longer describe `beamerthemeUP.sty` as a wrapper.
4. The documented `latexmk` compile path still succeeds for the checked-in starter deck.

Observed non-blocking warnings remained:

- `hyperref` PDF-string warnings,
- repeated `pdfauthor` warnings from title-page metadata changes,
- `Underfull \hbox` warnings on content-dense slides,
- MiKTeX `log4cxx` logging-path warnings.

These warnings predate the ownership consolidation and do not block the compile result for this release.

## Pitfalls and Debugging Notes

### 1) This is not a public interface change

Users should still load the theme with `\usetheme{UP}`.
This version changes internal ownership, not the supported user-facing theme identifier.

### 2) Compatibility was intentionally preserved

Older `\usetheme{UU}` material is still a legacy path.
It is just no longer the primary implementation surface, and the code now says that clearly.

### 3) Documentation should not keep calling `beamerthemeUP.sty` a wrapper

Once the implementation lives in `beamerthemeUP.sty`, any remaining doc copy that still calls it a wrapper becomes misleading.
That is why this version updates both the guide and the showcase wording alongside the code change.

## Practice Task

Open these three files and answer the questions without using internal planning notes:

1. Which file now owns the theme orchestration?
2. What is `beamerthemeUU.sty` responsible for after `v0.3.3`?
3. Which public command should users keep using to load the theme?

If those answers are obvious from the tracked repository surfaces, the ownership consolidation is documented well enough.

## Next 24-72 Hours

1. Review whether any remaining public docs still describe `beamerthemeUP.sty` as a wrapper.
2. Decide whether future work should keep the `UU`-named subthemes indefinitely or begin a broader internal rename only when the migration value clearly outweighs the churn.
3. If broader release packaging proceeds, keep the public contract centered on `UP` and keep `UU` framed only as legacy compatibility.
