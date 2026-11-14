# Local linting

Install Git, GNU Make and Docker with BuildKit enabled. The Docker daemon must
be running. The linter runs on Linux amd64, so other architectures need Docker's
amd64 emulation.

From the repository root:

```sh
make help
make lint
make lint-fix
make lint FILTER='[.]github/'
# The shared positional syntax also works:
make lint '[.]github/'
make lint-fix
```

The root Dockerfile pins the same Hoverkraft Super-Linter image as CI. The
Makefile builds its `linter` stage and runs the repository's lint profile.
The `FILTER` regular expression narrows file selection; repository-wide analyzers may still
inspect the complete project. Git worktrees are supported. Builds stop on errors, and each repository uses its
own local image tag. Build arguments use your UID and GID so generated files
retain your ownership.

Commitlint uses the root configuration and checks the latest local commit.
CI checks the relevant PR or push commit range. CodeQL and action-pinning jobs
run separately in GitHub Actions.

Review changes made by `make lint-fix`, then run `make lint` again. Findings
without an automatic fix still require manual changes.

Dependabot tracks the root Dockerfile. Keep its image and validator configuration
aligned with the shared CI workflow when updating either.

## Dev container

Open the repository in Visual Studio Code and select **Dev Containers: Reopen in
Container**. The configuration installs GitHub CLI and Docker for the same
`make lint` and `make lint-fix` commands used locally. Helm repositories also
include Helm and kubectl. Dependabot maintains the devcontainer features.
