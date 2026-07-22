# MODELS.md — Model Selection Guide

Cost-conscious mapping of Claude models to task types in this repo.
Updated when a new command is added or an assignment is revisited.

## Tiers

- **Haiku 4.5** (cheapest) — mechanical, rule-based, high-volume tasks with
  a fixed rubric, where output is always spot-checked by the user before
  being trusted. Throughput/cost matters more than judgment ceiling.
- **Sonnet 5** (default, balanced) — anything involving nuanced judgment,
  tone, personalization, or synthesis where quality directly affects a
  real outcome (a message sent externally, a decision made). This is the
  repo's default — most work here should stay on it.
- **Opus** (most expensive) — reserved for rare, high-stakes, ambiguous
  reasoning. Not used routinely in this repo: big-picture strategy already
  happens in the claude.ai Project. Invoke manually via `/model` only if a
  specific task turns out to need more than Sonnet delivers.

## Current assignments

| Command / session type | Model | Why |
|---|---|---|
| `standup`, `adhoc`, `weekly-review` | Sonnet 5 (session default, no override) | Core mentorship value is nuanced judgment, pushback, memory-linking; daily/weekly frequency makes Opus costly for marginal gain |
| `draft-outreach` | Sonnet 5 (default) | Represents the user externally — tone/personalization quality matters, low volume |
| `research-contracting`, `research-events`, `research-recruiters`, `research-sources`, `research-content-watch` | Sonnet 5 (default) | Web research + synthesis/relevance judgment; infrequent, on-demand |
| `classify-contact` | **Haiku 4.5** (pinned) | Mechanical classification against a fixed rubric; ~8,000-contact volume makes token cost add up fast; output is always spot-checked, so Haiku's lower ceiling is an acceptable tradeoff |
| `add-note` | **Haiku 4.5** (pinned) | Pure quick-capture/transcription into `INBOX.md`, no judgment required |

## Revisit triggers

- If `classify-contact` spot-checks show a meaningful error rate, move it
  back to Sonnet.
- If a routine task in this repo repeatedly needs deeper reasoning than
  Sonnet gives, do a one-off Opus run via `/model` rather than adding a
  permanent pin.
