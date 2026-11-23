# Git guide

English is canonical. Arabic: [GIT_GUIDE.ar.md](GIT_GUIDE.ar.md).

## Language

Repository docs use English or Arabic only. English is the source of truth. Arabic mirrors it. Do not add other languages.

## Branches

`main` is the only long-lived branch. Work in a short branch and open a pull request.

```bash
git switch -c fix/winget-cache
git add .
git commit
git push -u origin fix/winget-cache
```

Delete the branch after the squash merge.

## Commits

Use a relaxed Conventional Commit title:

```text
feat(sway): add greetd autologin toggle
fix(iot): handle missing winget cache
docs: standardize repo health files
chore: add gitattributes
ci: add read-only validation
security: enable push protection
```

Rules:

- One commit is one complete idea.
- Subject is short, imperative and has no final period.
- The body explains why the change exists.
- Do not rewrite pushed history. Use `git revert`.
- Rebase only local branches.

## Pull requests

- State what changed and why.
- Keep the diff focused.
- Let all four read-only checks pass: shell, PowerShell, data, docs.
- Use squash merge. Linear history makes reverts simple.

There are no tests. Verification means parsers, syntax checks and the repository's existing read-only `Verify`, `-Verify`, `Validate.ps1` or `install.sh --verify` entry point.

## Local setup

```bash
git config --global user.name "SOSMLG"
git config --global user.email "$(gh api user --jq .id)+SOSMLG@users.noreply.github.com"
git config --global init.defaultBranch main
git config --global pull.rebase true
git config --global core.autocrlf false
git config --global core.quotepath false
git config --global fetch.prune true
git config --global push.autoSetupRemote true
```

Windows PowerShell 5.1 reads BOM-less UTF-8 as ANSI. Keep `.ps1` files ASCII.

## Before pushing

```bash
git diff --check
bash -n path/to/script.sh
./install.sh --verify    # where present
```

On Windows:

```powershell
.\Validate.ps1 -Profile daily
.\install-Win-Iot.ps1 -DryRun
```

Report only what actually ran. If a check cannot run on the host, say so.

## Releases

- `CHANGELOG.md` uses Keep a Changelog with an `Unreleased` section.
- Versions use SemVer.
- `fix` means patch, `feat` means minor, `BREAKING CHANGE` means major.
- Tags are annotated and pushed after the changelog is curated.

## Security

- Secrets stay in the environment or GitHub Secrets.
- Never commit keys, passwords or tokens.
- Report vulnerabilities through the Security tab, not a public issue.
- Microsoft Defender stays as shipped. No script writes its preferences.
