# rampart-action — Rampart Policy Lint and Bench for GitHub Actions

## Quick start

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: peg/rampart-action@v1
    with:
      policy: .rampart/policies/standard.yaml
      min-coverage: 70
```

## Inputs

| Input | Description | Required | Default |
| --- | --- | --- | --- |
| `policy` | Path to policy file or directory | No | `.rampart/policies/` |
| `min-coverage` | Fail if coverage drops below this percentage (0 = just report) | No | `0` |
| `severity` | Minimum severity: critical, high, or medium | No | `medium` |
| `version` | Rampart version to install (default: latest) | No | `latest` |
| `strict` | Strict mode — require_approval does not count as covered | No | `false` |

## Examples

### Basic

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: peg/rampart-action@v1
```

### With minimum coverage

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: peg/rampart-action@v1
    with:
      policy: .rampart/policies/standard.yaml
      min-coverage: 70
```

### Strict mode

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: peg/rampart-action@v1
    with:
      strict: true
```

### Pinned version

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: peg/rampart-action@v1
    with:
      version: v1.2.3
```

## Badge

```markdown
[![Rampart Policy](https://img.shields.io/badge/secured_by-rampart-red?logo=shield)](https://rampart.sh)
```

## Links

- https://rampart.sh
- https://github.com/peg/rampart
