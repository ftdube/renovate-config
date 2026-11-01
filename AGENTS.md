# renovate-config

Public Renovate preset (`default.json`), extended as `github>ftdube/renovate-config` by public and private repositories.

## Hard rules
- Public: no personal identifiers, infrastructure, or references to private repositories.
- A change here reaches every extending repository on its next run: validate before merging (CI's `validate` job runs `renovate-config-validator --strict`).
- Never add a repository-specific rule; it belongs in that repository's `renovate.json`.
- Rebuild: [`REBUILD.md`](REBUILD.md).
