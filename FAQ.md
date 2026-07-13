# FAQ.md — How I Run This System (cheat sheet for future me)

*Human-facing. Claude doesn't read this file — instructions for Claude live in `CLAUDE.md`.*

---

## The map: what happens where

| Place | Used for | How often |
|---|---|---|
| **Claude Code** (terminal / Desktop app, at my desk) | Daily standup, Friday review, ad-hoc work sessions, the `wrap` pipeline (files + git commit) | Daily, weekdays |
| **claude.ai Project** ("mentor" Project, browser/mobile) | Big-picture strategy sessions | Occasionally |
| **GitHub mobile app** (phone) | Voice-dictating notes into `INBOX.md` during the day | Anytime |
| **Claude mobile app** | Urgent "I'm stuck" questions when away from desk | Rarely |

---

## Daily standup (weekday mornings, ~10 min)

1. Open a terminal (or the Claude Desktop app → Code tab).
2. `cd` into this repo's folder.
3. Run `claude`.
4. Type: `standup`
5. Talk it through — Claude asks one question at a time. Be honest; "nothing got done" is data.
6. When finished, say: **`wrap`**
7. Claude files everything (FACTS / SPRINT / LOG / LEARNINGS / archive) and commits to git. Done.

**Why Claude Code and not the browser?** It reads `CLAUDE.md` automatically, edits the files itself, and runs the git commit — the browser can't touch the repo.

---

## Friday review (~20 min)

Same as standup, but type **`review`** instead. Extra steps Claude will walk through:
- Score the week (tasks, Japanese minutes, outreach, replies, events)
- Keep / change / drop decisions
- Plan next sprint
- **Two-week lookahead:** holidays, family commitments, wife's evening schedule → lock networking events *now*
- Update LEARNINGS, prune old LOG entries

---

## Daily notes → INBOX.md (voice, from phone)

Purpose: capture during the day so tomorrow's standup forgets nothing. Don't organize — just capture. Claude routes each item with me at the next standup, then clears the file.

**How (voice, ~30 seconds):**
1. Open **GitHub mobile app** → this repo → `INBOX.md`
2. Tap the **pencil (edit)** icon
3. Tap into the file below the `---` line, new line
4. Tap the **microphone** on the phone keyboard → **dictate in English** (bonus: free English speaking practice)
5. Tap **Commit changes** (default message is fine)

**Format rules (keep it loose):**
- One item per line, `- ` prefix if easy
- No formatting, no categories — routing happens at standup
- Anything goes: facts ("JLPT registration opens Aug 25"), ideas, tasks, questions for tomorrow
- If it came out of a strategy chat in claude.ai, prefix it: `- from strategy chat: ...`

**Rule of thumb:** if in doubt where something goes → INBOX. It's the one funnel; nothing gets lost from there.

---

## "I'm stuck" — ad-hoc questions during the day

Two kinds of thing come up during the day. Route them differently:

| Situation | What to do |
|---|---|
| **Blocking me right now** ("accountant asked X, how do I answer?") | Start an **adhoc session**: Claude Code → type `adhoc` + the question. Away from desk → Claude mobile app; afterwards drop the outcome into INBOX so the repo learns it. |
| **Can wait until tomorrow** ("found the JLPT date", "idea for a post") | **INBOX** it. Elaborate at standup. |

**The test:** *Do I need the answer to continue today?* Yes → adhoc. No → INBOX.

Adhoc sessions end with `wrap` too, so decisions get filed and committed like everything else.

---

## Strategy sessions (claude.ai Project)

For big-picture stuff: roadmap changes, phase decisions, "is this working?" doubts.

1. Run the conversation in the claude.ai mentor Project.
2. Say `wrap` there too — Claude produces minutes.
3. **Manually** save the minutes as `archive/YYYY-MM-DD-strategy-<topic>.md`.
4. Paste any new facts/tasks into `INBOX.md`, prefixed `from strategy chat:`.
5. Next standup routes them — pre-discussed items get filed, not re-debated.

---

## Quick reference

| I want to… | I do… |
|---|---|
| Morning standup | Claude Code → `standup` → talk → `wrap` |
| Friday planning | Claude Code → `review` → talk → `wrap` |
| Note something on the go | GitHub mobile → edit `INBOX.md` → dictate → commit |
| Unblock myself now | Claude Code / Claude mobile → `adhoc` + question |
| Big strategy thinking | claude.ai Project → minutes to `archive/`, facts to INBOX |
| Remember how any of this works | Read this file 🙂 |
