# Rebuild

**Rehearsal status:** not rehearsed from this page.

## Inputs

| Input | Needed for | Where it lives |
|---|---|---|
| Owner access to the GitHub account | Creating the repository, its ruleset | The owner's GitHub account |
| The Mend Renovate GitHub App | Running Renovate on extending repositories | GitHub Marketplace, installed on the account |

## Steps

1. Create the repository public under the owner's account, initialised with the MIT licence so `main` exists. Everything else arrives by pull request.
2. Apply the ruleset once, then compare it with what GitHub reports. Never reapply it to a repository that already has it:

   ```bash
   gh api repos/{owner}/{repo}/rulesets --method POST --input .github/ruleset.main.json
   ```

3. Install the Mend Renovate app on this repository only after `renovate.json` is on `main`; otherwise Mend opens an onboarding pull request with its default config.
