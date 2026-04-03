# Version v0.0.8 Documentation

## Title
Drafted the `U-D` Visual Direction Baseline for `beamer-up`

## Quick Diagnostic Read

This version is a design-and-documentation milestone, not a full theme restyle.
It does four concrete things:

- locks the next visual direction to a restrained UP color system,
- defines the typography and asset-usage rules before template edits begin,
- records the contrast decisions that should govern the next styling bolt,
- updates the public docs so contributors know the current gate is visual approval, not loader migration.

## One-Sentence Objective

Set an explicit, reviewable UP-directed visual contract for the next template-styling milestone so the theme does not drift through ad-hoc color and logo decisions.

## Why This Version Matters

The repository already solved one major ambiguity: the public loader is now `UP`.
What remained ambiguous was the visual direction.

Without a locked visual mapping, the next styling work would risk mixing:

- inherited Utrecht-era styling habits,
- loosely remembered UP brand assumptions,
- and readability decisions made too late, inside template code.

This version closes that gap by making the visual rules explicit before implementation.

## Plan A / Plan B

### Plan A (Recommended)

1. Read `README.md` for the current public project status.
2. Read `CHANGELOG.md` for the short release summary.
3. Read this file for the full rationale and the decisions the next styling bolt should follow.

### Plan B

1. Open `beamer-up/main.tex`, `beamer-up/beamercolorthemeUU.sty`, `beamer-up/beamerinnerthemeUU.sty`, and `beamer-up/beamerouterthemeUU.sty`.
2. Compare the inherited yellow-led and multi-hue styling against the guidance summarized below.
3. Use the "Next 24-72 Hours" section to orient the next implementation step.

## System View

The repo staging now looks like this:

```text
approved governance baseline
  -> approved brownfield models
  -> implemented UP public loader
  -> drafted UP visual direction baseline
  -> next template-styling bolt
  -> later showcase, validation, and packaging work
```

That sequence matters because the visual-system rewrite can now follow an explicit contract instead of inventing the contract while editing the theme.

## Artifact Map

### Updated public docs

- `README.md`
- `CHANGELOG.md`
- `docs/version-0-0-8-docs.md`

### Public implementation surfaces the next bolt will restyle

- `beamer-up/beamercolorthemeUU.sty`
- `beamer-up/beamerinnerthemeUU.sty`
- `beamer-up/beamerouterthemeUU.sty`
- `beamer-up/main.tex`

## Detailed Walkthrough

## 1) The palette is now constrained

The next UP-directed styling pass should center on four institutional colors:

- maroon as the primary field color,
- forest green as the complementary structural color,
- gold as an accent color,
- spot black as the main dark neutral.

This matters because the inherited theme still teaches a broader rainbow-like palette directly in the demo deck and supporting templates.

The baseline direction now rejects that broader palette for normal public output.

## 2) Contrast decisions are explicit now

The visual-direction baseline now treats readability as an up-front rule rather than a final screenshot judgment.

Key approved pairings:

- white on maroon,
- white on forest green,
- dark text on gold,
- maroon on gold for limited emphasis.

Explicitly rejected pairing:

- white on gold.

That single rejection is important because gold works as an accent but fails as a broad reversed-text field.

## 3) Typography is now framed as a hierarchy, not a guess

The UP guide points in a different direction than the current Merriweather and Open Sans story.
The baseline therefore treats typography as a deliberate hierarchy:

- Padayon stays reserved for logo artwork only,
- heading treatment should move toward Optima-like behavior,
- body copy should move toward a Palatino-based baseline,
- auxiliary sans behavior may use Avenir or Helvetica style fallbacks where appropriate.

This is still a planning milestone, so it does not yet claim that the checked-in theme implementation has switched to that hierarchy.

## 4) Logo and oblation usage is now bounded

This version also clarifies how the next styling bolt should treat official assets.

The current direction is:

- use the official logo as a genuine identity element, not as a decorative texture,
- keep the seal legible if `showlogo` remains active on content slides,
- use the oblation only as a whole silhouette with pedestal and sufficient clear space,
- avoid watermark-like, clipped, or pseudo-heraldic treatments.

That matters because unofficial decorative use is one of the fastest ways a theme can look careless even when the colors are correct.

## 5) Decorative cleanup is now part of the plan

The inherited title-page rayburst and gradient wash are now classified as styling that should be retired in the next bolt.

The replacement direction is simpler:

- solid maroon or forest-green fields,
- restrained gold rules,
- spacing and hierarchy doing most of the work,
- fewer ornamental effects competing with the official assets.

This is a stronger fit for a guide-constrained derivative than keeping old motifs and swapping logos on top.

## What This Version Does Not Claim

This version does not claim that the full visual rewrite is finished.

It does not yet:

- restyle the checked-in templates,
- replace all Utrecht-facing demo text,
- or complete the validation and packaging milestone.

Those belong to the next bolts.

## Validation and Evidence

The evidence basis for this version is the combination of:

- the checked-in UP logo and oblation assets,
- the current inherited theme surfaces in the Beamer files and demo deck,
- the UP Visual Identity Guidebook,
- the recorded contrast decisions used to approve or reject key color pairings.

This makes the milestone reviewable even before the next template edits land.

## Practice Task

Before reading implementation code, answer these three questions from the public docs alone:

1. Which colors should dominate the next UP-styled theme revision?
2. Why is gold treated as an accent instead of a primary text field?
3. What is the next major task after this version?

If the public docs let you answer those quickly, the milestone write-up is doing its job.

## Self-Check

You understood this version if you can explain:

- why the repo needed a visual-direction baseline before a styling bolt,
- why a constrained four-color system is more defensible than preserving the inherited multi-hue palette,
- why asset handling rules matter separately from color choices.

## Next 24-72 Hours

1. Review and approve the drafted `U-D` visual-direction baseline.
2. Apply the approved rules to the theme templates and the bundled showcase deck.
3. Replace remaining Utrecht-facing visual language in normal presentation content.
4. Prepare validation evidence and distribution notes once the styled output settles.
