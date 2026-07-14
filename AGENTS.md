# Agent Instructions

Read the approved private feature artifacts before implementation work. The current rebuild artifacts are in `.ai/specs/001-rebuild-web-workflow/`.

Use [agent roles](agents/README.md), [permissions](docs/permissions.md), and [operations](docs/operations.md). Keep private facts in ignored `.ai/`; never add them to tracked public content.

## Codex and Agy Git Rules

These rules apply equally to Codex and Agy:

- Work only on a task branch; never make feature changes directly on `main`.
- Before any Git mutation, report the repository root, remote, base branch, current branch/worktree, feature or issue identifier, and ownership/cleanliness.
- Inspect status, diff, and recent history before changing files. Preserve unrelated work.
- After a branch is merged and the merge is verified, delete both its local and remote branch. Never delete an unmerged branch.
- Record branch, commit, pull request, checks, merge result, and branch-deletion result in the handoff.
- Keep specs, briefs, reports, and other agent-only artifacts under ignored `.ai/`; use `.ai/specs/` for private feature artifacts.
