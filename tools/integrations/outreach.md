# Outreach

Outreach is a sales-engagement platform for prospects, sequences, mailings,
accounts, and tasks.

## Hosted Agent execution status

`execution_unavailable`: the current Hosted Agent contract has no reviewed
Outreach service/action. Never invoke the bundled legacy CLI, direct provider
API, SDK, remote MCP bridge, or user-held OAuth token from sandboxed shell.

Prepare an import/export plan or ask the user for a safe export. A future
adapter must add a Gateway-owned connection, fail-closed route allowlist,
read/change classification, exact approval for sequence enrollment or sends,
idempotency, and impact/usage accounting before this document can advertise
execution.

## Data model reference

- Prospects: name, email, title, company, tags, and last engagement.
- Sequences: name, enabled state, steps, opens, clicks, and replies.
- Mailings: delivery state and engagement timestamps.
- Accounts: company-level records related to prospects.
- Tasks: due work and completion state.

Do not infer that an account is connected from an API-key-shaped environment
variable. Only the generated execution contract and Gateway readiness may
advertise an executable Outreach capability.
