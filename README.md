# .github

Default community health files and reusable validation workflows for SOSMLG repositories.

English is canonical. Arabic is provided in `docs/GIT_GUIDE.ar.md`.

Repositories inherit issue and pull request templates from here unless they provide their own copy. Reusable workflows only parse files and check repository hygiene. They do not install software or change system state.

- [Git guide](docs/GIT_GUIDE.md)
- [دليل Git](docs/GIT_GUIDE.ar.md)
- [Visual standard](docs/THEME.md)
- [المعيار البصري](docs/THEME.ar.md)
- [Contributing](CONTRIBUTING.md)
- [Security](SECURITY.md)

## Workflows

- `validate-shell.yml`: `bash -n`, conflict markers, whitespace.
- `validate-powershell.yml`: PowerShell parser, conflict markers, whitespace.
- `validate-json-xml.yml`: JSON, XML and YAML parsing.
- `validate-docs.yml`: local Markdown links, language policy, whitespace.

All workflows use `permissions: contents: read`. Actions are pinned to full commit SHAs. No secrets are used.
