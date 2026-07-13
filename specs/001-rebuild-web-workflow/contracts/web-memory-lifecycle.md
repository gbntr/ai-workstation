# Contract: Web Memory Lifecycle

`conversation → candidate → review → consolidate or hold → changelog → archive`

- A candidate is not canonical memory.
- Curation may apply trivial, non-conflicting updates only.
- Conflicting preferences, goals, and decisions require user approval.
- Every processed candidate reaches Archive; no source candidate is silently deleted.
- When app write is unavailable, a user saves the candidate to the local clone and waits
  for synchronization before treating it as available to ChatGPT discovery.
