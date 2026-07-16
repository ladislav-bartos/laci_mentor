# Adhoc — 2026-07-16 (Thu): CRM, Ideal Contact Profile, Sourcing & Outreach

Continuation of the same day's standup (see `2026-07-16-standup.md`),
covering the day's main task: setting up the merged CRM.

## CRM design
- Tool: Google Sheets (user's own account)
- Columns agreed: Name, Source (warm/networking), Company, Title,
  Connection Strength, Target Fit (Y/N vs. Ideal Contact Profile), Role
  Type (Buyer/Connector/Neither — added later in session), Status,
  Last Contact Date, Notes
- Decision: Target Fit applies to ALL contacts, including the existing
  ~8,000 LinkedIn connections, not just new networking contacts. Reasoning
  (user's): a warm contact who's also a strong ICP fit is the highest-
  priority outreach — has both the relationship and the target profile.
- Decision: LinkedIn Sales Navigator deliberately deferred. Reasoning
  (user's): its value is precision/volume filtering, but if the warm-
  outreach message isn't converting yet, more volume just scales a broken
  funnel. Revisit once messaging is proven.

## Filtering the existing 8,000 contacts
- Practical path: LinkedIn "Get a copy of your data" → Connections export
  (CSV: name, company, position, connected-on date) — requested during
  session, expected to take a few hours to arrive
- Once available: Claude Code can run a script to score/tag the full CSV
  against the ICP + known past employers (DAZN, Rakuten, Indeed, Amazon,
  Okomp, Gumtree) — added to SPRINT.md as a follow-up task, not done today
  since the export hadn't landed yet

## Ideal Contact Profile (ICP)
Company profile: Series B+ growth-stage through enterprise; either
expanding into Japan/APAC or already Japan-based and scaling. Excludes
HR-tech/job-board/recruitment-platform companies as clients (hard
constraint, unrelated to whether an HR/Talent *person* can be a contact).

Signals: recent funding round or Japan/APAC market-entry announcement;
visible hiring/product-team growth; PE/VC-backed.

Target titles: CEO/COO/CPO (decision-makers), Head/VP of Product or
Country Manager Japan (champions/peers), CHRO/Head of Talent
(facilitators).

## Buyer vs. Connector (Role Type)
Discussed as two separate things easy to conflate:
- **Buyer**: could personally decide to hire — matched by title + company
  signal, plus a "gap" signal (no one above Head of Product in the org, or
  a long-unfilled VP Product req)
- **Connector**: not a buyer, but knows buyers — ex-colleagues (even in
  non-product roles), recruiters, VC/accelerator staff, other fractional
  execs, board members/advisors
- Reasoning: sending a direct pitch to a Connector, or a "just catching up"
  message to a Buyer, wastes the contact — each gets a different message.

## Sourcing new contacts — SOURCES.md + /research-sources
Researched free/low-cost channels beyond Sales Navigator: chambers of
commerce (BCCJ, ACCJ, EBC), ProductTank Tokyo, VC portfolio pages (Global
Brain, GLOBIS, Coral Capital, DNX, JAFCO, East Ventures, Incubate Fund,
WiL, Z Venture Capital, SBI Investment), PE portfolios (Unison Capital,
Advantage Partners), and the Growth List Japan-startups aggregator.
Findings and a research-approach log saved to `SOURCES.md`.

Created `/research-sources` — a new command (`.claude/commands/
research-sources.md`) that, on demand, researches further sourcing
channels using a different angle each run (rotating through VC/PE firm
sites, Slack/Discord communities, industry associations, accelerator
alumni, other chambers, etc.), logs what worked/didn't, and commits its
own updates to `SOURCES.md` — doesn't require a "wrap" step, mirrors the
existing `/add-note` command's self-contained commit behavior.

Committed and pushed during session (commit `bedcf55`).

## Outreach messaging — OUTREACH.md
Principle: never open with the pitch. Weaker ties need more specific
shared context; warmer ties should read as reconnecting, not selling.
Every message ends with a small, low-commitment ask (a call, an intro),
never "hire me" directly — a direct pitch to a long-dormant contact reads
as transactional and burns relationship equity.

Three templates drafted and saved to `OUTREACH.md`, matched to Role Type +
Source:
1. Warm Buyer — ex-colleague, now senior at an ICP-fit company
2. Warm Connector — ex-colleague, not a buyer, but well-connected
3. New/Networking Buyer — met via a chamber/meetup, no prior relationship

Recommendation: start the first 5 outreach messages (existing SPRINT/
Upcoming task) entirely with Warm Buyers — highest conversion, lowest
risk, validates the message before spending it on colder contacts.

`OUTREACH.md` includes a Response Log (date sent, contact, Role Type,
template used, response Y/N, notes) to refine templates against real
reply data over time.

## Status at end of day
Done: CRM sheet + structure (incl. Role Type), LinkedIn export requested,
ICP defined, SOURCES.md + /research-sources built and pushed, OUTREACH.md
built. Not done: adding the first 10 warm-contact names, the bulk AI pass
on the 8,000-contact export (blocked on export landing), conversation
topic list, and today's N2 study — confirmed with user (not assumed),
carried to tomorrow.
