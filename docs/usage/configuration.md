# Shared Git hooks

The [example configuration](../../examples/lefthook.yaml) imports the supported
`hooks/pre-commit/lefthook.yml` configuration. Run `lefthook install` after adding
or updating the remote, and `lefthook run pre-commit` to run it manually.

Use Lefthook's remote `ref` setting to pin an existing release tag or reviewed
commit when reproducibility is required. Omitting it follows the default branch.

The hook runs `git diff --cached --check`. It checks the index, so unstaged
changes do not alter the result. Conflicts and whitespace errors make the hook
fail; no files are changed automatically.
