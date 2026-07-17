---
description: Research additional contract/fractional-executive recruitment agencies and platforms, and log the results in RECRUITERS.md
argument-hint: [optional: a specific angle or region to focus this run on]
---

On-demand recruiter/agency research. Purpose: find new candidate
agencies/platforms worth registering with as a candidate (see
`RECRUITERS.md` for the ICP/garden-leave context this assumes), without
repeating the same search every time.

Steps:

1. Read `RECRUITERS.md` in full — the tables, the Outcomes Log, and the
   Research Log.
2. Pick this run's angle:
   - If `$ARGUMENTS` is non-empty, use that as the angle.
   - Otherwise, take the "Next idea to try" from the most recent Research
     Log row, but rotate the *type* of approach across runs rather than
     repeating the same one: (1) direct agency/platform sites in a region
     not yet covered, (2) industry-association member directories (e.g.
     interim-management associations, national HR/staffing bodies), (3)
     LinkedIn searches for people holding the target job title at
     agencies (e.g. "interim practice lead" + region), (4) "similar to
     X" searches once a known-good agency exists in the Outcomes Log —
     use that agency's name as the seed, (5) recruiting-industry
     conference/expo exhibitor lists, (6) review/ranking sites for
     staffing agencies in a given region.
   - Factor in the Outcomes Log: if an agency type turned out to be a
     good fit, look for more like it; if a type consistently isn't
     actionable (no real interim/fractional practice, or no candidate
     pipeline), deprioritize that type in this run.
3. Do the actual web research for this run's angle. Be concrete — named
   agencies/platforms with a real registration or contact URL, and enough
   evidence to judge whether they actually do interim/fractional senior
   Product-leadership placement (not just generic permanent recruitment).
4. Update `RECRUITERS.md`:
   - Add new rows to the relevant regional table (or a new region
     section if needed) for anything genuinely new — check existing rows
     first, don't duplicate.
   - If something looked promising by name but turned out not to be
     actionable or not product-relevant, add it to "Checked and
     excluded" with a one-line reason, so future runs don't re-find it.
   - Append one new row to the Research Log: today's date, the approach
     taken, what worked, what didn't, and a concrete next angle to try
     (rotate to a different angle type than this run used).
5. Show a short summary of what was added (just the new rows).
6. Commit: `git add RECRUITERS.md && git commit -m "recruiters: research pass YYYY-MM-DD — <one-line summary of angle>"`.

This command runs standalone — it does not require a "wrap" step. Keep
new entries concise and factual, matching the existing file's tone.
