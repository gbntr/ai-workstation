# Security and Public Content Safety

Tracked public content must be reusable and sanitized. Never include credentials, tokens, recovery material, personal data, client or internal identifiers, raw conversations, account details, or machine-local paths.

| Request type | Correct route |
| --- | --- |
| Confirmed Web preference or decision | Candidate, review, then Web canonical record. |
| Technical state, development log, or repository decision | Private CLI technical-memory workflow. |
| Credential, token, recovery material, or raw log | Do not persist; remove or handle through the appropriate secure process. |
| Conflicting memory | Hold for user approval; preserve source evidence. |
| New connected-app permission or Drive write | Explicit confirmation plus manual-save fallback. |

Before handoff, scan planned public paths for prohibited content and record findings only in ignored `.ai/reports/`.
