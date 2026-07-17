---
description: Research additional networking/visibility events (in-person Tokyo, online, speaking opportunities, startup-adjacent, or tangential), and log the results in EVENTS.md
argument-hint: [optional: a specific category or angle to focus this run on]
---

On-demand event research. Purpose: find new candidate events/opportunities
worth attending or pursuing (see `EVENTS.md` for the ICP/scheduling
context this assumes), without repeating the same chamber/meetup search
every time.

Steps:

1. Read `EVENTS.md` in full — the Categories section, the candidate
   events table, the To Do list, and the Research Log.
2. Pick this run's category/angle:
   - If `$ARGUMENTS` is non-empty, use that as the category/angle.
   - Otherwise, take the "Next idea to try" from the most recent Research
     Log row. Prefer covering one of the under-researched categories
     (Online/Virtual, Speaking opportunity, Tangential/creative) over
     re-searching Chamber/Business, which is already well covered —
     go deep on one category per run rather than shallow across all.
   - For **Speaking opportunity** specifically: research actual CFPs /
     call-for-speakers pages for product-management, growth, or
     AI-in-business conferences and meetups in Japan/APAC, not just
     "conferences that exist" — the goal is a submittable opportunity,
     with a topic angle grounded in `FACTS.md`'s achievements (DAZN
     0-to-1 Japan launch, Rakuten transformation, AI/GCP background).
   - For **Tangential/creative**: deliberately look outside product-
     management/interim-hiring — adjacent domains (fintech, gaming,
     e-commerce, HR-tech-as-attendee-not-client, business-school alumni
     networks) where senior operators or investors might plausibly show
     up, or where there's something genuinely new to learn.
3. Do the actual web research. Be concrete — named events/organizations
   with a real URL and a way to find upcoming dates, not generic
   "networking is important" filler. Flag anything with a concrete date
   in the next 2-4 weeks against `SPRINT.md`'s scheduling-constraints
   section.
4. Update `EVENTS.md`:
   - Add new rows to the candidate events table, tagged with the correct
     Category. Check existing rows first — don't duplicate.
   - If anything is time-sensitive (a real upcoming date), add it to
     "Near-term opportunities" too.
   - Append one new row to the Research Log: today's date, the
     category/angle covered, what worked, what didn't, and which
     category to cover next (rotate rather than repeat).
   - Update the To Do list if this run resolves or adds an action item.
5. Show a short summary of what was added.
6. Commit: `git add EVENTS.md && git commit -m "events: research pass YYYY-MM-DD — <one-line summary of category/angle>"`.

This command runs standalone — it does not require a "wrap" step. Keep
new entries concise and factual, matching the existing file's tone.
