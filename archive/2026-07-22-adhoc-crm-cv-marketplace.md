# 2026-07-22 (Wed) — Adhoc — Model guide, CRM bulk classification, CV rebuild, Service Marketplace

Continuation of today's standup session (see `archive/2026-07-22-standup.md`
for the morning inbox/planning portion). This covers the rest of the day's
work on Sprint 2's picks.

## Model-selection guide
User asked for a cost-conscious model-routing setup before starting the
bulk contact classification. Built `MODELS.md`: Haiku 4.5 for mechanical/
high-volume commands (`classify-contact`, `add-note`), Sonnet 5 default
for conversational/quality-sensitive work (standups, adhoc, review,
draft-outreach, research-*). Pinned via `model:` frontmatter in the two
command files. Confirmed scope with user first (commands only, not the
conversational sessions).

## Uploads folder structure
Set up `uploads/private/` (gitignored) and `uploads/shared/` for future
file uploads, splitting PII/sensitive content from anything safe to
commit. User's own idea, in response to needing to upload the LinkedIn
export.

## Bulk contact classification
- LinkedIn export (`Connections.csv`, renamed
  `linkedin-connections-2026-07-22.csv`) uploaded to `uploads/private/`.
- First batch of 300 contacts processed inline (286 after skipping blank
  rows) as a spot-check-ready sample.
- Remaining ~8,300 contacts split into 9 batches of up to 1,000, run as
  parallel background Haiku subagents, each reading its own line range
  and writing its own output CSV.
- **Bug found:** several batches ignored the "LinkedIn-only defaults to
  Connector, not Buyer absent real relationship evidence" rule and
  title-matched instead — Buyer rates ranged from 1% to 39% across
  batches, wildly inconsistent with batch 1's manually-done 1/286. Also
  found a Target-Fit-Y=0 anomaly in one batch (too conservative the other
  direction).
- Ran a correction pass on every batch 2-10: re-audited every Buyer-
  labeled row, downgraded any without real ex-colleague evidence (Indeed/
  Rakuten/Amazon/DAZN) to Connector. Also had the anomalous batch
  re-review its Target-Fit-Unclear rows against general company
  knowledge.
- **Final result:** 8,025 contacts classified. Target Fit: Y=1,477,
  N=1,199, Unclear=5,346. Role Type: Buyer=4, Connector=6,757,
  Neither=1,261. The 4 Buyers: Shingo Matsushima (D-Wave, APAC/Japan
  country manager), Amir Bendjazia (DAZN, ex-colleague), Masa Hirata
  (DAZN, ex-colleague), Ayako Ishida (Amazon, ex-colleague).
- Made the correction-driving refinements permanent in
  `.claude/commands/classify-contact.md` (job-board/recruiting-agency
  Target-Fit-N-but-Connector rule, ex-colleague-company defaulting,
  blank-row skipping) so future single-contact classifications inherit
  them automatically.
- Two residual quality caveats flagged to user rather than chased
  further: batch 4's unusually high "Neither" rate, batch 9's Target-
  Fit-Y correction landing higher than other batches' rates. Judged not
  worth another full audit round given diminishing returns.

## Priority list + CRM import
Merged all 10 corrected batches into a single tiered priority list,
confirming the tiering scheme with the user first:
1. Buyers (4)
2. Connector + ex-colleague (Indeed/Rakuten/Amazon/DAZN) — 281
3. Connector + facilitator function (recruiter/VC/PE/board/advisor) — 818
4. Connector + cold LinkedIn but Target-Fit-Y employer — 1,051
5. Connector + everything else — 4,607
(Neither excluded from the priority list entirely.)

Output: `uploads/private/crm-priority-list-2026-07-22.csv`, columns
matched to the existing CRM Google Sheet schema plus a new Priority Tier
column. Recommended importing as a new "LinkedIn Bulk Import" tab rather
than merging into existing CRM rows, to avoid disturbing the ~10
already-manually-added warm contacts.

## Inbound LinkedIn Service Marketplace requests
Two requests reviewed today, plus a mechanics correction:

**Mechanics correction:** these are posted marketplace listings, not
direct messages — nothing to "decline," the only choice is whether to
submit a proposal. Decision rule built earlier in the day (service-line
match / buyer-or-connector / ICP fit / reply-or-silence / feedback loop)
adjusted accordingly.

**Rushikesh M.** (Junior Data Analyst, dashboard-building request) —
skipped, no proposal. Off-service-line and non-buyer.

**Sara Al-Attas** (Head of Strategy, Riyad Bank — org-politics/
leadership-presence coaching) — initially recommended declining on pure
ICP-fit grounds; user pushed back with new context: mentoring background
(~5 mentees, ~4/5 women, strong track record building leadership
confidence). Reframed as the same "treat first attempts as low-stakes
practice" pattern already used for outreach, applied to a new
opportunity type, contingent on current spare capacity. Drafted and sent
a trial-then-$100/hr coaching proposal (`OUTREACH.md` template 5),
logged in its Response Log (pending).

**Sutirtha Prakash** (career transition, targeting AI/product-strategy/
digital-transformation leadership roles) — stronger fit than Sara's
since the subject matter is the user's own domain (he did almost exactly
this positioning exercise for himself 2026-07-14). Ask was ambiguous
(60-day plan vs. 360 review; unclear who builds it), so drafted an
intro-call-first message instead of quoting terms (`OUTREACH.md`
template 6). User corrected an early draft that named a specific tactic
("job-posting reverse-engineering method") as a selling point — replaced
with genuine lived experience (repeated 60-90 day plans when moving into
new companies/roles).

New task queued for a future sprint: research LinkedIn Service
Marketplace mechanics + best practices + review selected service
categories against who gets recommended, to reduce false-positive leads
like Rushikesh — build `SERVICE_MARKETPLACE.md`.

## CV rebuild
Registration with Robert Walters Japan (the recommended first pick from
`RECRUITERS.md`) was underway when the user asked what CV version to
upload. Found 4 CV files freshly uploaded to `uploads/private/`:
- v1 (`Ladislav_Bartos_CV.docx`) — technical/ML-engineering framing,
  explicitly superseded by the 2026-07-14 positioning decision
- v2 (`Ladislav_Bartos_CV_2026.docx`) — growth-framing draft, missing
  the quantified achievements
- v3 (`Ladislav_Bartos_CV_tripla_VPoP.docx` + matching PDF) — complete,
  quantified, current best version

Cross-checked v3 against the finalized LinkedIn positioning and found
two gaps: no "Fractional/Interim" framing anywhere (reads as a
full-time-exec CV), and only the Growth half of the two-pillar
positioning — the Transformation pillar (team/process/OKR, AI-driven
efficiency) was entirely unlabeled despite several bullets already
being transformation evidence (Rakuten team restructuring, Amazon RPA
automation).

User chose to pause the registration and rebuild the CV properly rather
than submit v3 as-is. Archived v1/v2 to `uploads/private/cv-archive/`,
renamed v3 files with clearer names, and built v4
(`CV_v4_fractional-interim-growth-transformation.docx`): explicit
Fractional/Interim framing, Core Strengths reorganized into labeled
Growth and Transformation groups (no new achievements invented — existing
bullets relabeled/regrouped), rest of the content unchanged from v3.

Could not generate a local PDF (no pdflatex/LibreOffice installed) —
user to export via Google Docs before submitting. Robert Walters
registration pushed to tomorrow; specialization dropdown choice
("Product data & design" vs. "Technology & digital" vs. "C-suite &
executive search") still open, user's call.

## Files touched today (full list)
`MODELS.md` (new), `.claude/commands/classify-contact.md`,
`.claude/commands/add-note.md`, `.gitignore`, `uploads/shared/.gitkeep`
(new), `FACTS.md`, `SPRINT.md`, `LOG.md`, `LEARNINGS.md`, `OUTREACH.md`,
plus private (ungitted) files in `uploads/private/`: the LinkedIn
export, 10 classification batch CSVs, the merged priority-list CSV, and
the CV files (archived + new v4).
