# Version v0.0.29 Documentation

## Title
Returned the Light-Surface Title-Page Venue/Date Separator to Forest Green

## Quick Diagnostic Read

This version is a very narrow title-page follow-up.
It does three concrete things:

- switches the venue/date separator dot in `\uutitlemeta` from `UPMaroon` back to `UPForestGreen`,
- revalidates the bundled showcase deck on the supported `pdfLaTeX` path,
- advances the public root docs to `v0.0.29` so they describe the current checked-in theme state accurately.

## One-Sentence Objective

Keep the light-surface title-page accent system coherent by leaving the divider maroon while moving the smaller venue/date separator back to the same forest-green accent family already used by the conference affiliation markers.

## Why This Version Matters

`v0.0.27` established the broader title-page polish pass:

- bold dark subtitle,
- maroon divider,
- forest-green affiliation markers,
- refreshed title-page showcase metadata.

The remaining follow-up is smaller, but still visible:

- the conference affiliation markers were green,
- the nearby title-page version badge was green,
- but the venue/date separator had been left maroon.

That made the metadata accents feel split across two competing emphasis colors.
This version narrows the treatment so the divider remains the stronger maroon separator while the smaller metadata dot returns to forest green.

## Plan A / Plan B

### Plan A (Recommended)

1. Open `beamer-up/beamerinnerthemeUU.sty`.
2. Inspect `\uutitlemeta`.
3. Change only the separator-dot color token.
4. Compile `beamer-up/main.tex` with `pdflatex`.
5. Update the root release docs to match the actual checked-in theme state.

### Plan B

1. Compare the current `v0.0.28` root docs against the live `.sty` diff.
2. Confirm that only the venue/date separator dot changed in code.
3. Confirm that the updated `README.md`, `CHANGELOG.md`, and this version note now describe the separator as forest green.

## System View

```text
light-surface title page
  -> maroon left accent bar
  -> runtime-cropped inline black UP cover lockup
  -> bold dark subtitle
  -> maroon divider
  -> forest-green venue/date separator
  -> forest-green conference affiliation markers
```

The key design point is that the divider keeps the heavier maroon emphasis while the smaller metadata accents now align with the existing green conference markers.

## Artifact Map

### Implementation surfaces updated in this version

- `beamer-up/beamerinnerthemeUU.sty`

### Public documentation updated in this version

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-29-docs.md`

### Public governance docs reviewed but not changed

- `SECURITY.md`
- `CONTRIBUTING.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The code change is intentionally one line wide

The implementation change in this version is narrow by design.

Inside `\uutitlemeta`, the dot printed between `\@uuvenue` and `\insertdate` now uses `UPForestGreen` again.

Nothing else in the title-page template is reopened here:

- the bold subtitle stays as-is,
- the divider rule stays maroon,
- the affiliation superscripts and numbered affiliation list stay forest green,
- the showcase metadata stays unchanged.

That keeps this version honest and tightly scoped.

## 2) The title-page accent hierarchy is cleaner after the follow-up

On the light title-page surface, accent colors matter more because there is less background saturation doing visual work.

The current arrangement is now:

- maroon for the stronger structural divider,
- forest green for the smaller metadata accents,
- dark text for the primary reading copy.

That is a cleaner hierarchy than treating both the divider and the metadata separator as equally maroon.

## 3) The root docs now match the real checked-in theme state again

Before this update, the root docs still described the current cover baseline as if the venue/date separator remained maroon.

This version updates the public root documentation so it now says what the live code actually does:

- `README.md` now publishes `v0.0.29`,
- the current-state wording describes the divider as maroon and the venue/date separator as forest green,
- `CHANGELOG.md` records this as a narrow code-bearing follow-up rather than another docs-only pass.

That matters because `commit.task` is supposed to describe the real git diff, not the previous intent.

## Validation

The local verification for this version used:

```sh
cd beamer-up
pdflatex -interaction=nonstopmode -halt-on-error main.tex
```

Observed result on April 3, 2026:

- the deck compiled successfully on the supported `pdfLaTeX` path,
- the single-author and multi-author title slides remained intact,
- the title-page divider stayed maroon,
- the venue/date separator dot rendered forest green,
- the conference affiliation markers remained forest green.

The existing bibliography warnings remain outside the scope of this narrow visual follow-up because `biber` was not rerun here.

## Pitfalls and Debugging Notes

### 1) Tiny color tweaks still need release-note accuracy

Even when the code diff is one line, the root docs still need to move with it.
Otherwise the public README and changelog stop describing the current baseline truthfully.

### 2) Divider accents and metadata accents do not have to share one color

The stronger structural separator and the smaller metadata dot serve different visual roles.
Keeping both maroon is not automatically more consistent if the smaller metadata accents are otherwise green.

### 3) Compile validation is enough for this follow-up

This change does not reopen bibliography, logo-path, or engine-selection behavior.
One successful `pdflatex` rebuild is the correct validation scope here.

## Practice Task

Compile the showcase deck and inspect the first two title pages.

Self-check:

- the subtitle is still bold and dark,
- the divider rule is still maroon,
- the venue/date separator dot is forest green,
- the conference affiliation markers remain forest green,
- the title-page layout is otherwise unchanged.

## Next 24-72 Hours

1. Decide whether the current green metadata accents are now final for the light-surface title-page baseline.
2. Re-run the full `pdflatex -> biber -> pdflatex -> pdflatex` sequence if the bundled PDF should also clear bibliography warning noise.
3. Continue release-packaging and broader compile validation for the first public release.
