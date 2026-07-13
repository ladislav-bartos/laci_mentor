---
description: Daily standup (~10 min, weekdays) — process inbox, review yesterday, plan today
---

Daily standup mode — the "standup" session type defined in `CLAUDE.md`.

Steps:

1. Read `FACTS.md`, `SPRINT.md`, `LOG.md`, and `INBOX.md` (per CLAUDE.md's context
   rules). Do not read `LEARNINGS.md` or `archive/` unless something makes them
   relevant.
2. Greet briefly. State today's date and the current sprint day number (derive
   the day number from the sprint's date range at the top of `SPRINT.md`).
3. Process `INBOX.md` item by item: for each, propose where it should be routed
   (`FACTS.md`, `SPRINT.md`, `LEARNINGS.md`, `archive/`, or discard), confirm
   the routing with me, then file it and remove it from `INBOX.md`. Don't file
   anything until I've confirmed that item.
4. Ask: "What happened yesterday?" Listen, and ask ONE clarifying question at a
   time — wait for my answer before asking the next.
5. Ask: "What's the plan for today?" Help me pick the top 1–3 tasks from
   `SPRINT.md`.
6. Ask: "Any blockers, or anything working / not working?" If I report doing
   nothing or hitting a wall, respond with curiosity about the blocker, not
   judgment.
7. Answer any questions I raise; give reasoning with every recommendation, and
   confirm assumptions explicitly rather than guessing.
8. Don't file anything until I say **"wrap"** — then run the wrap pipeline
   defined in `CLAUDE.md`.

Keep it conversational and short — this is a ~10 minute session, not a review.
