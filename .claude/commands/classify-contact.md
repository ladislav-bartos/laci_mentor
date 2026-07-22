---
description: Classify a CRM contact's Target Fit (vs Ideal Contact Profile) and Role Type (Buyer/Connector/Neither), for the LinkedIn bulk pass or new contacts as they're added
argument-hint: [one contact's name/title/company, a list of several, or a path to an exported CSV]
model: claude-haiku-4-5-20251001
---

On-demand contact classification. Purpose: apply the CRM's Target Fit and
Role Type rules consistently — for the pending bulk pass on the ~8,000
LinkedIn export once it lands, and for any new contact added later —
instead of re-deriving the criteria from memory each time.

Steps:

1. Read `FACTS.md`'s "Business Development System" section for the current
   Ideal Contact Profile and Role Type definitions. Apply these refinements
   (not yet in FACTS.md's prose — treat as authoritative):
   - (2026-07-17) A LinkedIn 1st-degree connection with no real in-person or
     working relationship defaults to **Connector**, not Buyer, regardless
     of title, unless there's specific evidence of an actual working
     relationship — being connected on LinkedIn alone isn't evidence of a
     Buyer tie.
   - (2026-07-22) The hard-constraint exclusion (no HR-tech/job-board/
     recruitment-platform clients) applies to **Target Fit**, not Role
     Type — mark Target Fit **N** for the contact's company if it's a
     recruiting/staffing/executive-search agency (e.g. Robert Half, Michael
     Page, Randstad, TEKsystems, Morgan McKinley, any "K.K." recruiting
     firm) or a job board/recruitment-matching platform (e.g. Indeed,
     LinkedIn, YOUTRUST, Findy, Daijob.com) — regardless of the company's
     own scale — but still classify the *contact* as Role Type Connector
     (recruiters/platform staff are facilitators, per the Connector
     definition below).
   - (2026-07-22) Ex-colleagues from the user's own known past employers
     (Indeed, Rakuten, Amazon, DAZN) are a real relationship, not a bare
     LinkedIn connection — classify them as Connector (ex-colleague) by
     default rather than defaulting on ambiguity; Target Fit for their
     *current* employer still follows the normal rule above (e.g. still N
     for Indeed).
   - (2026-07-22) Rows with no name at all (fully blank export rows) have
     nothing to classify — skip them, don't output a row.
2. For each contact in `$ARGUMENTS` (a single contact, a pasted list, or a
   CSV path):
   a. **Target Fit (Y / N / Unclear):** does the contact's *company* match
      the ICP — growth-stage (Series B+) through enterprise, and either
      expanding into Japan/APAC or already Japan-based and scaling? If the
      available info doesn't say, mark "Unclear" — don't force a guess.
   b. **Role Type (Buyer / Connector / Neither):**
      - Buyer: could personally decide to hire — CEO/COO/CPO, Head/VP of
        Product, Country Manager Japan
      - Connector: not a buyer, but knows buyers — ex-colleagues,
        recruiters, VC/PE staff, other fractional execs, board members/
        advisors, OR any LinkedIn-only connection per the refinement above
      - CHRO/Head of Talent counts as a Connector-equivalent facilitator —
        include even if their employer is HR-tech (the hard-constraint
        exclusion is about *clients*, not about a contact's own function)
      - Neither: fits none of the above — e.g. students, academics/
        researchers at non-business institutions, unrelated small local
        businesses (dental, real estate, retail), individual freelancers/
        gig workers, or anyone with no plausible business network value
   c. Note one line of reasoning per contact — makes the output
      spot-checkable rather than a black box, and cheap to correct.
3. Output format depends on volume:
   - Small batch (fits comfortably in a chat message): a table — Name,
     Company, Title, Target Fit, Role Type, Reasoning — formatted to paste
     directly into the CRM Google Sheet's columns.
   - Large batch (a CSV export, hundreds+ of contacts): write the same
     columns as an actual CSV file (the caller will specify the output
     path) instead of a chat table — paste-into-sheet formatting doesn't
     scale to thousands of rows in a single response.
4. This command has no write access to the Google Sheet — it only
   produces output (chat table or CSV file) for the user to import/paste
   in. For a batch run, tell the user to spot-check a sample before
   trusting the full set, especially any "Unclear" Target Fit rows.

This command runs standalone — no "wrap" step required. If run mid-standup
or mid-review, mention the batch result in that session's minutes instead.
