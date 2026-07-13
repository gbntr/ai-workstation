# Implementation Plan: Rebuild Public Workstation and Web Workflow

**Branch**: `001-rebuild-web-workflow` | **Date**: 2026-07-13 | **Spec**: [spec.md](spec.md)

## Summary

Rebuild `ai-workstation` as a public, reusable documentation playbook and configure a
human-operated ChatGPT Web workflow. The designated local synchronized Drive clone is
the authoritative editing surface; the ChatGPT Google Drive app with sync is used for
discovery when available. Direct app writes remain optional, confirmed actions; manual
save to the local clone is the universal fallback.

## Technical Context

**Language/Version**: Markdown and repository metadata; no application runtime.

**Primary Dependencies**: GitHub Spec Kit 0.11.3, ChatGPT Projects, Google Drive app
with sync where eligible, and the pre-existing local Drive synchronization.

**Storage**: Markdown files in the Drive `AI Web` hierarchy; public Markdown in Git.

**Testing**: Document navigation, public-content safety review, temporary Drive-fixture
walkthrough, ChatGPT Project instruction walkthrough, and `verify-doc-coverage .`.

**Target Platform**: Git-hosted documentation, local Drive clone, and ChatGPT Web.

**Project Type**: Documentation and operating-procedure rebuild.

**Performance Goals**: A first-time reader finds the setup order within five minutes;
an inbox candidate is triaged in one curation pass without loss of traceability.

**Constraints**: No product code, secret storage, external mutation, MCP, deployment,
or machine paths in tracked public files. App availability and write actions vary by
account and must never remove the manual fallback.

**Scale/Scope**: Four Web Projects, one core memory hierarchy, reusable public role and
workflow guidance, and private planning notes only for environment-specific facts.

## Constitution Check

| Gate | Pre-design | Post-design | Evidence |
| --- | --- | --- | --- |
| Public reusable content | Pass | Pass | Public paths contain rules/templates only; private facts are isolated. |
| Web/CLI separation | Pass | Pass | Web flow excludes technical memory; CLI content remains a boundary reference. |
| Deliberate canonical memory | Pass | Pass | Drive hierarchy, candidate, curation, archive, and conflict flow are modeled. |
| Least privilege and confirmation | Pass | Pass | App write is confirmed; manual-save fallback is mandatory. |
| Spec-first and no implementation | Pass | Pass | This plan and tasks are documentation-only handoff artifacts. |

## Project Structure

### Documentation (this feature)

```text
specs/001-rebuild-web-workflow/
├── spec.md
├── clarify.md
├── plan.md
├── research.md
├── data-model.md
├── contracts/
│   ├── chatgpt-project-instructions.md
│   └── web-memory-lifecycle.md
├── quickstart.md
└── tasks.md
```

### Tracked public documentation to rebuild

```text
README.md
AGENTS.md
docs/
├── index.md
├── architecture.md
├── operations.md
├── web-workflow.md
├── cli-workflow.md
├── memory-system.md
├── permissions.md
└── security.md
agents/
├── README.md
├── jessica.md
├── harvey.md
├── mike.md
├── dona.md
└── rachel.md
web/
├── README.md
├── project-instructions.md
├── session-closure.md
└── curation.md
templates/
├── session-memory-candidate.md
├── memory-policy.md
└── project-memory-files.md
```

**Structure Decision**: Keep the existing top-level public layout and add only the
documentation paths needed to make the workflow independently reproducible. Do not add
code, private configuration, or a copy of `ai-memory`.

## Implementation Phases

1. Establish the public navigation, architecture, scope, and safety boundaries.
2. Define reusable agent roles, CLI workflow boundaries, and implementation handoff.
3. Define the Web memory model, four Project instructions, session closure, curation,
   templates, and manual Drive workflow.
4. Configure the external ChatGPT Project and Drive app manually with confirmation;
   create a temporary non-sensitive Drive fixture to validate the documented flow.
5. Validate public safety, navigation, content coverage, acceptance scenarios, and the
   manual fallback; record the future curation-cadence decision without scheduling it.

## Complexity Tracking

No constitutional violation requires justification. The four ChatGPT Projects are
intentional user scopes, not application components.
