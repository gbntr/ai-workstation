# Tasks: Rebuild Public Workstation and Web Workflow

**Input**: [spec.md](spec.md), [plan.md](plan.md), [research.md](research.md),
[data-model.md](data-model.md), [contracts](contracts/), and [quickstart.md](quickstart.md)

**Tests**: Documentation walkthrough and safety checks are required; no software test
suite is created because this feature contains no product code.

## Phase 1: Setup (Shared Infrastructure)

**Purpose**: Establish safe scope and a reviewable baseline before any tracked-document
rebuild. These tasks do not authorize commits or external Drive mutations.

- [ ] T001 Record the pre-rebuild file map, known limitations, and exact private Drive
  verification result in `.ai/reports/web-workflow-baseline.md`.
- [ ] T002 Confirm `.gitignore` excludes `.ai/` and inspect every planned tracked public
  path for personal data or machine-specific content in `.gitignore` and `README.md`.
- [ ] T003 [P] Normalize the public entry point and navigation in `README.md` and
  `docs/index.md` without embedding private environment facts.
- [ ] T004 [P] Rebuild public boundary and maintenance guidance in `docs/architecture.md`,
  `docs/operations.md`, `docs/permissions.md`, and `docs/security.md`.

**Checkpoint**: Public safety and navigation foundation is ready.

## Phase 2: Foundational (Blocking Prerequisites)

**Purpose**: Create the reusable public vocabulary that all Web and CLI guidance relies on.

- [ ] T005 Define the public workflow split and cross-repository routing in
  `docs/web-workflow.md` and `docs/cli-workflow.md`.
- [ ] T006 Create the shared role contract and handoff boundaries in `agents/README.md`,
  `agents/jessica.md`, `agents/harvey.md`, `agents/mike.md`, `agents/dona.md`, and
  `agents/rachel.md`.
- [ ] T007 Create reusable, non-personal memory templates in
  `templates/session-memory-candidate.md`, `templates/memory-policy.md`, and
  `templates/project-memory-files.md`.
- [ ] T008 Update `AGENTS.md` and `docs/index.md` to map the rebuilt public workflow and
  require SpecKit artifacts before implementation work.

**Checkpoint**: All public vocabulary, navigation, and role boundaries are consistent.

## Phase 3: User Story 1 - Recreate the public playbook (Priority: P1) 🎯 MVP

**Goal**: A clean checkout explains and navigates the reusable system without private data.

**Independent Test**: A reviewer follows `README.md` and `docs/index.md`, reaches every
tracked public artifact, and completes a public-content safety scan.

- [ ] T009 [US1] Rebuild the public overview and setup order in `README.md` with links to
  `docs/index.md`, `web/README.md`, `cli/README.md`, and `agents/README.md`.
- [ ] T010 [P] [US1] Rebuild the Web and CLI entry-point summaries in `web/README.md` and
  `cli/README.md` using only reusable language.
- [ ] T011 [P] [US1] Add a public documentation map and ownership references in
  `docs/index.md` and `docs/architecture.md` for every new tracked document.
- [ ] T012 [US1] Run a content-safety review and record only findings/remediations in
  `.ai/reports/public-content-safety.md`; remove any disallowed content from the planned
  tracked paths before proceeding.
- [ ] T013 [US1] Run `verify-doc-coverage .` and record its result in
  `.ai/reports/web-workflow-validation.md`.

**Checkpoint**: The public playbook is usable and contains no private environment data.

## Phase 4: User Story 2 - Use durable Web memory safely (Priority: P2)

**Goal**: A user can configure four Projects and execute close-and-curate memory flow with
a synchronized local source of truth and a manual fallback.

**Independent Test**: A temporary non-sensitive fixture completes the three quickstart
scenarios without accessing CLI technical memory.

- [ ] T014 [US2] Define the canonical `AI Web` hierarchy, record lifecycle, and archive
  behavior in `docs/memory-system.md` using `templates/project-memory-files.md`.
- [ ] T015 [P] [US2] Write the four scoped Project instruction variants and source-reading
  order in `web/project-instructions.md` from `contracts/chatgpt-project-instructions.md`.
- [ ] T016 [P] [US2] Write the candidate-first closing procedure in `web/session-closure.md`
  and align it with `templates/session-memory-candidate.md`.
- [ ] T017 [US2] Write curation, conflict, changelog, archive, confirmation, and manual
  local-save fallback rules in `web/curation.md` from `contracts/web-memory-lifecycle.md`.
- [ ] T018 [US2] Configure the four Projects and, only after explicit user confirmation,
  connect or verify the Google Drive app; record capability, account-match, and sync state
  in `.ai/reports/chatgpt-drive-verification.md` without credentials.
- [ ] T019 [US2] Create and process a temporary non-sensitive Drive fixture following
  `quickstart.md`; record validation evidence and unresolved sync issues in
  `.ai/reports/web-workflow-validation.md`.

**Checkpoint**: The Web flow works with either an eligible Drive app or manual local save.

## Phase 5: User Story 3 - Maintain the boundaries over time (Priority: P3)

**Goal**: Future maintainers can classify changes and preserve privacy/authority rules.

**Independent Test**: A reviewer classifies a Drive-write request and a CLI-memory request
using the documentation and receives the correct route and approval requirement.

- [ ] T020 [US3] Add a boundary decision table and prohibited-content examples to
  `docs/security.md` and `docs/permissions.md`.
- [ ] T021 [US3] Add change ownership, approval, and non-goals to `docs/operations.md`
  and `agents/harvey.md`, `agents/mike.md`, `agents/dona.md`, and `agents/rachel.md`.
- [ ] T022 [US3] Record the unselected curation cadence as a user decision in
  `.ai/reports/web-workflow-pending-decisions.md`; do not create a scheduled task.

**Checkpoint**: Maintenance and authority boundaries are explicitly testable.

## Phase 6: Polish & Cross-Cutting Concerns

- [ ] T023 [P] Reconcile links, naming, terminology, and duplication across `README.md`,
  `docs/`, `web/`, `cli/`, `agents/`, and `templates/`.
- [ ] T024 [P] Validate every scenario in `specs/001-rebuild-web-workflow/quickstart.md`
  and record pass/fail evidence in `.ai/reports/web-workflow-validation.md`.
- [ ] T025 Run `verify-doc-coverage .`, inspect `git diff --check`, and hand off results
  in `.ai/reports/web-workflow-handoff.md` without committing, pushing, or deploying.
- [ ] T026 Add exact documentation references for `.specify/scripts/bash/check-prerequisites.sh`,
  `.specify/scripts/bash/common.sh`, `.specify/scripts/bash/create-new-feature.sh`,
  `.specify/scripts/bash/setup-plan.sh`, `.specify/scripts/bash/setup-tasks.sh`, and
  `.specify/extensions/agent-context/scripts/bash/update-agent-context.sh` in
  `docs/index.md`, then rerun `verify-doc-coverage .`.

## Dependencies & Execution Order

- T001–T004 precede all content rebuild work.
- T005–T008 establish shared definitions before the user stories.
- US1 (T009–T013) is the MVP and may be validated before any external ChatGPT setup.
- US2 depends on the public templates and Web safety rules from T014–T017; T018 needs
  explicit user confirmation; T019 depends on T018 or the manual fallback.
- US3 can begin after T005–T008 and must complete before final polish.
- T023–T026 depend on every desired story and are the final handoff gate.

## Parallel Opportunities

- T003 and T004 can proceed in parallel after T001–T002.
- T006 and T007 can proceed in parallel after T005.
- T010 and T011 can proceed in parallel after T009.
- T015 and T016 can proceed in parallel after T014.
- T020 and T021 can proceed in parallel after the foundational phase.

## Implementation Strategy

Deliver and validate P1 as a public documentation-only MVP. Add P2 through a
non-sensitive fixture and manual fallback first; treat app-based writing as optional.
Complete P3 and cross-cutting validation before handing the work to Dona. No task
authorizes code implementation, commits, remote changes, deployment, or scheduled jobs.
