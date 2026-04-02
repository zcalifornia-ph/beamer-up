# Version v0.1.2 Documentation

## Title
Sanitized the Public Root Docs and Refreshed the Repository Screenshot Asset

## Quick Diagnostic Read

This patch release is a public-surface cleanup pass.
It does three concrete things:

- removes references in the root public docs to ignored internal planning paths,
- replaces specific ignored LaTeX artifact naming with generic public cleanup wording,
- refreshes the repository screenshot asset used on the front page.

## One-Sentence Objective

Keep the public repository surface truthful, release-safe, and aligned with the current checked-in showcase output without exposing ignored internal workflow details.

## Why This Version Matters

The public root docs and screenshot are part of the repository's release surface.
If they expose ignored internal planning paths or overly specific local artifact names, they stop behaving like clean public documentation.

This version matters because it tightens that boundary:

- the README no longer points readers at ignored internal planning or traceability paths,
- the changelog no longer spells out ignored local artifact patterns as if they were public-facing inventory,
- the screenshot asset used on the repository front page now matches the current public showcase baseline.

## Plan A / Plan B

### Plan A (Recommended)

1. Audit the root public docs against `.gitignore`.
2. Replace ignored-path references with generic public wording.
3. Keep the public docs focused on shipped surfaces only.
4. Refresh the repository screenshot asset to match the current visible baseline.
5. Publish a new versioned docs note so the public trail stays continuous.

### Plan B

1. Leave the docs as-is.
2. Treat ignored internal path references as harmless.

Plan B is faster, but it weakens the public/private boundary the repository rules explicitly require.

## System View

```text
gitignored internal planning + local LaTeX outputs
  -> must not be described explicitly in root public docs
  -> README.md / CHANGELOG.md should stay public-facing
  -> repo/images/project_screen.png should represent the current showcase baseline
  -> docs/version-0-1-2-docs.md records the cleanup rationale
```

## Artifact Map

### Root docs updated in this version

- `README.md`
- `CHANGELOG.md`

### Versioned public docs added in this version

- `docs/version-0-1-2-docs.md`

### Public asset updated in this version

- `repo/images/project_screen.png`

### Governance docs reviewed but not changed

- `CONTRIBUTING.md`
- `SECURITY.md`
- `CODE_OF_CONDUCT.md`

## Detailed Walkthrough

## 1) The root README now stays on the public side of the boundary

The previous root README still mentioned ignored internal planning/traceability surfaces indirectly through path-level wording.
This version keeps the important public facts but removes that internal-path leakage.

What remains in public view:

- the supported `UP` loader,
- the current visual and compile baseline,
- the public repository layout,
- the release-facing screenshot link.

What is no longer spelled out:

- ignored internal planning or traceability paths that are not meant to be part of the public repo contract.

## 2) The changelog now uses generic cleanup language

The repository rules explicitly say not to reference files mentioned in `.gitignore` inside the root public docs.
That means local LaTeX cleanup notes should stay generic.

This version therefore keeps the cleanup warning but expresses it as:

- generated local LaTeX build outputs for the bundled showcase deck remain cleanup candidates.

That keeps the meaning while avoiding publication of ignored artifact patterns as if they were part of the supported surface.

## 3) The repository screenshot asset was refreshed

The front-page screenshot is a public-facing project artifact.
When the visible showcase baseline changes, the screenshot should not lag behind it.

This version updates `repo/images/project_screen.png` so the repository landing surface better reflects the current checked-in showcase state.

## Validation

Validation for this version was a documentation-and-surface audit:

- checked the root public docs against `.gitignore`,
- removed ignored internal path references from `README.md` and `CHANGELOG.md`,
- confirmed the unchanged governance docs did not require equivalent cleanup,
- confirmed the front-page screenshot asset is present and tracked at `repo/images/project_screen.png`.

## Pitfalls and Debugging Notes

### 1) Public docs should describe the release surface, not the internal workflow scaffolding

Even if an ignored path exists in the repository, that does not make it appropriate to document publicly.

### 2) Cleanup notes still matter, but they should be generic

The right fix is not to remove all cleanup guidance.
The right fix is to keep it public-safe and non-revealing.

### 3) Screenshots are documentation too

If the screenshot drifts behind the current checked-in visual baseline, the README becomes less trustworthy even when the code is correct.

## Practice Task

Open `README.md`, `CHANGELOG.md`, and `.gitignore` side by side.

Self-check:

- the root docs no longer spell out ignored internal planning paths,
- cleanup wording stays generic instead of listing ignored LaTeX artifact names,
- the public docs trail now extends through `docs/version-0-1-2-docs.md`.

## Next 24-72 Hours

1. Capture and keep any future screenshot refreshes coupled to the visible showcase changes they document.
2. Continue validating the bundled showcase deck before the next release-facing packaging pass.
3. Keep future public-doc updates checked against `.gitignore` so hidden/internal surfaces do not leak back into the root docs.
