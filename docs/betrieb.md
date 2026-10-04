# Operations

Where and how sanitaer-heizungstechnik-ahrens.de runs (D-031). Update this file
with every change to operations, in the same PR.

| Item | Status |
|---|---|
| **Runs on** | GitHub Pages: <https://tilloh-dev.github.io/sanitaer-heizungstechnik-ahrens.de/> (prototype). The live domain `sanitaer-heizungstechnik-ahrens.de` still serves the old site; a move is not planned yet. |
| **Deploy** | GitHub Pages builds from branch `main` (legacy build, no own workflow). `main` only changes via PR with required check `gate`. |
| **Monitoring** | **open:** no uptime check yet; set one up once the live domain moves |
| **Backup** | no user data; the Git repo is the backup |
| **Secrets in CI** | none. Environment `github-pages` → restricted to selected branches |
| **Secrets at runtime** | none (static site) |

## Minimum rules for tier 1

- Deploy only via CI from `main`, never by hand.
- Secrets never in the repo; CI secrets only in environments.
- Backup for anything holding user data (where present).
- Uptime is monitored.

## Deploy steps

1. PR is merged into `main` after `gate` is green.
2. GitHub Pages publishes the repo root of `main` within a few minutes.
