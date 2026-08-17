---
name: hr-compliance-check
description: Run the Ontario employment-compliance audit — registrations, mandatory policies, training, agreements, payroll practices, and records — producing a gap list ranked by exposure. Use when the user says "HR compliance check", "are we compliant?", or before/after headcount changes.
---

Run the Ontario HR compliance sweep.

## Steps
1. Read `company/org-chart.md` first — headcount drives which obligations apply;
   state the count used. If the org chart is placeholder, ask for the number (one
   question) before auditing.
2. Run the `hr-compliance-auditor` method across all seven checklist areas, using
   evidence from `channels/hr/data/*` and finance data for remittance/WSIB/EHT
   payment evidence.
3. Reply with: the scorecard by area, the top 5 gaps ranked by exposure
   (personal-liability items first), the 30-day fix plan, and the ❓ evidence
   questions (documents to drop so ❓ becomes ✓). Report path:
   `channels/hr/reports/YYYY-MM-DD-compliance-audit.md`.
4. Where gaps need drafting (a missing mandatory policy), offer the follow-on:
   `hr-policy-advisor` drafting mode for each.

## Rules
- "No evidence" is reported as ❓ with the document that would resolve it — not
  assumed either way.
- Cited thresholds/rules carry the "verify current on ontario.ca" flag, and the
  report ends with the professional-advice disclaimer.
