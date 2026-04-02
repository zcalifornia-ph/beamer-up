# Version v0.0.15 Documentation

## Title
Corrected the Final Closing-Slide Footer Crop for the Exact Horizontal White UP Logos

## Quick Diagnostic Read

This version is a second, narrower follow-up to the earlier `\thankframe` footer work.
It does four concrete things:

- keeps the exact horizontal white English and Filipino UP footer files the user required,
- replaces the earlier still-imperfect footer crop with language-specific trim boxes based on the actual visible bounds of each PNG,
- adjusts the footer anchor and rendered height so the cropped lockup sits inside the slide instead of touching the bottom edge,
- records the new local preview renders generated while validating the fix.

## One-Sentence Objective

Keep the exact requested horizontal white UP footer-logo files and make the full visible wordmark render cleanly inside the closing slide.

## Why This Version Matters

The prior footer-logo fix improved the closing slide, but the render was still wrong in practice.

The remaining problem was not the selected file and not the general closing-slide layout.
The problem was the crop math.

Those requested PNGs are large transparent canvases that store the visible seal and wordmark inside a smaller region, and they also carry `96 dpi` metadata.
That meant the previous `bp` trim values were not matching the actual visible-logo bounds closely enough, so the rendered footer still left the wordmark too low and partially clipped.

This version fixes that specific mismatch.
It keeps the exact requested files, keeps the same `english` / `filipino` selection behavior, and keeps the same beamer-uu-style closing-slide layout.
What changed is the trim geometry and the final footer placement.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerouterthemeUU.sty`.
2. Find the `\@upclosinglogoenginclude` and `\@upclosinglogotaginclude` helpers.
3. Compile `beamer-up/main.tex`.
4. Inspect the closing `Feedback?` slide footer.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Open the generated closing-slide preview PNG.
3. Compare it against the earlier clipped result.

## System View

The closing-slide footer path now looks like this:

```text
exact requested horizontal white UP asset
  -> language-specific trim box based on actual visible bounds
  -> height-based scaling for the footer slot
  -> centered bottom placement inside the beamer-uu-style thank frame
```

That matters because the user requirement was stricter than just “use a UP logo.”
The footer must use the exact requested English or Filipino file and still render the full visible mark inside the slide.

## Artifact Map

### Theme implementation surface updated in this version

- `beamer-up/beamerouterthemeUU.sty`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-15-docs.md`

### Temporary verification output recorded in this version

- `beamer-up/preview-page-23-current-23.png`
- `beamer-up/preview-page-23-fixed-23.png`
- `beamer-up/preview-page-23-seq-23.png`
- `beamer-up/preview-page-23-cropfix-23.png`

## Detailed Walkthrough

## 1) The exact requested footer files stay in place

The non-`nl` closing-slide path still points directly to:

- `beamer-up/logos/up-horizontal-logo-with-white-engtype.png`
- `beamer-up/logos/up-horizontal-logo-with-white-tagtype.png`

The selection rule is unchanged:

- `english` selects the English file,
- `filipino` selects the Filipino file,
- `nl` stays on the legacy compatibility fallback.

This version does not swap the footer back to a composed fallback mark.

## 2) The crop was corrected from actual visible-logo bounds

The visible logo content in these PNGs occupies a much smaller region than the full image canvas.
This version tightens the trim against the real nontransparent bounds instead of relying on the earlier rough crop.

That produced narrower, language-specific trim boxes:

- English trim: `12bp 596bp 11bp 641bp`
- Filipino trim: `212bp 596bp 211bp 641bp`

The result is that the footer include now keeps the real lockup instead of leaving too much invisible space below it.

## 3) Footer placement and scale were tuned around the corrected crop

After the trim was corrected, the footer placement could return to a more natural bottom offset and a slightly larger visible mark.

This version uses:

- bottom anchor at `yshift=0.95cm`,
- non-`nl` footer logo height `0.74cm`.

That keeps the exact requested lockup visible without pushing the wordmark into the bottom frame boundary.

## 4) Validation was done on the rendered closing slide, not only at compile time

This change is a rendering fix, so compile success by itself is not enough.

The local validation for this version used:

```sh
cd beamer-up
pdflatex main.tex
pdftoppm -f 23 -l 23 -png main.pdf preview-page-23-cropfix
```

The final rendered preview confirmed that the full `University of the Philippines` wordmark is visible on the closing slide.

## Compile and Validation Notes

Observed results from the local validation run on April 2, 2026:

- `pdflatex main.tex` completed successfully,
- the closing slide still loads `up-horizontal-logo-with-white-engtype.png` for the English showcase route,
- the rendered preview `beamer-up/preview-page-23-cropfix-23.png` shows the full footer wordmark instead of a clipped baseline fragment,
- the usual non-fatal MiKTeX log-permission noise remains outside the repo-controlled files.

## Pitfalls and Debugging Notes

### 1) “Safer crop” was not precise enough

A crop can be better than the previous one and still be wrong.
That is what happened here.

### 2) Transparent padding plus image DPI can mislead trim decisions

These PNGs have large transparent areas and `96 dpi` metadata.
If the crop values are chosen loosely, the rendered footer position will still be off even though the correct source asset is being used.

### 3) Render validation is mandatory for footer-logo work

The issue only becomes obvious on the final slide render.
Looking only at the TeX code or compile success is not sufficient.

## Practice Task

Compile the showcase deck twice:

1. once with `\usetheme[english]{UP}`,
2. once with `\usetheme[filipino]{UP}`.

Self-check:

- does each language route still load the exact requested horizontal white file,
- is the full visible wordmark above the bottom page edge,
- does the `nl` compatibility path remain unchanged.

## Next 24-72 Hours

1. Do a dedicated Filipino closing-slide render so the tightened Filipino trim is visually confirmed, not only code-routed.
2. Decide whether the large horizontal source files should eventually gain dedicated runtime-cropped footer assets.
3. Remove the temporary preview renders after review.
