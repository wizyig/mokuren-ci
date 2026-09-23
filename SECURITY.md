# Security Policy

## Scope

This repository provides reusable CI/CD quality controls and supporting GitHub Actions components.

Current security controls include:

- Secret scanning via Gitleaks
- Dependency update monitoring via Dependabot
- Reusable workflow-based quality checks

CodeQL is not enabled.

## Reporting a Vulnerability

Do not open a public issue immediately.

1. Prepare a minimal reproduction or description.
2. Contact the maintainer privately.
3. Allow time for verification and remediation before public disclosure.

## Supported Releases

| Version | Supported |
|----------|----------|
| Latest stable tag | Yes |
| Older releases | Best effort |
| Unreleased experiments | No |

## Security Philosophy

- Detection before enforcement
- Auditable automation
- Explicit versioning
- Minimal trust assumptions

Breaking security changes may require a major version increment.
