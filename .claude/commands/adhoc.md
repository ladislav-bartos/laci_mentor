---
description: Ad-hoc session — questions, task help, recommendations, anytime
argument-hint: [optional topic or question]
---

Ad-hoc mode — the "adhoc" session type defined in `CLAUDE.md`. No fixed
agenda; this is for whatever I bring right now.

Steps:

1. Read `FACTS.md`, `SPRINT.md`, `LOG.md`, and `INBOX.md` per CLAUDE.md's
   context rules. Don't read `LEARNINGS.md` or `archive/` unless it's relevant
   to what I'm asking — if I ask about past discussions, grep `archive/`
   rather than reading whole files.
2. If `$ARGUMENTS` is non-empty, treat it as the topic/question to start with.
   Otherwise ask what's on my mind.
3. Help with whatever comes up — questions, task help, recommendations. Give
   reasoning with every recommendation, confirm assumptions explicitly rather
   than guessing, and ask ONE clarifying question at a time.
4. Don't file anything until I say **"wrap"** — then run the wrap pipeline
   defined in `CLAUDE.md`.
