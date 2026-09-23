# mokuren-ci

Reusable CI/CD quality and audit components for Mokuren-related repositories.

## Purpose

This repository provides reusable GitHub Actions workflows and supporting components focused on:

- Quality assurance
- Secret detection
- Dependency maintenance
- Auditability
- Supply-chain hygiene

This repository intentionally contains CI and audit infrastructure only.

## Boundary

```text
wizyig/mokuren
└─ CC BY-NC-SA 4.0
   Product / Deliverables

wizyig/mokuren-ci
└─ Apache-2.0
   CI / Audit / Quality Layer
```

The separation is intentional.

Project deliverables and audit infrastructure are versioned and licensed independently.

## Included

### Reusable Workflow

- reusable-quality.yml
- Profile-based execution model

### Security Controls

- Secret Scan
- Gitleaks Composite Action
- Dependabot Configuration

### Governance

- Apache-2.0 License
- NOTICE
- Versioned Releases

CodeQL is not enabled. Detection currently means Gitleaks + Dependabot.

## Usage

```yaml
jobs:
  quality:
    uses: wizyig/mokuren-ci/.github/workflows/reusable-quality.yml@v1.0.0
    with:
      profile: dice
```

Allowed profiles: `dice`, `baguamap`, `ofanimring`.

Raw shell commands are not accepted as workflow inputs.

Consumers pin immutable release tags. Do not pin `@main`. A floating `@v1` tag is not published.

## Release Policy

This project follows Semantic Versioning.

### Stable Releases

Stable releases are published as immutable annotated tags.

Examples:

- v1.0.0
- v1.1.0
- v1.2.3

### Version Types

| Type | Meaning |
|--------|--------|
| PATCH | Fixes and maintenance |
| MINOR | Backward-compatible additions |
| MAJOR | Potential breaking changes |

### Floating Major Tags

A floating major tag such as `v1` may be introduced after operational validation.

Before then, only immutable release tags are published.

### Compatibility Commitment

Published release tags are never force-moved.

## Security Policy

See `SECURITY.md`.

### Scope

Current controls include Gitleaks, Secret Scan, and Dependabot.

### Reporting

If you discover a potential vulnerability:

1. Report privately.
2. Allow verification.
3. Coordinate disclosure.

Please avoid opening a public issue before validation.

### Supported Versions

| Version | Status |
|----------|----------|
| Latest Stable Release | Supported |
| Older Releases | Best Effort |
| Experimental Branches | Unsupported |

### Security Philosophy

- Detection before enforcement
- Auditable automation
- Explicit versioning
- Minimal trust assumptions

## License

Apache License 2.0

See LICENSE and NOTICE.
