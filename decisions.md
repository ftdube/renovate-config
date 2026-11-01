# Decisions

## Update cadence — fortnightly batches
Patch and minor updates: one grouped pull request per manager every 14 days (the 1st and 15th). Majors: their own group, same cadence. Security fixes: opened immediately, off schedule. A non-security release is proposed only after it has been out for 3 days, to skip releases that are pulled or quickly patched; security fixes skip the wait.

Why 14 days: a monthly batch can leave a patch unproposed for a full month when a release lands just after a run. Fortnightly, after the 3-day wait, still leaves at least 13 days to review. Every update pull request costs a human approval (one required, no bypass): one grouped pull request per manager per batch is a review, one per dependency a rubber stamp. Majors get their own group, because a single group holding everything lets one breaking major block every safe update behind it.

Revisit if approvals start feeling like a rubber stamp, or if update windows are missed for lack of review time.

## Never automerge
The required approval is the review. Automerge would turn it into a formality on exactly the pull requests nobody reads.

## Digests pinned
A tag can be repointed; a digest cannot. Renovate keeps the digest current, so pinning costs no freshness.

## One updater per ecosystem
A repository using this preset has no `.github/dependabot.yml`: two updaters open duplicate pull requests for the same bump.
