---
name: onboard-company
description: Set up a freshly duplicated copy of this repo for a new company — interview the user, fill in the company profile, goals, and org chart, and confirm the data drop-zones. Use when the user says "onboard", "set up for <company>", or the profile still has placeholders.
---

You are onboarding a new company into its AI leadership team repo.

## Steps

1. **Check state**: read `company/company-profile.md`. If already filled for another
   company, stop and confirm — this may be the template repo, which must NOT be
   filled with real company data (it stays generic; companies get their own copies).

2. **Interview** — ask in 2–3 grouped rounds, not twenty questions at once. Use
   AskUserQuestion where it helps. Cover, in order of importance:
   - Identity: legal/operating name, structure (Ontario/federal corp, sole prop),
     fiscal year end, HST registered?, location, website
   - Business: what they sell (with prices), who buys, business model, top
     competitors (names/URLs)
   - Scale: employee & contractor count, revenue band, rough Ontario payroll
   - Systems: bank(s), accounting software, payroll, CRM, ad platforms, email tool,
     e-commerce platform if any
   - Priorities: top 3 for the next 90 days; any hard constraints
   Accept "skip" for anything — leave the placeholder and note it.

3. **Write the files**: fill `company/company-profile.md`, `company/goals-and-okrs.md`
   (translate the priorities into draft goals with numbers where given — mark drafts),
   and `company/org-chart.md` (names/roles given, or leave the table headed).

4. **Personalize the README title line** to the company name (e.g.,
   "# AI Leadership Team — Acme Corp").

5. **Data walkthrough**: from the systems answers, produce a tailored "first data
   drop" checklist — the 5–8 highest-value exports for THIS company and the exact
   folder for each (e.g., "RBC chequing statements (last 3 months, PDF) →
   `channels/finance/data/bank-statements/`"). Prioritize: bank statements,
   accounting export, ad export (if advertising), CRM export (if they have one),
   payroll register, current policies/handbook.

6. **Cadence & channels**: tune `company/routines.md` for this company (enable the
   e-commerce/board rows if applicable, disable what doesn't fit) and point to
   `docs/automation.md` for scheduling `/run-routines`. If they use Slack, offer to
   fill `company/slack-channel-map.md` from their channel names (`docs/slack.md`).

7. **Finish**: summarize what was set up, what's still placeholder, the first-drop
   checklist, and suggest the natural first runs (`/analyze-statements` after the
   statements land, `/hr-compliance-check`, `/marketing-audit`). Offer to commit.

## Rules
- Never invent company facts to fill gaps — placeholders with a note beat guesses.
- If the user pastes sensitive identifiers (full account numbers, SINs), store only
  masked versions and say so.
