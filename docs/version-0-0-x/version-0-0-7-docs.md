# Version v0.0.7 Documentation

## Title
Implemented and Approved `UP` Public Theme Interface for `beamer-up`

## Quick Diagnostic Read

This version turns the planned `UP` interface into the checked-in public reality.
It does four concrete things:

- adds `beamerthemeUP.sty` as the canonical public loader,
- moves the bundled demo and public snippets to `\usetheme{UP}`,
- keeps direct `\usetheme{UU}` loading only as a deprecated compatibility bridge,
- updates the public docs so contributors are pointed at visual adaptation work next instead of interface migration.

## One-Sentence Objective

Complete the first-release public theme migration from inherited `UU` loading to supported `UP` loading without breaking the existing option and helper surface.

## Why This Version Matters

Before this version, the repository had an approved migration policy but not the implemented public interface.
That meant the docs could explain the intended direction, yet the shipped theme still depended on inherited `UU` entry points.

This version closes that gap.
The repository now has one supported public loader, one explicit compatibility bridge, and one clearer next milestone.

## Plan A / Plan B

### Plan A (Recommended)

1. Read the updated root `README.md`.
2. Read `CHANGELOG.md` for the short release summary.
3. Open `beamer-up/beamerthemeUP.sty`, `beamer-up/beamerthemeUU.sty`, and `beamer-up/main.tex` to see how the migration was implemented.

### Plan B

1. Open `beamer-up/main.tex` and confirm the demo now loads through `\usetheme{UP}`.
2. Open `beamer-up/beamerthemeUU.sty` and confirm direct `UU` loading now emits deprecation guidance.
3. Use the README roadmap and next-actions sections to orient the next work in `U-D`.

## System View

The public migration path is now:

```text
approved governance + brownfield baseline
  -> approved UP migration plan
  -> implemented UP wrapper loader
  -> deprecated UU compatibility bridge
  -> next visual adaptation work for title, content, and closing-slide surfaces
```

That matters because the repo no longer asks contributors to guess whether the public contract is planned or shipped.

## Artifact Map

### Public interface implementation

- `beamer-up/beamerthemeUP.sty`
- `beamer-up/beamerthemeUU.sty`
- `beamer-up/main.tex`

### Updated public docs

- `README.md`
- `CHANGELOG.md`
- `CONTRIBUTING.md`
- `docs/version-0-0-7-docs.md`

## Detailed Walkthrough

## 1) The canonical public loader now exists

`beamerthemeUP.sty` is now the supported public entry point.
It passes the existing option surface through to the inherited implementation layer so the migration stays small and controlled.

This keeps the first-release public contract simple:

- users load `UP`,
- existing options keep working,
- helper commands remain available through the current implementation.

## 2) Direct `UU` loading is now explicitly deprecated

`beamerthemeUU.sty` is still present because the codebase is brownfield and some internal naming is still inherited.
But it is no longer presented as the supported public path.

Instead, this version makes the compatibility posture explicit:

- `UU` remains only as a transition bridge,
- direct legacy loads now emit a package warning,
- public documentation points new users to `UP`.

That is a better migration contract than silently supporting two coequal public loaders.

## 3) The showcase deck now exercises the supported interface

`beamer-up/main.tex` now loads `\usetheme{UP}` and updates its explanatory slides accordingly.
That matters because the sample deck is the fastest way contributors and users learn the project surface.

The deck now teaches:

- `UP` basic usage,
- `UP` option usage,
- the continued presence of legacy `UU` compatibility,
- the current file split between the public wrapper and inherited implementation files.

## 4) The root docs now match the shipped interface

The root `README.md` and `CHANGELOG.md` no longer describe `UP` as merely drafted or pending.
They now describe the actual shipped state:

- `UP` is implemented,
- compile validation already exists,
- `UU` is deprecated compatibility,
- the next major workstream is visual adaptation rather than interface migration.

`CONTRIBUTING.md` was also tightened so contributors do not accidentally reintroduce `UU` as the public-facing default in examples or screenshots.

## 5) The next milestone is now clearer

With the public loader migration complete, the repo can move to the next real design problem:

- adapting the inherited Utrecht-oriented visual language toward a deliberate UP presentation identity,
- replacing remaining Utrecht-facing slide copy and styling,
- preparing the deck and docs for later release packaging.

That is a better staging point for contributors than mixing interface migration and visual redesign in the same bolt.

## Validation and Evidence

The evidence for this version includes:

- the checked-in `beamerthemeUP.sty` public loader,
- the deprecation guidance added to `beamerthemeUU.sty`,
- the bundled demo source now loading `UP` in `beamer-up/main.tex`,
- the already recorded successful local compile validation on April 1, 2026 for the `UP` path,
- the root-doc consistency review across `README.md`, `CHANGELOG.md`, and `CONTRIBUTING.md`.

This version is an implementation-and-docs milestone.
It is not yet the visual redesign milestone.

## Practice Task

Without checking internal maintainer records, answer these three questions from the public repo surface alone:

1. What command loads the supported theme today?
2. What happens if someone still loads `\usetheme{UU}` directly?
3. What kind of work comes next after this version?

If the public docs let you answer all three quickly, the migration documentation is doing its job.

## Self-Check

You understood this version if you can explain:

- why adding `beamerthemeUP.sty` is better than renaming everything at once,
- why `UU` is still present but no longer the supported public interface,
- why the repo should move into visual adaptation next instead of reopening interface-planning work.

## Next 24-72 Hours

1. Approve the `U-D` visual-direction baseline.
2. Define the UP palette, typography, logo, and decorative mapping for key slide surfaces.
3. Replace remaining Utrecht-facing visual output in the demo and theme templates.
4. Prepare the next packaging and validation notes once the visual system stabilizes.
