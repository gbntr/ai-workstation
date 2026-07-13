<!--
Sync Impact Report
- Version change: template → 1.0.0.
- Modified principles: all template placeholders replaced with repository-specific rules.
- Added sections: Boundaries and Safety; Delivery Workflow.
- Removed sections: none.
- Templates reviewed: spec-template.md, plan-template.md, tasks-template.md — no changes required.
- Deferred TODOs: none.
-->
# ai-workstation Constitution

## Core Principles

### I. Public, Reusable, Human-Friendly
Tracked content MUST be understandable without private-system access and safe to reuse
publicly. It MUST describe practices, templates, roles, and boundaries; it MUST NOT
contain secrets, personal details, organization-specific identifiers, or local paths.

### II. Web and CLI Separation
The `web/` surface MUST document personal/executive ChatGPT and Drive workflows only.
The `cli/` and `agents/` surfaces MUST document development workflows only. Neither may
become a copy of the other or carry the other's operational state.

### III. Canonical Source and Deliberate Memory
The designated local Google Drive clone is the authoritative local representation of Web
memory; its machine-specific path belongs only in private planning context. ChatGPT
Memory is limited to small stable preferences; Projects provide scoped instructions;
Drive holds durable memory and objects. Durable updates MUST be explicit, structured,
attributable, and archived before deletion.

### IV. Least-Privilege and Confirmation
Workflows MUST minimize connected-app permissions and never record credentials. A Drive
write through ChatGPT requires explicit user confirmation. When a write action is
unavailable, the workflow MUST produce a candidate for manual save to the local clone.

### V. Spec-First, Auditable Change
Material changes MUST follow constitution → specify → clarify → plan → tasks before
implementation. Each change MUST have measurable acceptance criteria, risks,
dependencies, and a validation path. Private artifacts belong only in ignored `.ai/`;
a plan never authorizes implementation or release.

## Boundaries and Safety

- Tracked documentation is English unless a user-facing artifact requires another language.
- `ai-memory` is private technical memory and never a Web-memory source.
- The mounted Drive and its synchronized working directory are external data stores;
  planning may inspect them but MUST NOT mutate them.
- Integrations, MCP servers, deployment, and background automation are out of scope
  unless a separately approved feature explicitly includes them.

## Delivery Workflow

Harvey owns discovery, specification, and planning. Jessica reviews scope. Mike may
implement approved tasks without changing requirements. Dona independently validates
acceptance criteria. Rachel coordinates integration or release only when authorized.
`verify-doc-coverage .` is a delivery gate for tracked documentation changes.

## Governance

This constitution supersedes conflicting local planning conventions. Amendments MUST
state the rationale, semantic version bump, template impact, and migration work. Every
specification, plan, task list, and review MUST check compliance. MAJOR changes redefine
or remove a principle; MINOR changes add or materially expand one; PATCH changes clarify
it. Current artifacts and `AGENTS.md` are operational guides, not replacements for this
constitution.

**Version**: 1.0.0 | **Ratified**: 2026-07-13 | **Last Amended**: 2026-07-13
