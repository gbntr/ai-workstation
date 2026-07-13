# Web Memory Data Model

## Entities

### Web Memory Record

| Field | Rule |
| --- | --- |
| scope | `core` or one approved area slug. |
| type | profile, preference, goal, decision, state, learning, policy, or changelog entry. |
| date | ISO date of confirmation or change. |
| source | Session candidate or approved external source. |
| confidence | confirmed, high, medium, or pending. |
| status | current, superseded, pending review, or archived. |

### Session Memory Candidate

| Field | Rule |
| --- | --- |
| filename | `YYYY-MM-DD-HHMM-<project>-<topic>.md`. |
| project | One of the four approved Project names. |
| status | Starts as `pending`; becomes processed, held, or rejected. |
| durable sections | Decisions, preferences, state changes, learnings, improvements. |
| exclusions | Temporary information and conflict notes are explicit. |
| suggested destinations | Canonical target files, never an implied write. |

### Curation Run

| Field | Rule |
| --- | --- |
| input | One or more Inbox candidates. |
| result | consolidated, held-for-approval, rejected, or archived-without-change. |
| changes | Changelog entries identify target and reason. |
| conflict | Never overwritten automatically. |

## Relationships

One Project reads one area index and state, plus Core records. One session creates zero or
one candidate. One candidate may propose multiple canonical record changes. One curation
run processes many candidates and archives each processed source.
