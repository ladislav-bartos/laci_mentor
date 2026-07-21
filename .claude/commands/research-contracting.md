---
description: Research one section of the fractional/interim engagement playbook, and log the results in CONTRACTING.md
argument-hint: [optional: a specific section name or number to focus this run on]
---

On-demand fractional/interim contracting research. Purpose: build out
`CONTRACTING.md`'s playbook one lifecycle-stage section at a time (see
that file for the ICP/positioning context this assumes), without
repeating research on sections already covered.

Steps:

1. Read `CONTRACTING.md` in full — the Coverage status table, all
   section content, the Sources Reviewed table, the To Do list, and the
   Research Log.
2. Pick **exactly one** section for this run — never split effort across
   multiple sections in a single pass, even if several are uncovered:
   - If `$ARGUMENTS` names a section, use that.
   - Otherwise, pick by priority: (a) any section still "Not started" or
     "Seeded only" (uncovered beats stale — go breadth-first before
     depth), ordered by the Coverage status table's row order; (b) if all
     sections have at least an initial "Researched" pass, pick whichever
     has the oldest Last-researched date (30+ days old = due for a
     refresh); (c) check the To Do list and Research Log's "Next idea to
     try" for a specific angle already identified for that section.
3. Do the actual web research for that one section only. Be concrete —
   real sourced findings (do/don't, concrete practices, named
   examples), not generic filler. Cross-check the Sources Reviewed table
   first so this pass doesn't re-fetch a source already logged for this
   section (unless it's a stale-refresh pass, in which case re-checking
   a source for updated content is fine).
4. Update `CONTRACTING.md`:
   - Fill in / expand that section's content under its heading.
   - Update its row in the Coverage status table: Status → "Researched"
     (or keep "Researched", bump the date, if this was a refresh), and
     Last researched → today's date.
   - Append new rows to the Sources Reviewed table for every source
     actually used this run.
   - Append one new row to the Research Log: today's date, the section
     covered, what worked, what didn't, and a concrete next idea (for
     this section if left incomplete, or for the next section to pick).
   - Update the To Do list: check off what this run resolved; add
     anything new surfaced (e.g. a section 9 gap-list item worth
     promoting).
5. Show a short summary of what was added.
6. Commit: `git add CONTRACTING.md && git commit -m "contracting: research pass YYYY-MM-DD — <section researched>"`.

This command runs standalone — it does not require a "wrap" step. Keep
new entries concise and factual, matching the existing file's tone. Stay
within one section even if the research surfaces something clearly
relevant to another — note it in that other section's "Open questions"
instead of researching it now.
