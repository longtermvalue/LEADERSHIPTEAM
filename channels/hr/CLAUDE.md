# Human Resources Channel — Ontario, Canada

Owns the employee lifecycle: hiring, policies, compensation, performance, and
compliance. **Jurisdiction: provincially regulated employers in Ontario** (ESA 2000,
OHSA, Ontario Human Rights Code, AODA, WSIB, Pay Equity Act where applicable; PIPEDA
federally for privacy). If the company is federally regulated (banking, telecom,
interprovincial transport), say so — the Canada Labour Code applies instead and these
agents' Ontario defaults don't.

## Agents
| Agent | Use for |
|---|---|
| `hr-policy-advisor` | Drafting/auditing handbook & policies against Ontario law |
| `hr-recruiter` | Job postings, interview kits, screening rubrics |
| `hr-onboarding-offboarding` | New-hire onboarding; terminations done safely |
| `hr-comp-analyst` | Pay bands, payroll review, EHT/WSIB/CPP/EI sanity checks |
| `hr-performance-coach` | Review cycles, feedback, PIPs |
| `hr-compliance-auditor` | The full Ontario compliance sweep |

## Skills: `/hr-compliance-check`, `/new-hire`

## Data
- `data/policies/` — current handbook, individual policies
- `data/employment-agreements/` — contracts, offer letters, contractor agreements
- `data/payroll-reports/` — payroll registers, T4 summaries, WSIB/EHT filings
- `data/recruiting/` — open role descriptions, candidate notes (anonymize in reports)
- `data/training-records/` — OHSA awareness, WHMIS, AODA training logs

## Ontario anchors (agents: verify current figures on ontario.ca before citing)
- **ESA minimums**: minimum wage (adjusted each Oct 1); vacation 2 wk/4% (3 wk/6% at
  5+ yrs); 9 public holidays; 3 unpaid sick days + other job-protected leaves;
  termination notice/pay 1 wk per year of service to max 8; **severance pay** in
  addition if 5+ yrs service AND employer Ontario payroll ≥ $2.5M; hours-of-work and
  overtime (1.5× after 44 hrs/wk) rules.
- **Mandatory for all employers**: ESA poster available to staff, workplace violence &
  harassment policy + program (OHSA), health & safety policy, worker/supervisor OHSA
  awareness training, WHMIS where hazardous products, WSIB registration/premiums for
  most industries, Employer Health Tax registration once past exemption.
- **Headcount triggers**: see `company/org-chart.md` flags (25+ → disconnecting-from-work
  & electronic-monitoring policies; 50+ → JHSC; 20+ → AODA obligations scale).
- **Hiring rules**: publicly advertised postings must include expected compensation
  range and disclose AI use in screening (Working for Workers amendments, in force
  2026); no "Canadian experience" requirements; Human Rights Code — no questions on
  protected grounds.
- **Termination**: ESA is the floor — common-law reasonable notice can be far larger
  unless a valid termination clause limits it. Any termination, constructive dismissal
  risk, or disability/accommodation issue → recommend employment counsel before acting.

## Channel rules
- Anonymize individuals in analytical reports (use roles/initials); full names only in
  documents meant for that person's file.
- Every legal-adjacent output ends with the professional-advice disclaimer and flags
  figures to verify (rates and thresholds change).
- When headcount matters, read `company/org-chart.md` first and state the count used.
