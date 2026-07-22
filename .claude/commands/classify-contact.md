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
   Ideal Contact Profile and Role Type definitions. Apply this refinement
   (2026-07-17, not yet in FACTS.md's prose — treat as authoritative): a
   LinkedIn 1st-degree connection with no real in-person or working
   relationship defaults to **Connector**, not Buyer, regardless of title,
   unless there's specific evidence of an actual working relationship —
   being connected on LinkedIn alone isn't evidence of a Buyer tie.
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
      - Neither: fits none of the above
   c. Note one line of reasoning per contact — makes the output
      spot-checkable rather than a black box, and cheap to correct.
3. Output a table: Name, Company, Title, Target Fit, Role Type, Reasoning
   — formatted to paste directly into the CRM Google Sheet's columns.
4. This command has no write access to the Google Sheet — it only
   produces output for the user to paste in. For a batch run, tell the
   user to spot-check a sample before trusting the full set, especially
   any "Unclear" Target Fit rows.

This command runs standalone — no "wrap" step required. If run mid-standup
or mid-review, mention the batch result in that session's minutes instead.
