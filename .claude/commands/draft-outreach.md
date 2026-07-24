---
description: Draft a personalized outreach message for one CRM contact using OUTREACH.md templates and FACTS.md achievements
argument-hint: [contact name + whatever you already know: company, title, Source, Role Type, a recent detail about them]
---

On-demand outreach drafting. Purpose: turn one CRM contact into a
personalized message, using the templates in `OUTREACH.md` and the
achievements in `FACTS.md`, without redoing the template-matching logic
from scratch each time.

Steps:

1. Gather what's needed, using `$ARGUMENTS` for anything already given.
   Ask ONE question at a time for whatever's missing — don't guess. This
   is a required per-contact check, added 2026-07-24 specifically so this
   never turns into a mass-send process — realistic pace is ~2/day (maybe
   5/day once practiced), by design, not a limitation to fix:
   - **Met them before?** (Y/N — if Y, where/when/what was discussed —
     reference this directly in the message)
   - **Received a message from them before** (e.g. their own connection-
     request note)? (Y/N — if Y, what did they actually say, even
     paraphrased — this makes it a reply-in-thread, not a cold open, and
     doesn't need to explicitly call out "you messaged me in [year]" since
     they'll see their own original message in the same thread)
   - **Background/role review**: their current role, company, and — most
     importantly — a genuine similarity to the user's own experience worth
     calling out ("I'm doing X too"), not just a compliment on their
     achievements
   - Name, Company, Title
   - Source: warm (actually met/worked together) vs. networking (met at an
     event) vs. LinkedIn-only (1st-degree connection, never actually met)
   - Role Type: Buyer / Connector / Neither (see `FACTS.md` "Business
     Development System" for the definitions)
   - One specific, real detail about them or their company to personalize
     with (a recent post, a move, something about their company's Japan/
     APAC situation) — a message with no real specific in it isn't ready
     to send
2. Pick the template from `OUTREACH.md`:
   - Warm + Buyer → "Warm Buyer"
   - Warm + Connector → "Warm Connector"
   - Networking/met in person + Buyer → "New/Networking Buyer"
   - Source = LinkedIn-only (never actually met), regardless of Role Type
     → "LinkedIn Connector (never met)" — refined 2026-07-17: a LinkedIn
     1st-degree connection with no real relationship should NOT get a
     warm "reconnect" message just because you're connected — there's no
     shared history to reconnect over
   - Role Type = Neither → stop and flag it to the user; not a good
     outreach target, confirm before drafting anything
3. Draft the message: fill the template with real specifics. Pull only
   the achievement(s) from FACTS.md likely to land with *this* contact's
   context — don't dump the full achievement list into every message.
   Follow OUTREACH.md's core principle: never open with the pitch, end
   with a small low-commitment ask. Check tone against OUTREACH.md's
   Voice Reference sample (added 2026-07-24) — favor its plainer phrasing
   ("really appreciate," "thanks in advance") over more polished/formal
   AI-sounding phrasing ("incredibly grateful," "I am currently seeking").
   Title note: "VP of Product" is the default, but "CPO" alongside it is
   fine when the recipient is at a startup (CPO there is typically
   hands-on/execution, unlike at a big company) — see FACTS.md positioning
   refinement 2026-07-24.
4. Show the draft, ask if they want edits. Iterate until approved.
5. Once approved, ask: was this actually sent (now or already)? If yes,
   append one row to `OUTREACH.md`'s Response Log (Date sent, Contact/
   Company, Role Type, Template used, Response = blank, Notes) and commit:
   `git add OUTREACH.md && git commit -m "outreach: draft for <Name> YYYY-MM-DD"`.
   If it's just a draft not yet sent, don't log or commit anything — only
   log messages that actually went out.

This command runs standalone — no "wrap" step required. If run mid-standup
or mid-review, mention what was drafted in that session's minutes instead.
