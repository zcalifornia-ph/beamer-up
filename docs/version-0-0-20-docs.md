# Version v0.0.20 Documentation

## Title
Replaced the Inherited Utrecht Branding Citation with the UP Visual Identity Guide 2017 on the References Slide

## Quick Diagnostic Read

This version is a narrow bibliography-source correction.
It does four concrete things:

- replaces the inherited Utrecht corporate-identity bibliography metadata with a UP-specific guide source,
- renames the showcase cite key from `uubrand2025` to `upvig2017` so the implementation reads semantically cleanly,
- keeps the existing references-slide wording and numeric `biblatex` flow intact,
- records the full `pdflatex` plus `biber` verification cycle used to confirm the rendered entry on page 24.

## One-Sentence Objective

Make the bundled references slide cite the actual UP Visual Identity Guide 2017 instead of an inherited Utrecht branding page.

## Why This Version Matters

The showcase deck had already shifted its visual system, palette, typography guidance, and closing-slide assets toward the University of the Philippines.

But the references slide still carried one inherited branding citation from the original Utrecht-derived baseline.
That created a documentation mismatch:
the deck verbally pointed to UP branding guidance while the bibliography still resolved to Utrecht corporate-identity metadata.

This version closes that gap.
The references slide now points directly to a UP-hosted copy of the `UP Visual Identity Guide 2017`, which is the source the current deck should be anchored to when it describes UP palette, typography, and logo usage expectations.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/references.bib`.
2. Inspect the `upvig2017` entry.
3. Open `beamer-up/main.tex`.
4. Confirm the references frame cites `\cite{upvig2017}`.
5. Rebuild the deck with the full `pdflatex` / `biber` sequence.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Extract page 24 text from the rebuilt PDF.
3. Confirm that bibliography item `[3]` now starts with `University of the Philippines. UP Visual Identity Guide 2017.`

## System View

The corrected bibliography path now looks like this:

```text
references frame text in main.tex
  -> cite key upvig2017
  -> references.bib entry for UP Visual Identity Guide 2017
  -> biber-generated main.bbl
  -> rendered bibliography item [3] on page 24
```

This matters because bibliography corrections in a `biblatex` deck are not finished when the `.bib` file changes.
The `biber` output and the rendered slide have to agree.

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/main.tex`
- `beamer-up/references.bib`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-20-docs.md`

### Generated verification outputs recorded in this version

- `beamer-up/main.aux`
- `beamer-up/main.bbl`
- `beamer-up/main.bcf`
- `beamer-up/main.blg`
- `beamer-up/main.log`
- `beamer-up/main.nav`
- `beamer-up/main.out`
- `beamer-up/main.pdf`
- `beamer-up/main.run.xml`
- `beamer-up/main.snm`
- `beamer-up/main.toc`
- `beamer-up/main.vrb`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The fix was made at the bibliography layer, not by hardcoding slide text

The references slide in `beamer-up/main.tex` already described the source correctly at a high level:
it said the UP Visual Identity Guidebook defined palette, typography, and logo usage rules.

The mismatch lived underneath that sentence in the bibliography backend.
The older cite key still resolved to Utrecht corporate-identity metadata.

This version fixes the actual source entry in `beamer-up/references.bib` so the rendered evidence now matches the slide narrative.

## 2) The cite key was renamed to match the real source

The old key name, `uubrand2025`, encoded the wrong institution and the wrong conceptual source.

This version replaces it with:

- `upvig2017`

That is a small change, but it matters for maintainability.
Anyone reading the deck source can now tell immediately that the cite target is the UP Visual Identity Guide rather than a leftover Utrecht branding reference.

## 3) The rendered reference stays intentionally concise

The lookup context for this replacement included both:

- the UP-hosted PDF guide,
- the UP announcement page describing the guidebook release.

The final rendered bibliography entry intentionally points to the guide PDF itself.

That is the cleaner outcome for a Beamer references slide because:

- the cited artifact is the guide, not the announcement,
- the page remains easier to read,
- the bibliography item avoids unnecessary duplicate link noise.

## 4) Verification required the full `biblatex` rebuild cycle

This change could not be trusted after a single `pdflatex` run because `biblatex` caches bibliography output through `biber`.

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
biber main
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdftotext -f 24 -l 24 main.pdf -
```

Observed result on April 2, 2026:

- the deck compiled successfully through the full `biblatex` cycle,
- the references slide still rendered as the final page of the showcase deck,
- bibliography item `[3]` now began with `University of the Philippines. UP Visual Identity Guide 2017.`,
- the rendered URL now pointed to the UP-hosted guide PDF rather than the Utrecht identity-policy page.

## Pitfalls and Debugging Notes

### 1) A `.bib` edit alone is not enough in a `biblatex` workflow

Without rerunning `biber`, the PDF can keep showing stale bibliography content even when the source file is already correct.

### 2) Inherited cite-key names can hide documentation drift

The old key still worked technically, but it obscured the fact that the rendered source no longer matched the current UP-directed theme narrative.

### 3) Too many links make a Beamer references slide harder to scan

The final entry was intentionally kept to the UP guide PDF plus an access note so the slide remains readable.

## Practice Task

Rebuild the showcase deck and inspect the references slide.

Self-check:

- the inline sentence still says the UP Visual Identity Guidebook defines palette, typography, and logo usage rules,
- bibliography item `[3]` names the University of the Philippines,
- the title reads `UP Visual Identity Guide 2017`,
- the URL points to the UP-hosted PDF guide.

## Next 24-72 Hours

1. Review the rest of the showcase deck for any remaining inherited Utrecht reference text that should now point to UP-specific sources.
2. Decide whether any supporting announcement-page context belongs in prose documentation instead of the slide bibliography.
3. Remove the generated local bibliography verification artifacts after review.
