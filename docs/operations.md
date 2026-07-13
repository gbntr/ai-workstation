# Operations

## Change procedure

1. Harvey prepares approved SpecKit artifacts and records risks.
2. Mike implements only the approved scope and records evidence.
3. Dona independently validates acceptance scenarios and safety.
4. Rachel coordinates integration or release only with separate authorization.

For public documentation changes, update the owning document and [index](index.md), run link and safety checks, `git diff --check`, and `verify-doc-coverage .`.

## Curation procedure

Review Inbox candidates against the memory policy. Consolidate only confirmed, non-conflicting items; add a Changelog entry with date, target, source, and reason; then move the candidate to Archive. Hold conflicts or synchronization disagreements for user approval. Never overwrite either version while a source disagreement is unresolved.

## Non-goals

This playbook does not authorize MCP, unattended automation, direct connected-app writes without confirmation, scheduled curation, private technical-memory copying, deployment, or release activity.
