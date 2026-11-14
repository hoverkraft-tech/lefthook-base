# <img src=".github/logo.svg" width="56" alt="" /> Lefthook Base

Reuse Hoverkraft Git hooks in your projects with Lefthook.

[![Continuous Integration](https://github.com/hoverkraft-tech/lefthook-base/actions/workflows/main-ci.yml/badge.svg)](https://github.com/hoverkraft-tech/lefthook-base/actions/workflows/main-ci.yml)
[![Release](https://img.shields.io/github/v/release/hoverkraft-tech/lefthook-base)](https://github.com/hoverkraft-tech/lefthook-base/releases)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](docs/development/linting.md)

## Prerequisites

Install Git and Lefthook on the development machine.

## Use the shared hook

Add the remote to your project's `lefthook.yml`:

```yaml
remotes:
  - git_url: https://github.com/hoverkraft-tech/lefthook-base
    configs:
      - hooks/pre-commit/lefthook.yml
```

Then install the hooks:

```sh
lefthook install
```

The pre-commit hook checks staged changes for merge-conflict markers and whitespace errors.
See [configuration](docs/usage/configuration.md) for pinning and local execution.

## Contributing

Open an issue or pull request to discuss changes. The [contributor guide](docs/development/linting.md)
describes the dev container and local lint commands.

## Maintainer

Maintained by [Hoverkraft](https://hoverkraft.cloud).

## License

This repository does not currently provide a top-level license.
