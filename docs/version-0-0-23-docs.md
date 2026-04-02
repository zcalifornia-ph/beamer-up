# Version v0.0.23 Documentation

## Title
Rebalanced the UP Cover Pages Around Trimmed Inline Lockups Instead of the Thin Standalone Wordmark

## Quick Diagnostic Read

This version is a focused title-page harmony pass.
It does four concrete things:

- rewires the non-`nl` cover pages to use trimmed inline UP logo-lockup assets,
- reshapes the title-page copy into one controlled left-aligned block,
- keeps content-slide header logos and closing-slide footer logos on their existing separate paths,
- records the local compile and text-layer verification for the first two title slides.

## One-Sentence Objective

Make the single-author and multi-author cover pages feel visually coherent again by giving the UP title mark enough visual weight and by tightening how the title-page text stack is composed.

## Why This Version Matters

The prior UP cover page technically worked, but it did not feel resolved.

The top-left mark was still based on the thinner standalone white wordmark path, and the cover copy was still laid out through separate full-width boxes.
That combination made the page read as disconnected pieces on a large maroon field:

- a light logo mark near the top edge,
- a large title block floating below it,
- metadata stacked beneath with less shared structure than the inherited Utrecht cover.

The Utrecht reference works better because the mark and the text block feel like parts of the same composition.
This version moves the UP cover in that direction without rewriting content-slide headers or the repaired thank page.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerthemeUU.sty`.
2. Inspect the non-`nl` logo-path configuration for title surfaces.
3. Open `beamer-up/beamerinnerthemeUU.sty`.
4. Inspect the `title page` template.
5. Compile `beamer-up/main.tex`.
6. Check pages 1 and 2.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Extract text from pages 1 and 2 of the rebuilt PDF.
3. Compare the updated cover-page structure against the inherited Utrecht cover reference.

## System View

The title-page path now looks like this:

```text
english / filipino option
  -> title-page-specific white inline UP lockup include
  -> explicit trim to visible bounds
  -> dedicated title-page width + anchor tuning
  -> one shared left-aligned content block
  -> title / subtitle / divider / metadata read as one composition
```

This matters because title-page harmony is not only about the asset choice.
It also depends on whether the chosen mark and the text stack are positioned as a single designed unit.

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerthemeUU.sty`

### Source assets added in this version

- `beamer-up/logos/up-inline-logo-eng-black.png`
- `beamer-up/logos/up-inline-logo-eng-white.png`
- `beamer-up/logos/up-inline-logo-tag-black.png`
- `beamer-up/logos/up-inline-logo-tag-white.png`
- `beamer-up/logos/up-inline-lineshot-eng-black.png`
- `beamer-up/logos/up-inline-lineshot-eng-white.png`
- `beamer-up/logos/up-inline-lineshot-tag-black.png`
- `beamer-up/logos/up-inline-lineshot-tag-white.png`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-23-docs.md`

### Generated verification outputs recorded in this version

- `beamer-up/main.aux`
- `beamer-up/main.bbl`
- `beamer-up/main.bcf`
- `beamer-up/main.blg`
- `beamer-up/main.fls`
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

## 1) The title page needed a stronger UP mark, not just more spacing

The earlier cover used the standalone white UP wordmark path.
That asset was usable, but on the maroon cover it did not provide enough structural weight relative to the title block below.

This version switches the title surface to the inline UP logo-lockup family instead.
After comparing the available inline options, the current implementation chose:

- `up-inline-logo-eng-white.png`
- `up-inline-logo-tag-white.png`

for the active cover path.

The lineshot variants were also added to the repository as source assets for future tuning, but the full inline logo pair gave the title page a better counterweight against the headline block.

## 2) The inline assets needed trimming before they were useful in TeX

The newly added inline PNGs are large canvases with the visible mark sitting inside substantial transparent padding.

If those files are placed directly, TeX anchors the padded rectangle instead of the visible logo.
That would preserve the same alignment problem in a different form.

This version fixes that by defining title-page-specific include macros in `beamer-up/beamerthemeUU.sty`:

- English cover path trims `up-inline-logo-eng-white.png`,
- Filipino cover path trims `up-inline-logo-tag-white.png`.

The trim values are based on the actual visible bounds of those files, and the title-page path gets its own width plus anchor offsets.

That separation is important because:

- content-slide headers still use their own header lockup path,
- closing slides still use their own horizontal white footer lockups,
- title-page tuning can now evolve without breaking the other surfaces.

## 3) The cover copy is now composed as one block instead of scattered boxes

The older title template relied on several separate `beamercolorbox` blocks stacked across a wide area.
That was functional, but it made the page feel looser than the Utrecht reference.

This version changes the title-page body in `beamer-up/beamerinnerthemeUU.sty` to a single controlled left-aligned `minipage` block.

Inside that block, the page now reads as one designed stack:

- title,
- subtitle,
- divider,
- author metadata,
- institute data,
- venue/date metadata when multi-author mode is active.

That change is small in code, but high-impact visually because it gives the cover a clearer internal spine.

## 4) The change is isolated to the cover pages

This pass does not retune the other logo surfaces.

Specifically unchanged:

- content-slide header lockups,
- automatic section-divider behavior,
- the repaired `\thankframe` layout,
- the lowered thank-page footer position,
- the bibliography/source correction.

That isolation matters because the user request was about the front / cover pages feeling visually unresolved, not a general logo-system rewrite.

## Verification

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
biber main
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdflatex -interaction=nonstopmode -halt-on-error main.tex
pdftotext -f 1 -l 2 main.pdf -
```

Observed result on April 2, 2026:

- the deck compiled successfully,
- the title pages used the new inline white UP cover mark,
- page 1 still exposed the title, subtitle, author, institute, and date,
- page 2 still exposed the multi-author and conference metadata,
- the title-page rebalance remained isolated to the cover surfaces.

## Pitfalls and Debugging Notes

### 1) Asset choice alone does not solve layout imbalance

Swapping a logo file without changing how the surrounding text stack is composed can leave the page feeling just as loose as before.

### 2) Transparent padding changes anchor behavior

Large PNG canvases often look fine in an image viewer but behave badly in TeX layout unless you trim them explicitly.

### 3) Title, header, and footer logo paths should not be conflated

The cover page, content header, and closing slide solve different layout problems.
Keeping separate asset paths is cleaner than forcing one logo treatment onto all three.

## Practice Task

Compile the showcase deck and inspect pages 1 and 2.

Self-check:

- the top-left UP mark feels substantial enough for the maroon cover,
- the title block reads as one composition rather than separate floating pieces,
- the multi-author slide still handles affiliations and venue/date cleanly,
- the title-page tuning does not spill into content-slide headers or the thank page.

## Next 24-72 Hours

1. Review the Filipino title-page route to confirm the same balance with the alternate inline lockup.
2. Decide whether the newly added inline lineshot variants should remain as future-use assets or be wired into another title-surface experiment later.
3. Remove the generated local build artifacts after review.
