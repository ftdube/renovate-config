# renovate-config

A shared [Renovate](https://docs.renovatebot.com/) preset. A repository uses it with:

```json
{
  "$schema": "https://docs.renovatebot.com/renovate-schema.json",
  "extends": ["github>ftdube/renovate-config"]
}
```

`default.json` is the policy:

- Updates run on the 1st and 15th of the month, for releases at least 3 days old.
- Vulnerability and OSV alerts run at any time, with no minimum age or PR limit, and carry the `security` label.
- Each manager it lists gets one minor/patch group and a separate `-major` group; add a manager here before a repository relies on it.
- Docker images are pinned by digest and GitHub Actions by commit SHA.
- At most 4 open PRs. Nothing automerges.
- A `# renovate: datasource=… depName=…` comment above a YAML value makes that value tracked (custom regex manager).

Why each choice: [`decisions.md`](decisions.md).
