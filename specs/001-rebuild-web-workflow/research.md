# Research: Rebuild Public Workstation and Web Workflow

## Decision 1: Use Projects for scoped ChatGPT context

**Decision**: Configure four Projects with scoped instructions and relevant file order.

**Rationale**: Projects group instructions, chats, and files around recurring work; the
instruction scope can keep the Web workflow separate from development.

**Alternatives considered**: A single general Project was rejected because it weakens
area boundaries; custom GPTs were rejected because the requirement is Project-based.

## Decision 2: Use Google Drive app with sync for discovery, not authority

**Decision**: Prefer the Google Drive app with sync for Drive discovery/reference where
available. Treat the designated local synchronized clone as the editing source of truth.

**Rationale**: Sync availability and app actions vary by account. A local edited file
that is synchronized to Drive remains independently verifiable and avoids claiming a
write capability that may not exist.

**Alternatives considered**: App-only writes were rejected because they may be disabled,
unavailable, or require additional authorization. An MCP server was rejected as out of
scope for the initial human-operated workflow.

## Decision 3: Candidate-first memory curation

**Decision**: Close relevant sessions into an Inbox candidate, then review, consolidate,
log, and archive.

**Rationale**: It keeps unconfirmed statements out of durable memory and preserves a
traceable source.

**Alternatives considered**: Immediate silent updates were rejected because they can turn
inferences into facts and lose conflict history.

## Verification Sources

- OpenAI Help Center: Google Drive app with sync setup and indexing behavior.
- OpenAI Help Center: ChatGPT apps with sync and Drive link reference behavior.
- OpenAI Help Center: Projects in ChatGPT and project instruction scope.
