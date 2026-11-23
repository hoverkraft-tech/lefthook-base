# <img src=".github/logo.svg" width="56" alt="" /> Lefthook Base

![GitHub Verified Creator](https://img.shields.io/badge/GitHub-Verified%20Creator-4493F8?logo=github)
[![Continuous Integration](https://github.com/hoverkraft-tech/lefthook-base/actions/workflows/main-ci.yml/badge.svg)](https://github.com/hoverkraft-tech/lefthook-base/actions/workflows/main-ci.yml)
[![PRs welcome](https://img.shields.io/badge/PRs-welcome-brightgreen)](https://github.com/hoverkraft-tech/lefthook-base/issues)
[![Release](https://img.shields.io/github/v/release/hoverkraft-tech/lefthook-base)](https://github.com/hoverkraft-tech/lefthook-base/releases)
[![Downloads](https://img.shields.io/github/downloads/hoverkraft-tech/lefthook-base/total)](https://github.com/hoverkraft-tech/lefthook-base/releases)
[![GitHub Stars](https://img.shields.io/github/stars/hoverkraft-tech/lefthook-base?style=social)](https://github.com/hoverkraft-tech/lefthook-base)

Reuse Hoverkraft Git hooks in your projects with Lefthook.

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
Pin the remote with a release tag or reviewed commit for reproducible use:

```yaml
remotes:
  - git_url: https://github.com/hoverkraft-tech/lefthook-base
    ref: v1.0.0
    configs:
      - hooks/pre-commit/lefthook.yml
```

Run `lefthook run pre-commit` to execute the hook locally.

## Development

Install Git, GNU Make, Docker with BuildKit, and Lefthook.
Run `make lint`, `make lint-fix`, or `make lint '[.]github/'` from the repository root.
Open the repository in the dev container for the same tools and commands.

## Contributing

Open an issue or pull request to discuss changes.

## Maintainer

Maintained by [Hoverkraft](https://hoverkraft.cloud).

## License

This repository does not currently provide a top-level license.
