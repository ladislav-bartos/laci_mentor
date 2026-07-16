---
description: Research additional free/low-cost channels for finding new ICP-matching contacts in Japan/APAC, and log the results in SOURCES.md
argument-hint: [optional: a specific angle to focus this run on]
---

On-demand contact-sourcing research. Purpose: find new candidate channels
(beyond LinkedIn Sales Navigator, which is deferred — see `LEARNINGS.md`
2026-07-16) for reaching people matching the Ideal Contact Profile in
`FACTS.md` (growth-stage-to-enterprise companies expanding/scaling in
Japan/APAC).

Steps:

1. Read `SOURCES.md` in full — both the Sources table and the Research Log.
2. Pick this run's angle:
   - If `$ARGUMENTS` is non-empty, use that as the angle.
   - Otherwise, take the "Next idea to try" from the most recent Research
     Log row as the starting point, but don't just repeat it verbatim
     forever — vary the *type* of channel across runs (e.g. rotate through:
     individual VC/PE firm portfolio pages, Slack/Discord community
     directories, industry associations, accelerator/incubator alumni
     pages, other national chambers of commerce, conference/event speaker
     lists, coworking-space community boards, LinkedIn Groups, newsletter
     sponsor/advertiser lists). Don't repeat an angle already logged as
     tried unless the log shows it was promising and worth going deeper on.
   - Also factor in any "My notes" / "Verified" feedback already filled in
     on existing rows — if a source type was marked not useful, don't
     source more of the same type; if marked useful, look for more like it.
3. Do the actual web research for this run's angle. Be concrete — the goal
   is named organizations/sites with a URL and a real mechanism for finding
   people (a directory, a member list, a portfolio page), not generic
   "networking is important" filler.
4. Update `SOURCES.md`:
   - Append new rows to the Sources table for anything genuinely new (check
     existing rows first — don't duplicate a source already listed).
     Each new row needs: Source, Why chosen, How to use it, and leave "My
     notes" / "Verified" blank for the user to fill in later.
   - Append one new row to the Research Log: today's date, the approach
     taken, what worked, what didn't, and a concrete next idea for the
     following run.
5. Show a short summary of what was added (just the new rows, not the
   whole file).
6. Commit: `git add SOURCES.md && git commit -m "sources: research pass YYYY-MM-DD — <one-line summary of angle>"`.

This command runs standalone — it does not require a "wrap" step. Keep the
tone of new entries consistent with the existing file (concise, factual,
reasoning included for "why chosen").
