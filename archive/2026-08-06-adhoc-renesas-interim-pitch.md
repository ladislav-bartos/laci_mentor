# 2026-08-06 (Thu) — Adhoc — Sprint 4, Day 4 (continued after standup)

Standup for today is in `archive/2026-08-06-standup.md`. This covers
everything that followed it in the same session: today's 3 picks, the
JAC reply, and the Mario Kushtgjini / Renesas thread, which turned into
the largest single piece of work this sprint.

## Connector outreach #1 — Keisuke Oishi
User asked for a recommendation from the CRM priority list. Picked
**Keisuke Oishi** (Japan Country Manager, Prime Video, Amazon) over
Joseph Tan (Representative Director, Indeed Technologies Japan) —
reasoning given: Oishi is ex-colleague-tier (same company, Amazon,
during the user's JCI-VSP tenure), senior, Japan-based, and "Country
Manager Japan" is literally on the ICP title list. Tan was parked at the
user's request — still at Indeed while the user is on garden leave from
there, too close for comfort.

User then corrected the framing: he and Oishi were at Amazon at the same
time but never met — that's not "ex-colleague." Agreed, and used it as
the trigger to fix `classify-contact.md`'s wording convention: shared
employment alone is now "same-company connection (no confirmed
interaction)," with "ex-colleague" reserved for verified real
interaction. Role Type (Connector) unchanged, only the label.

Drafted via `/draft-outreach`, Template 4 (LinkedIn Connector, never
met). User asked to keep it short, drop the Amazon tie entirely (very
senior, no real relationship to lean on), and personalize instead with
the user's own AI-and-leadership research (from LinkedIn post #12).
Iterated twice more: added back a "reason for reaching out" line, then
tightened it. Sent. Logged to OUTREACH.md's Response Log, SPRINT.md
checked off, CRM row updated (local, gitignored).

## Sara Al-Attas and Dharmesh Raithatha follow-ups
**Sara** (marketplace lead, sent 07-22, 15 days pending): recommended a
short, low-pressure bump restating the free-trial offer. User asked to
acknowledge she may have already chosen someone/moved on rather than
re-pitching cold, and to drop "or two" from "a free session or two."
Sent, logged, SPRINT.md checked off.

**Dharmesh** (Connector, sent 07-24, 13 days pending): user decided
*not* to send a short bump — "not a project-related contact." Instead,
hold ~30 days (target ~2026-09-05) and reconnect with a different ask:
inviting him to contribute info/perspective for the user's AI-leadership
research, not repeating the original "know anyone in your network" ask.
SPRINT.md task marked done (decision made, even though nothing sent
today) with the 30-day reminder moved to Upcoming/unscheduled.

## JAC Recruitment reply
User pasted a Japanese auto-reply from JAC: no current listing to
introduce, for either a directly-entered job or general registration.
Explicitly a mass-template email ("individual guidance isn't feasible
given volume"), not a personalized rejection — says a consultant will
reach out directly if something matching appears later. Logged to
RECRUITERS.md's Outcomes Log as "N (for now)," no action needed, door
stays open per their own note.

## Mario Kushtgjini / Georgios Pfitzner — call prep, the call, and the Renesas thread

### Prep: slide deck + private markdown doc
User wanted to prep for today's 3-4pm JST call. Built:
- **A private markdown prep doc** (`uploads/private/mario-kushtgjini-call-
  prep_2026-08-06.md`) — positioning talking points, the user's own
  three-company-type-in-Japan framework (cleaned up from dictation and
  cross-checked, with additions flagged `[+]`: real terms like *shūshin
  koyō*, *ringi/nemawashi*, "boundary spanner," Rakuten's Englishnization
  as a concrete example the user actually lived through), scoping
  questions for search professionals (including a precision correction —
  gender/age criteria are illegal to *write down* in Japan, so what the
  user described is a law-vs-practice gap, not a hidden written rule),
  the hidden-talent-pool/passive-market argument, an AI-adoption-by-
  archetype section (Sakana AI as a concrete example, the Renesas
  semiconductor-demand outlier framed as an open question), and a
  dedicated research note confirming Olympic Consulting Partners has
  no findable independent Japan/APAC track record — their own site says
  "Europe-wide operations" only.
- **A 22-slide deck** ("Leadership in Japan — Field Notes," published as
  a Claude Artifact, kept private) covering the shareable subset of the
  above (positioning, the 3-archetype framework, the leadership-pairing
  model, scoping questions, the hidden-talent-pool argument) plus an
  8-slide appendix (AI adoption by archetype, Sakana AI, the hardware/
  semiconductor outlier, the H6 authority-over-compensation research
  stat, and two Renesas-specific slides — company profile, and a "what
  the perfect match looks like" analysis). Deliberately excluded the
  private tactical notes (soft-ask wording, the garden-leave answer, the
  Olympic Consulting Partners research note) — those aren't for a shared
  screen. Also exported as a PDF; found and fixed a real bug where the
  print layout used a mismatched viewport, causing content to bleed
  across page boundaries and the 3-column comparison slide to collapse
  to one column — fixed by pinning the print page to explicit widescreen
  dimensions matching the render viewport, verified by rendering actual
  pages to PNG and inspecting them rather than assuming the fix worked.

### The call
Held as scheduled, with Georgios Pfitzner (co-founder, leads their
Executive Search practice and the Renesas AI searches) joining alongside
Mario. Per the user: went very well. Covered hiring in Japan generally
and specifically whether Indeed is hiring. In the course of learning
about the user's background, they thought he could be a fit for their
live Renesas **AI Enablement Lead** search and asked him to review the
confidential job spec, which they sent afterward
(`uploads/private/Olympic_Consulting_Partners_Confidential_JobSpec_AI
Enablement Lead.pdf`).

### Reviewing the job spec
Read in full. Role: AI Enablement Lead, Renesas Electronics, reporting
to Head of AI & Transformation, Tokyo HQ preferred, banded "senior
consultant to senior manager." Core mandate: drive org-wide AI
enablement/adoption (workflows, training/helpdesks, culture/change
management, security/governance guidelines, KPI/impact tracking,
cross-functional evangelism) — guidance and connection, not building AI
products.

Assessed against FACTS.md:
- **Real matches:** direct AI-enablement experience (flagged initially
  via StageLync, later replaced per the user's request — see below),
  quantified impact-tracking track record (Rakuten +20%/+30%, Indeed 25%
  ML improvement), strong technical credibility (7 Google Cloud certs,
  DeepLearning.AI specializations), Tokyo-based/PR holder.
- **Real gaps:** seniority (VP-level vs. the JD's stated band — flagged
  as the single biggest structural issue at first), Japanese fluency
  ("strongly preferred," not yet fluent — N3, working toward N2),
  background-type (JD favors marketing/consulting/communications
  backgrounds; the user's is product-strategy/P&L leadership).
- **The dominant issue, flagged first:** this reads as a full-time,
  permanent Renesas role — reporting line, standard structure, no
  contract/interim framing anywhere in the spec — which conflicts
  directly with the garden-leave hard constraint (no full-time
  employment before April 2027). Flagged clearly as a decision only the
  user can make, not something to assume away.

### The reframe: interim Head of AI & Transformation
User's own idea, stated explicitly: rather than apply for the
subordinate AI Enablement Lead role, position himself as a possible
**interim Head of AI & Transformation** — come in to help while they run
the search for the right permanent long-term person, then step aside
once found ("if they find the right candidate, they can get rid of me").

This was validated as a strong move because it resolves two structural
gaps at once, not just the employment-type one:
- **Full-time constraint → resolved.** Interim/contract work is exactly
  what garden-leave terms allow.
- **Seniority mismatch → inverted in his favor.** "Head of AI &
  Transformation" is the level above "AI Enablement Lead" (which reports
  to it) — at VP level, the wrong altitude for the posted role, the right
  altitude for leading it.
- **One caveat surfaced:** Olympic Consulting Partners' JD is for a
  retained *permanent* placement; interim/bridge leadership is a
  different service line than what they're formally running. Worth
  raising as "would you even consider or relay this" rather than
  assuming it's a straightforward ask for them.

Logged as a new general pattern in LEARNINGS.md: when a role is a strong
substance match but blocked by both a full-time-employment constraint
and being over-leveled for the posted band, pitching one level up as an
interim engagement can resolve both at once — worth checking for this
shape before assuming a role is simply not a fit.

The user pushed back on 3 of the 4 gaps originally flagged, given this
reframe, and the pushback was accepted as fair:
- **Seniority** — no longer a mismatch once targeting the Head-level
  interim framing instead of the subordinate role.
- **Background** — product leadership genuinely requires deep fluency in
  marketing, cross-functional communication, and working alongside
  consultants/agencies; the substance was already there, the CV just
  wasn't describing it that way (see CV section below).
- **Hands-on/day-to-day** — retracted; the CV already backs this up
  ("hands-on AI builder who ships model-agnostic LLM services").
- **Japanese fluency** — the one gap both agreed was real, no pushback.

### CV review and rebuild (v4 → v5)
Reviewed the existing CV (`CV_v4_fractional-interim-growth-
transformation.docx`) against the JD. Found:
- **Okomp** (CEO & Chief Strategy Officer, UK–China digital agency) was
  already, structurally, exactly the "consulting/marketing" background
  type the JD said it wanted — just described in growth-agency language
  instead of consulting/marketing language. Reframed the existing bullet
  rather than adding new claims.
- **No AI-enablement-specific vocabulary anywhere** ("enablement,"
  "adoption," "playbooks," "governance," "evangelism") despite the
  substance existing (Amazon's 116-workflow RPA/ML program).
- **Google Cloud security certs** (Professional Cloud Security Engineer,
  Professional Security Operations Engineer) sitting unconnected to any
  narrative — nothing tied them to the JD's "Security & Governance"
  responsibility.
- **The StageLync AI-enablement story** — far and away the strongest
  single proof point discussed earlier this sprint (personally drove
  NotebookLM/Gemini adoption team-wide at StageLync) — was flagged as
  the natural fit here, but it's deliberately excluded from the CV as an
  unpaid founder-mentoring relationship (see FACTS.md). Asked the user
  explicitly rather than assuming either way.

**User's decision:** leave StageLync out. Instead, substitute a real,
current, higher-stakes proof point from his actual employer: for the
last ~6 months at Indeed, he has been leading adoption of Claude across
the product development lifecycle — requirements documentation, system
architecture review, test planning/execution, operational monitoring,
and privacy/security/legal review — used by his own delivery team,
leadership (visibility), and partner functions (marketing, sales,
customer support). Gathered via one clarifying-question round (tools,
scope, beneficiaries, duration) before writing anything, to keep the
"honest message" framing genuinely honest rather than vague filler.
Filed to FACTS.md as a new stable fact.

CV updates made (Core Strengths "AI-Driven Internal Efficiency" bullet
renamed and rewritten to lead with the Indeed story, keeping Amazon's
RPA program as supporting history; new "AI Governance & Security" bullet
connecting the security certs to the Indeed privacy/security/legal
review work; matching new bullet added at the top of the Indeed
experience entry; Okomp bullet reframed). Headline/positioning left
untouched — the CV stays a general-purpose asset, the interim pitch
lives in the message instead.

**Delivery format problems and fixes**, since no markdown source existed
for the CV (only the original `.docx`):
1. Converted the `.docx` to HTML via `textutil`, edited it there, and
   regenerated a new `.docx` (`CV_v5_ai-enablement-transformation.docx`)
   — round-tripped cleanly on inspection.
2. User reported the re-imported `.docx` looked wrong in Google Docs.
   Built a properly styled, standalone HTML version instead
   (`CV_v5_ai-enablement-transformation.html`, kept local-only —
   deliberately not published as a Claude Artifact, since it's personal
   CV data) plus a matching PDF, rendered via headless Chrome and
   verified visually (not just assumed) by rendering actual PDF pages to
   PNG and inspecting them.
3. User asked for two design changes: Core Strengths from two columns to
   one, and a more readable font (Georgia serif → system sans-serif
   stack). Made both, re-verified visually.
4. User edited the HTML directly (removed "since early 2026" from the
   Indeed bullet) and asked for the PDF to be regenerated with no
   sections splitting across pages, and proper header/footer margins.
   Found Chrome CLI's `--print-to-pdf` doesn't support real header/
   footer templates — installed `puppeteer-core` (points at the existing
   Chrome install, no extra Chromium download) to get genuine
   `displayHeaderFooter`/`headerTemplate`/`footerTemplate` support with
   real `pageNumber`/`totalPages` fields, not faked. First attempt at
   "no splitting" (wrapping whole list/column blocks in
   `break-inside:avoid`) overcorrected — created large blank-page gaps
   by forcing entire multi-bullet sections to jump pages as one unit.
   Fixed by narrowing the atomic unit to individual list items and whole
   job entries (title + bullets) rather than entire sections — back to a
   clean 3 pages, verified page-by-page, no bullet or job entry split
   across a break, consistent margins and running header/footer on every
   page.

### The message
Drafted and sent — an explicitly honest strengths-and-weaknesses email
rather than a straightforward "yes, I'm interested." Structure: real
strengths (transformation track record, the new Indeed AI-adoption
story, the security/AI certs, Tokyo/PR), real weaknesses stated plainly
(Japanese not yet fluent, more senior than the stated band, not
available for full-time employment), then the interim Head of AI &
Transformation proposal as the resolution to the last point — framed as
"I didn't want to leave it unsaid" rather than a pivot away from
interest. Neither Mario nor Georgios knew about the interim angle before
this message.

**Sent. Awaiting their reply** — no forced follow-up date set; logged to
SPRINT.md's Blocked/Waiting and OUTREACH.md's Response Log (Mario's row
consolidated to cover the full thread through today).

## Files touched this session
- OUTREACH.md — Keisuke Oishi Response Log row added; Sara Al-Attas row
  updated (follow-up sent); Dharmesh Raithatha row updated (30-day defer
  decision); Mario Kushtgjini row substantially rewritten to cover the
  call, the JD, the interim pitch, and the CV v5 update
- SPRINT.md — Connector outreach #1, Sara follow-up checked off; Dharmesh
  follow-up marked done (decision made); new Blocked/Waiting entry for
  the Mario/Renesas reply; new Upcoming/unscheduled reminder for the
  Dharmesh 30-day reconnect
- RECRUITERS.md — JAC's no-current-match reply logged to Outcomes Log
- FACTS.md — new Indeed AI-adoption-leadership fact added
- LEARNINGS.md — 3 new entries: the interim-pitch-as-dual-fix pattern,
  the `classify-contact` wording fix, and the CV-reframe-before-rewrite
  principle
- `.claude/commands/classify-contact.md` — wording convention refined
  ("same-company connection" vs. "ex-colleague")
- `uploads/private/` (all gitignored, not committed) —
  `mario-kushtgjini-call-prep_2026-08-06.md`,
  `CV_v5_ai-enablement-transformation.{docx,html,pdf}`,
  `leadership-in-japan-deck.html`'s PDF export,
  CRM priority-list rows updated for Oishi
- Claude Artifact (private, not committed to git) — "Leadership in Japan
  — Field Notes," 22 slides
