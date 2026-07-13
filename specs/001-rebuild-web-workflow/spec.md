# Feature Specification: Rebuild Public Workstation and Web Workflow

**Feature Branch**: `001-rebuild-web-workflow`

**Created**: 2026-07-13

**Status**: Draft

**Input**: Rebuild the public workstation repository and define the ChatGPT Web
memory workflow around the synchronized Google Drive clone while preserving a clear
separation from CLI technical memory.

## Clarifications

### Session 2026-07-13

- Q: What is the authoritative editing surface for durable Web memory? → A: The
  designated synchronized local Drive clone; its machine-specific path is private.
- Q: How does ChatGPT Web access the durable memory? → A: Google Drive app with sync
  when available, with manual local-save fallback always supported.
- Q: What happens when ChatGPT cannot write to Drive? → A: It creates a structured
  candidate; the user saves it to the local clone after review.
- Q: Is MCP or unattended automation part of this rebuild? → A: No; both are out of
  scope for this feature.

## User Scenarios & Testing *(mandatory)*

### User Story 1 - Recreate the public playbook (Priority: P1)

As a person setting up the workflow on a new machine, I can follow one short entry
point and recreate the public documentation, agent roles, and Web/CLI boundaries without
access to the private technical-memory repository.

**Why this priority**: This is the smallest independently useful reconstruction outcome.

**Independent Test**: A reviewer can follow the public setup order and identify the
purpose, owner, and boundary of every tracked file without encountering private data.

**Acceptance Scenarios**:

1. **Given** a clean checkout, **When** a reader opens the navigation document, **Then**
   they can reach architecture, Web workflow, CLI workflow, agent roles, templates, and
   safety guidance through documented links.
2. **Given** a candidate tracked artifact, **When** it is reviewed, **Then** it contains
   no personal data, credentials, client context, internal identifiers, or machine paths.

---

### User Story 2 - Use durable Web memory safely (Priority: P2)

As a ChatGPT Web user, I can start a Project with the right scoped instructions, consult
the right Drive files, close a relevant session into an inbox candidate, and have a
curation process consolidate only confirmed durable information.

**Why this priority**: It turns the public playbook into a repeatable daily workflow.

**Independent Test**: A reviewer can execute a sample session using only the documented
Project instructions and a temporary Drive fixture, then trace one candidate through
Inbox, curation, Changelog, and Archive without changing CLI memory.

**Acceptance Scenarios**:

1. **Given** an initialized Project and connected Drive app, **When** a relevant task
   starts, **Then** the instruction directs ChatGPT to the core and area state files
   before any optional material.
2. **Given** a completed relevant session, **When** the user requests session closure,
   **Then** the result distinguishes durable candidates from temporary content and names
   a suggested destination without silently changing consolidated memory.
3. **Given** a reviewed inbox candidate, **When** curation runs, **Then** non-conflicting
   updates are recorded, the candidate is archived, and conflicts are held for approval.

---

### User Story 3 - Maintain the boundaries over time (Priority: P3)

As a maintainer, I can evolve the public workflow and agent guidance without accidentally
turning it into private technical memory or granting unreviewed connected-app write access.

**Why this priority**: The rebuild must remain safe after initial setup.

**Independent Test**: A reviewer can assess a proposed documentation change against the
boundary checklist and identify its required owner, approval, and validation step.

**Acceptance Scenarios**:

1. **Given** a proposed Web change, **When** it involves a Drive write or a new app
   permission, **Then** the plan requires explicit user confirmation and a fallback that
   creates a candidate for manual local saving.
2. **Given** a proposed CLI-memory addition, **When** it is classified, **Then** the
   public workflow directs it to the private repository rather than a Web-memory folder.

### Edge Cases

- The Google Drive app is unavailable, still indexing, disconnected, or lacks a needed
  write action: the workflow remains usable through manual save in the designated local
  clone and must disclose the unsynchronized state.
- A Drive candidate conflicts with a consolidated preference, goal, or decision: it is
  not merged automatically and is reported for approval.
- A user requests a Web operation containing development state or credentials: the
  workflow declines persistence and routes technical information to the private CLI flow.
- The local clone and remote Drive disagree: curation pauses, preserves both versions,
  and asks for a user resolution before overwriting either source.

## Requirements *(mandatory)*

### Functional Requirements

- **FR-001**: The rebuilt public repository MUST present a concise navigation map,
  architecture, operating workflow, role definitions, reusable templates, and examples.
- **FR-002**: Public content MUST document Web, CLI, and agent boundaries without copying
  private technical state or machine-specific details.
- **FR-003**: The Web workflow MUST define Google Drive as the durable structured memory
  store, ChatGPT Memory as limited global preference context, and Projects as scoped
  workspace instructions.
- **FR-004**: The Web workflow MUST designate the configured local synchronized Drive
  clone as the authoritative local editing surface; its actual path MUST be maintained
  only in private planning context.
- **FR-005**: The workflow MUST define the `AI Web` memory hierarchy, required files,
  naming rules, a session-memory-candidate template, a curation policy, and an archive
  rule.
- **FR-006**: The workflow MUST provide instructions for the four scoped ChatGPT Projects:
  Faculdade, Pessoal e carreira, Organização e decisões, and Design e fotografia.
- **FR-007**: The workflow MUST use the Google Drive app with sync for discovery when
  available, clearly distinguish syncing/indexing from source-of-truth writes, and retain
  a manual fallback.
- **FR-008**: Any direct Drive write through ChatGPT MUST require explicit confirmation;
  without an available confirmed write action, ChatGPT MUST only produce content for the
  user to save to the local clone.
- **FR-009**: The public workflow MUST declare the CLI technical-memory repository as an
  independent system and exclude it from Web Project instructions.
- **FR-010**: The implementation handoff MUST assign specification to Harvey,
  implementation to Mike, independent validation to Dona, and release coordination to
  Rachel only when separately authorized.

### Key Entities

- **Web Memory Record**: A small, durable Markdown document with an owner, scope,
  confidence, status, source, and revision history where relevant.
- **Session Memory Candidate**: A pending structured extraction from one relevant Web
  session; it is not consolidated memory.
- **Curated Memory Record**: A reviewed, canonical Core or Project document entry.
- **Web Project**: A ChatGPT Project that supplies an area-specific instruction and
  routes to the relevant memory subset.
- **Curation Run**: A review event that classifies candidates, records changes, archives
  processed input, and surfaces conflicts.

## Success Criteria *(mandatory)*

### Measurable Outcomes

- **SC-001**: A new reader can identify the setup order and the Web/CLI boundary from the
  public entry point in five minutes or less.
- **SC-002**: Each of the four Web Projects has one instruction block that names the
  mandatory-first reading order and a session-close behavior.
- **SC-003**: A sample session candidate can be classified, consolidated or held for
  approval, logged, and archived with no loss of source or date information.
- **SC-004**: A public-content review finds zero credentials, personal details, client
  identifiers, internal project names, or machine-local paths.
- **SC-005**: The documented fallback lets a user complete the close-and-curate flow even
  when the ChatGPT Drive app is unavailable or lacks an enabled write action.

## Assumptions

- The Drive account used by ChatGPT is the same account represented by the configured
  synchronized local clone.
- Google Drive app availability, plan eligibility, and enabled actions are verified at
  implementation time; the fallback is mandatory regardless of availability.
- This feature documents and configures a human-operated workflow; it does not create an
  MCP server, background process, product code, deployment, or automatic data migration.
- Exact local paths, account identifiers, and sync implementation details remain in
  ignored private planning artifacts rather than public tracked documentation.
