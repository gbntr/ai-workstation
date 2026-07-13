# ai-workstation

A public, reusable playbook for a human-operated AI workflow. It separates ChatGPT Web memory from private CLI technical memory.

## Start here

1. Read [the documentation map](docs/index.md).
2. Choose [Web workflow](web/README.md) for ChatGPT Projects and durable Web memory, or [CLI workflow](cli/README.md) for technical work.
3. Read [agent roles](agents/README.md) before a SpecKit implementation handoff.

## Boundaries

- Web memory is structured Markdown in a synchronized Drive folder, curated by a human.
- ChatGPT Memory holds only small global preferences; Projects provide scoped instructions.
- The private technical-memory repository is a separate system. Do not copy its state here.
- This repository contains no machine paths, accounts, credentials, personal data, or client context.

See [architecture](docs/architecture.md), [security](docs/security.md), and [operations](docs/operations.md) for the operating rules.
