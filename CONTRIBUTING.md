# Contributing

Small changes, small pull requests.

## Flow

1. Branch from `main`.
2. Make one complete change.
3. Use a Conventional Commit style title: `feat:`, `fix:`, `docs:`, `chore:`, `ci:`, `security:`.
4. Open a pull request. Describe what changed and why.
5. Let the read-only checks finish, then squash-merge.

## Rules

- No tests. Validation means parsers, syntax checks and existing read-only `Verify` entry points.
- No secrets in the tree. Keep keys in the environment or GitHub Secrets.
- No force pushes to `main`.
- Never rewrite pushed history. Use `git revert`.
- English is canonical. Arabic translations are welcome. Other languages are not used in repo docs.

See the [Git guide](docs/GIT_GUIDE.md) or [دليل Git](docs/GIT_GUIDE.ar.md) for the full local workflow.
