# Version v0.0.18 Documentation

## Title
Enlarged the UP Feedback-Page Footer Logo to Match the Inherited Utrecht Footer Weight More Closely

## Quick Diagnostic Read

This version is a narrow closing-slide follow-up.
It does four concrete things:

- keeps the exact horizontal white English and Filipino UP footer-logo files,
- replaces the earlier too-small UP footer scale with a dedicated larger height constant,
- preserves the existing trim boxes and legacy `nl` compatibility path,
- records the local compile and rendered-slide verification for the updated footer size.

## One-Sentence Objective

Make the UP feedback-page footer logo read closer in perceived size to the inherited Utrecht University footer mark without clipping the selected UP lockup.

## Why This Version Matters

The earlier footer-logo work solved the clipping problem, but it left the UP footer mark too visually timid next to the inherited beamer-uu reference.

That meant the implementation was technically correct:

- the exact requested horizontal UP assets were in use,
- the full visible mark stayed inside the slide,
- the language-selection behavior still worked.

But the final feedback-page surface still felt off because the footer logo carried much less visual weight than the Utrecht footer mark it was meant to parallel.

This version fixes that narrower issue by raising the rendered footer size while keeping the already-correct crop math and footer placement model.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerouterthemeUU.sty`.
2. Find `\@upclosinglogoheight`.
3. Compile `beamer-up/main.tex`.
4. Inspect the `Feedback?` closing slide.

### Plan B

1. Read `CHANGELOG.md` for the short release summary.
2. Compare the current UP closing slide against the inherited Utrecht feedback-page reference.
3. Check whether the footer mark now reads as intentionally sized rather than underscaled.

## System View

The relevant closing-slide path now looks like this:

```text
exact horizontal white UP footer asset
  -> language-specific trim box
  -> dedicated footer height constant (1.10cm)
  -> centered closing-slide placement
  -> larger perceived footer weight without clipping
```

This matters because the user requirement here was not to swap assets or redesign the page.
It was to keep the current UP footer path and make it feel as substantial as the inherited Utrecht footer mark.

## Artifact Map

### Theme implementation surface updated in this version

- `beamer-up/beamerouterthemeUU.sty`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-18-docs.md`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The footer-size change is isolated to the UP closing-logo path

The Utrecht compatibility branch already had its own footer treatment.
The issue was specifically in the non-`nl` UP path, where the footer mark was still being included at:

- `0.74cm`

That value kept the wordmark safe from clipping, but it made the final logo read too small on the closing slide.

This version raises that path to a dedicated constant:

- `\@upclosinglogoheight = 1.10cm`

The point of the constant is practical:

- the value is easier to tune later,
- the footer-height decision is no longer buried inline inside `\thankframe`,
- the closing-logo scale is now a first-class theme parameter.

## 2) The exact requested UP footer assets remain unchanged

This version does not replace the current files.
The non-`nl` closing-slide path still points to:

- `beamer-up/logos/up-horizontal-logo-with-white-engtype.png`
- `beamer-up/logos/up-horizontal-logo-with-white-tagtype.png`

The selection rule is still:

- `english` -> English file,
- `filipino` -> Filipino file,
- `nl` -> legacy compatibility fallback.

That matters because this fix is about visual weight, not asset substitution.

## 3) The trim math stays intact

The previous closing-slide fixes already established trim values based on the visible logo bounds.
Those trims solved the clipping defect.

This version leaves those trim boxes alone.
Only the rendered height changes.

That is the correct narrow fix because the old problem and the new problem are different:

- clipping was a crop-and-placement issue,
- underscaled perception was a size issue.

Changing only the height keeps the fix scoped tightly to the real remaining defect.

## 4) Verification required both compile success and rendered-slide inspection

This footer change cannot be validated from TeX code alone.
The slide has to be rendered and judged visually.

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode main.tex
```

Then the closing slide was rendered and inspected directly.

Observed result on April 2, 2026:

- the deck still compiled successfully,
- the English showcase route still loaded the exact horizontal white UP footer asset,
- the enlarged footer mark stayed fully inside the page,
- the closing-slide logo now reads closer in perceived size to the inherited Utrecht footer mark.

## Pitfalls and Debugging Notes

### 1) “Not clipped” is not the same as “correctly sized”

A footer logo can be technically safe and still feel visually wrong.
That is exactly what happened here.

### 2) Transparent source canvases still distort intuition

These horizontal UP assets sit inside large transparent PNG canvases.
That makes visual-weight tuning much harder if you do not first solve the trim problem.

### 3) Use a named constant for small visual tuning loops

Once the trim is right, size tuning should be isolated to one explicit parameter.
That makes later adjustment much safer than repeatedly editing inline numeric literals.

## Practice Task

Compile the showcase deck and compare:

1. the current UP `Feedback?` closing slide,
2. the inherited Utrecht feedback-page reference.

Self-check:

- the UP footer mark should feel materially larger than before,
- the full visible wordmark should still remain inside the page,
- the `nl` fallback path should remain unchanged.

## Next 24-72 Hours

1. Run the same closing-slide check on the Filipino path so both language routes are visually confirmed at the new footer size.
2. Decide whether the closing-logo height constant should stay private or become a documented tuning hook.
3. Clean up generated local LaTeX verification artifacts after review.
