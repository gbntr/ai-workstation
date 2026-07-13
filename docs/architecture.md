# Architecture

## Purpose and flow

The public playbook documents a human-operated workflow:

`ChatGPT Web session → candidate → human review → consolidated Web record or hold → changelog → archive`

The synchronized local Drive clone is the authoritative editing surface for Web records. ChatGPT's Google Drive app, when available, is a discovery/reference surface; it is never presumed to have write authority.

## File map

- `web/` defines the Web operating procedure.
- `cli/` names the boundary to the independent private technical-memory system.
- `agents/` defines ownership through specification, implementation, validation, and separately authorized release work.
- `templates/` contains reusable, non-personal record shapes.
- `docs/` holds the canonical public explanation.
- `.ai/` is ignored agent-only workspace material.

## Invariants

- Web Projects read Core plus their own area index and current state first.
- A candidate is pending input, not canonical memory.
- Conflicts and source-of-truth disagreements require user resolution.
- Public files contain no local paths, account details, credentials, personal details, client identifiers, or private repository state.
