# Mokuren CI

Reusable audit and quality-gate platform for research artifacts.

License: Apache-2.0.

## Audit chain

```
Secret
  ↓
Schema
  ↓
Fingerprint
  ↓
Vectors
  ↓
Release
```

Consumers pin major versions only:

```yaml
uses: wizyig/mokuren-ci/.github/workflows/reusable-quality.yml@v1
```

Do not pin `@main`.

## Consumer input

```yaml
jobs:
  quality:
    uses: wizyig/mokuren-ci/.github/workflows/reusable-quality.yml@v1
    with:
      profile: dice
```

Allowed profiles: `dice`, `baguamap`, `ofanimring`.

Raw shell commands are not accepted as workflow inputs.

## Status

OBSERVED bootstrap. Not CR-frozen. Not Ed25519. Not Trust-L4.

CAS / lock-branch / signed floating-tag rollback are not shipped.
Concurrency uses `release-v1` with `cancel-in-progress: false` on release jobs only.

## Related

- Consumer runtime example: `wizyig/mokuren` (separate license)
