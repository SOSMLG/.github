# Security policy

## Supported versions

Only the current `main` branch is supported. Security fixes land there first.

## Reporting

Use the repository's **Security** tab and choose **Report a vulnerability**. Do not open a public issue for exploit details or secrets.

## Scope

These repositories contain desktop setup scripts. They install packages and write user configuration. Run the read-only verifier before trusting a change.

## Secrets

Secrets belong in the environment or GitHub Secrets. Never commit keys, passwords or tokens, and never read a secret value from a tracked file.
