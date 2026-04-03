# Version v0.0.30 Documentation

## Title
Replaced the First Numeric Bibliography Item with the Paper-thin Threads Web Citation

## Quick Diagnostic Read

This version is a narrow bibliography-source follow-up.
It does three concrete things:

- replaces the source behind the reused `tai1994mathematical` entry in `beamer-up/references.bib`,
- revalidates the bundled showcase bibliography with the full `pdflatex -> biber -> pdflatex -> pdflatex` chain,
- advances the public root docs to `v0.0.30` so they describe the staged bibliography change accurately.

## One-Sentence Objective

Keep the bundled numeric bibliography example aligned with the requested citation by swapping the source data behind the first cited item without changing the cite order or reopening unrelated theme behavior.

## Why This Version Matters

The bundled showcase deck cites three bibliography items in order:

- `[1]` comes from `\cite{tai1994mathematical}` on the mathematical-typesetting slide,
- `[2]` comes from the Beamer guide citation,
- `[3]` remains the UP Visual Identity Guide reference on the references slide.

That means the requested update was not about moving bibliography order around.
It was about replacing the data attached to the already-first citation key.

This version keeps that scope honest:

- `main.tex` does not need a new cite key,
- the first rendered bibliography item changes,
- the UP branding guide citation remains in place as a later item,
- unrelated title-page and theme work stays out of this commit-task pass.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/references.bib`.
2. Replace the body of `tai1994mathematical` with the requested web-citation metadata.
3. Rebuild the deck with `pdflatex`, `biber`, and two final `pdflatex` passes.
4. Extract page-24 text to confirm the rendered `[1]` bibliography item changed as expected.
5. Update the root release docs to match the actual staged diff.

### Plan B

1. Inspect `git diff --cached -- beamer-up/references.bib`.
2. Confirm that only the cited bibliography record changed in the staged scope.
3. Update the root docs from that staged context without pulling in unrelated unstaged theme edits.

## System View

```text
math slide
  -> \cite{tai1994mathematical}
  -> numeric bibliography order locks this as item [1]
  -> references.bib entry data controls rendered author/title/source text
  -> full biber refresh required before trusting the PDF
```

The key point is that the first rendered bibliography item is controlled by citation order plus the source record, not by whichever `.bib` entry happens to appear first in the file.

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/references.bib`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-30-docs.md`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The staged code change is a source-record replacement, not a cite-order rewrite

The staged diff replaces the old diabetes-paper metadata attached to `tai1994mathematical` with the requested web citation:

- author: `Zildjian E California`,
- title: `"Paper-thin Threads: Stecker, Art, and Computing"`,
- source/date string: `Zildjian California, Feb. 10, 2026`,
- URL: `https://zecalifornia.com/blog/paper-thin-threads`.

The citation key remains the same on purpose.

That means:

- the math slide still cites `\cite{tai1994mathematical}`,
- the first bibliography slot remains `[1]`,
- only the rendered content of item `[1]` changes.

## 2) The rest of the bibliography stays structurally intact

This version does not reopen the already-corrected UP branding reference.

After the change:

- `[1]` is now the requested web citation,
- `[2]` is still the Beamer guide,
- `[3]` still cites `UP Visual Identity Guide 2017`.

That matters because the requested edit was targeted to the first bibliography item, not a reversal of the later UP-specific branding fix.

## 3) The validation scope had to include `biber`

This could not be trusted after a single `pdflatex` pass because the deck uses `biblatex` with `backend=biber`.

The verification path used here was:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
biber main
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdftotext -f 24 -l 24 main.pdf -
```

The page-24 text extraction confirmed that the rendered entry now appears as:

`Zildjian E California. "Paper-thin Threads: Stecker, Art, and Computing". Zildjian California, Feb. 10, 2026. URL: https://zecalifornia.com/blog/paper-thin-threads.`

The `URL:` label is still produced by the existing numeric `biblatex` style, which this version intentionally leaves unchanged.

## 4) The root docs now describe only the staged scope

Because the user requested a `commit.task` pass for staged changes only, the documentation updates here are deliberately narrow.

They describe:

- the bibliography-entry swap in `references.bib`,
- the verification sequence used for that swap,
- the resulting `v0.0.30` public baseline.

They do not describe:

- the unrelated unstaged `beamerouterthemeUU.sty` change,
- the untracked preview assets in the working tree,
- any other work outside the staged bibliography diff.

## Validation

Observed result on April 3, 2026:

- the showcase deck rebuilt successfully with the full bibliography-refresh sequence,
- bibliography item `[1]` now renders the requested Zildjian California source,
- bibliography items `[2]` and `[3]` stayed in their existing order,
- the current root docs now describe the staged change as `v0.0.30`.

## Pitfalls and Debugging Notes

### 1) The first rendered bibliography item is not necessarily the first `.bib` record

Numeric bibliography order follows citation order in the document.
If you want to change `[1]`, inspect the cite key used first in `main.tex` before editing records blindly.

### 2) Reusing an old cite key is acceptable when the request is about rendered output, not semantic history

Here the user asked to replace the first bibliography item itself.
Keeping the existing `tai1994mathematical` key avoided unnecessary document-structure edits.

### 3) Bibliography edits are incomplete until `biber` runs

If you skip `biber`, the PDF can keep showing stale bibliography content even when `references.bib` is already correct.

## Practice Task

Open `beamer-up/main.tex` and trace which cite key controls each numbered bibliography item on the references slide.

Self-check:

- you can explain why `tai1994mathematical` maps to `[1]`,
- you can explain why `upvig2017` remains `[3]`,
- you know why a source-record edit was enough for this request.

## Next 24-72 Hours

1. Decide whether the reused `tai1994mathematical` key should eventually be renamed for semantic clarity in a later cleanup pass.
2. Stage the updated root docs if this `commit.task` output should ship as one `v0.0.30` commit.
3. Remove generated local showcase build outputs when release-packaging cleanup is appropriate.
