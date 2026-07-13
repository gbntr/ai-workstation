# Validation Quickstart: Web Workflow

## Prerequisites

1. The designated local Drive clone is mounted and synchronized.
2. A temporary non-sensitive `AI Web` fixture exists in that clone.
3. The correct Google account is connected to ChatGPT's Google Drive app with sync if
   the account is eligible; otherwise use the documented manual-only path.
4. Four ChatGPT Projects exist with their scoped instructions.

## Scenario A: Start a scoped task

1. Open each Project and begin a sample task.
2. Verify the instruction names Core, area index, and current-state reading order.
3. Verify it excludes CLI technical memory.

**Expected**: Each Project stays within its area and names only permitted memory sources.

## Scenario B: Close and curate a session

1. Request session closure for a sample decision and one temporary note.
2. Verify the candidate uses the required template and puts only durable items in the
   proposed destinations.
3. Save the candidate through a confirmed app action or manually to the local clone.
4. Process it using the curation procedure and inspect Changelog and Archive.

**Expected**: The decision is traceable, the temporary note is not consolidated, and the
candidate is archived.

## Scenario C: Drive app unavailable

1. Do not use a Drive app write action.
2. Have ChatGPT produce the candidate content only.
3. Manually save it to the local clone and verify synchronization.

**Expected**: The workflow still completes without a claimed automatic write.
