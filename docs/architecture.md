# Architecture

## Purpose

Describe the repository's boundaries, primary information flows, and the split between ChatGPT web, the terminal, and private artifacts.

## Boundaries

- `web/` documents the ChatGPT web experience: Memory, Projects, Work, and Drive.
- `cli/` documents terminal use: orchestration, development, QA, and technical memory.
- `agents/` documents shared agent behavior and role definitions.
- `.ai/` is private, local-only, and ignored by Git.

## Principles

- Keep the repo human-friendly and easy to browse.
- Minimize leftover structure; add only what has a clear purpose.
- Keep English as the default for tracked documentation.
- Do not store secrets, credentials, or personal data here.
