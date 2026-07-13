# Operations

## Development

This repo is documentation-only, so operations are editing, organizing, and verifying docs.

## Routine workflow

1. Add or update the relevant README or doc.
2. Update `docs/index.md` if a tracked file changed.
3. Keep the structure minimal and obvious.
4. Avoid duplicating content across files.
5. Run `verify-doc-coverage .` before handoff.

## Manual setup guidance

When recreating this by hand later, start in this order:

1. `README.md`
2. `docs/index.md`
3. `web/README.md`
4. `cli/README.md`
5. `agents/README.md`

## Guardrails

- No secrets.
- No generated clutter.
- No speculative future tooling unless it has a clear owner.
