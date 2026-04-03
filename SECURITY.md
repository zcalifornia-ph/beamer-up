# Security Policy

## Repository Scope

`beamer-up` is a LaTeX/Beamer theme repository.
This repository is an independently maintained derivative distribution; do not treat the original `beamer-uu` author or Utrecht University as the support channel for `beamer-up`.
The supported public theme loader is `UP`; any remaining `UU`-derived identifiers are relevant only insofar as they affect compile safety, provenance, or migration integrity.
Security reports are welcome for issues that could cause unsafe execution, harmful build behavior, accidental credential disclosure, or supply-chain risk in the repository's materials and instructions.
Reports are also welcome for packaging or release issues that strip `LPPL 1.3c` notices or obscure whether distributed files are modified derivatives, because that creates provenance and downstream trust risk.

Examples in scope:

- TeX or build changes that require unsafe shell execution such as `--shell-escape` without clear need or warning.
- Malicious or surprising macros, scripts, or embedded assets that could affect normal compilation.
- Sensitive data accidentally committed to the repository, screenshots, or release materials.
- Dependency or packaging guidance that materially increases downstream risk for users compiling the theme.
- Release or distribution changes that remove license or provenance cues needed to identify modified LPPL-covered files.

Out of scope:

- purely aesthetic or non-security design feedback
- local TeX distribution problems not caused by repository contents
- third-party service outages or upstream package issues outside this repository's control

## Security Principles

We treat security as part of quality.
Our approach emphasizes:

- responsible stewardship of user and contributor trust
- ethical, professional, and evidence-based issue handling
- inclusive and respectful collaboration during incident response
- continuous improvement through post-incident learning

## Supported Versions

| Version | Supported |
| --- | --- |
| `1.0.0` | :white_check_mark: |
| `0.4.0` and earlier `0.x` preparation baselines, plus unpublished archives | :x: |

## Reporting a Vulnerability

Use coordinated disclosure.
Do not open public issues for suspected vulnerabilities.
Report issues for this derivative distribution to the repository maintainer rather than to upstream.

Send reports to `zecalifornia@up.edu.ph` with:

- affected file, workflow, or release artifact
- reproduction steps or proof of concept
- impact assessment and severity estimate
- whether the issue affects bundled license text, attribution, or derivative-work provenance
- suggested mitigation or patch, if available

## Response Targets

- acknowledgment within 72 hours
- initial triage within 7 calendar days
- best-effort remediation plan within 30 calendar days

Complex issues may require more time; maintainers will provide status updates during triage and remediation.

## Safe Handling and Disclosure

- We will coordinate disclosure timing with the reporter after a fix or mitigation is available.
- We will credit reporters unless anonymity is requested.
- We ask reporters to avoid privacy violations, service disruption, or data destruction during testing.
