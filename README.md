# Setup Archgate

Official GitHub Action to install the [Archgate](https://archgate.dev) CLI and add it to `PATH`. Supports all GitHub-hosted runner platforms: Ubuntu, macOS, and Windows.

## Inputs

| Input     | Required | Default  | Description                                    |
|-----------|----------|----------|------------------------------------------------|
| `version` | No       | `latest` | Archgate version to install (e.g. `v0.14.0`). |

## Usage

```yaml
steps:
  - uses: actions/checkout@v4
  - uses: archgate/setup-action@v1
    with:
      version: v0.14.0 # optional, defaults to latest
  - run: archgate check --ci
```

## Cross-platform workflow

```yaml
jobs:
  check:
    strategy:
      matrix:
        os: [ubuntu-latest, macos-latest, windows-latest]
    runs-on: ${{ matrix.os }}
    steps:
      - uses: actions/checkout@v4
      - uses: archgate/setup-action@v1
      - run: archgate check --ci
```

## Community

Questions or feedback? Join [r/archgatedev](https://www.reddit.com/r/archgatedev).

## License

[Apache 2.0](LICENSE)
