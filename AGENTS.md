# Penvire contracts

OpenAPI, AsyncAPI and Avro contracts between the Penvire services and clients, published as versioned Maven and npm packages. Services and clients consume contracts only through published packages.

## Repository map

```text
openapi/<service>/openapi.yaml   one release component per service
asyncapi/<domain>/               AsyncAPI and Avro schemas per event domain (not defined yet)
generator/                       validation, compatibility checks, code generation
```

## Development environment

Enter the environment with `devenv shell`, or run `direnv allow` once. It provides Java 25, Gradle 9, Node 24, pnpm and openapi-changes. Always run tools through it.

Git hooks run automatically: a commit-msg hook rejects messages that are not Conventional Commits (the same rule as CI), and actionlint checks workflow files.

No build yet. Validation and publishing scripts arrive with the first contract.

## Rules

- Never push to `main`. Create a branch (`feat/`, `fix/` or `chore/`), push it and open a pull request. The maintainer merges.
- Pull requests are squash-merged. The PR title becomes the commit on `main`, so it must be a Conventional Commit; mark breaking changes with `!`.
- Commits are GPG-signed; `main` rejects unsigned commits.
- PR body: a one-paragraph summary, then a `## Test plan` section.
- Releases are managed by release-please. Do not bump versions or edit `CHANGELOG.md` by hand.
- Penvire never ships hand-written authentication.

## Agent docs

- [Issue tracker](docs/agents/issue-tracker.md): GitHub Issues for `Penvire/penvire-contracts`
- [Triage labels](docs/agents/triage-labels.md)
- [Domain docs](docs/agents/domain.md): where the glossary and ADRs live

## Related repositories

- `~/Projects/penvire/prod/backend`: [penvire-backend](https://github.com/Penvire/penvire-backend)
- `~/Projects/penvire/prod/clients`: [penvire-clients](https://github.com/Penvire/penvire-clients)
- `~/Projects/penvire/prod/docs`: [penvire-docs](https://github.com/Penvire/penvire-docs), the product documentation
