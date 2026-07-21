---
description: Weekly check for new posts/content from the CONTENT.md watchlist, and log results in CONTENT.md
argument-hint: [optional: a specific person or platform to focus this run on]
---

On-demand content-monitoring check. Purpose: keep `CONTENT.md`'s
watchlist (§3) and ranked post library (§4) current without a full
manual re-research pass each time. Intended to run roughly weekly,
ideally during the Friday `/weekly-review` — this command does not run
on its own; it must be explicitly triggered.

Steps:

1. Read `CONTENT.md` in full — §3 (watchlist), §4 (best posts library),
   §5 (weekly monitoring status/last-checked date), §6 (other
   platforms), the To Do list, and the Research Log.
2. Decide this run's scope:
   - If `$ARGUMENTS` names a specific person or platform, focus there.
   - Otherwise, check every person in §3's watchlist for posts newer
     than §5's last-checked date (or, on the first run, newer than the
     dates already logged in §4).
   - Include a check of §6's Substack sources for new posts from the
     same period, since that's the confirmed secondary channel.
   - Periodically (e.g. every 3rd-4th run) spend part of the pass
     specifically hunting for Japan/APAC-based fractional CPO/VP-Product
     posters — this is a repeated, unresolved gap logged in both
     CONTENT.md and CONTRACTING.md's research logs.
3. For each new post found that's genuinely on-topic (fractional/interim
   product-leadership content, not just tangentially related), fetch it
   to get the real text, reactions, comments, and author positioning —
   don't estimate or guess engagement numbers.
4. Update `CONTENT.md`:
   - Add qualifying new posts to §4's ranked library, keeping it sorted
     by engagement (reactions, then comments) — re-rank existing rows if
     the new entries change the ordering.
   - Add any newly-discovered watchlist-worthy person to §3, with a real
     link (never a guessed URL) and a one-line "why watching."
   - If a genuinely new, well-corroborated best-practice finding turns
     up, fold it into §7 — don't duplicate what's already there.
   - Update §5's "last checked" date to today.
   - Update the To Do list and append one Research Log row (date, scope
     covered, what worked, what didn't, next idea) — same format as the
     existing rows.
5. Show a short summary: how many new posts were found and added, and
   whether anything changed at the top of the §4 ranking.
6. Commit: `git add CONTENT.md && git commit -m "content: weekly watch pass YYYY-MM-DD — <N> new posts found"`.

This command runs standalone — it does not require a "wrap" step. If run
and nothing new is found, still update §5's last-checked date and log a
Research Log row noting the null result — that's useful signal too, not
a failure.
