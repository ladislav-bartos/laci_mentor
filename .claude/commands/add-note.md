---
description: Quick-capture dictated notes/updates into INBOX.md, then commit once done
argument-hint: [optional first note text]
model: claude-haiku-4-5-20251001
---

Quick-capture mode. Purpose: let the user dictate one or more short updates
(facts, ideas, tasks, questions) without going through a full standup/review
session. Do NOT process, route, or debate these items — that happens later
at standup per `CLAUDE.md`. Just capture them faithfully.

Steps:

1. If `$ARGUMENTS` is non-empty, treat it as the first note. Otherwise ask:
   "Go ahead, dictate your note (or several) — say 'done' when you're finished."
2. Append each note to `INBOX.md` as a new bullet under the existing content,
   preserving whatever's already there. Prefix each entry with today's date
   (use the current date from context). Don't reformat, summarize, or edit
   the user's wording beyond basic cleanup of dictation artifacts (false
   starts, filler words like "uh"/"um").
3. After appending a note, ask if there's another one to add. Keep capturing
   additional notes in the same way.
4. Stop capturing when the user signals they're done (e.g. "done", "that's
   it", "wrap", "commit", or similar).
5. Once stopped, if any notes were added:
   - `git add INBOX.md`
   - `git commit -m "inbox: add note(s) YYYY-MM-DD"` (use today's date, and
     if it's a short session, a one-line hint of the content in the message)
   - Confirm the commit to the user in one line.
6. If no notes were actually added (user immediately said done), don't commit
   anything — just acknowledge.

Keep this whole interaction terse — it's meant to be fast, not a conversation.
