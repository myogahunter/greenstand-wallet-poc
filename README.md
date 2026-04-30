# greenstand-wallet-poc

Replica of Greenstand/treetracker-wallet-app's CI workflow.

Demonstrates fork checkout + yarn workspace test injection:
- `pull_request_target` triggers on any fork PR (no gate)
- Checks out the fork's code
- Runs `yarn install --immutable` then `yarn workspace @treetracker/wallet test`
- Keycloak secrets (CLIENT_SECRET, CLIENT_ID, BASE_URL, REALM) set as job-level env vars
- Attacker controls the `test` script in `packages/wallet/package.json`

Used for authorized security research only.
