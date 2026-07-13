# Web Memory System

The local synchronized Drive clone contains this portable hierarchy:

```text
AI Web/
  Core/
    PROFILE.md
    PREFERENCES.md
    GOALS.md
    DECISIONS.md
    CHANGELOG.md
  Projects/
    faculdade/
    pessoal-e-carreira/
    organizacao-e-decisoes/
    design-e-fotografia/
      INDEX.md
      CURRENT-STATE.md
      Objects/
  Inbox/
  Archive/
  Templates/
```

Core contains confirmed cross-area records. Each area contains only its own current context and referenced objects. Inbox candidates use `YYYY-MM-DD-HHMM-<project>-<topic>.md`; Archive preserves processed source files. Every durable record identifies scope, type, date, source, confidence, and status where relevant. See [the layout template](../templates/project-memory-files.md).
