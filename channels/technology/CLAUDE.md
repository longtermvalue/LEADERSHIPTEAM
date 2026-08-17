# Technology (CTO/IT) Channel

Owns the company's technical footprint: the tool stack, website health, security
posture, access control, and backups/continuity. For a small business this channel
is about not getting burned — lost data, hacked accounts, a broken website nobody
noticed — and about the stack costing what it should.

## Agents
| Agent | Use for |
|---|---|
| `cto-stack-auditor` | Tool/systems inventory health: fit, overlap, cost, risk, integration gaps |
| `cto-website-auditor` | Technical site health: uptime, speed, SSL/DNS, mobile, forms, tracking |
| `cto-security-auditor` | Security posture: MFA, passwords, access, phishing readiness, incident prep |
| `cto-data-steward` | Backups, data locations, retention, recovery testing, continuity |

## Skills: `/it-security-check`

## Data
- The **canonical systems/tool inventory is shared with Operations**:
  `channels/operations/data/systems/` — read and extend it there; don't fork a copy.
- `data/access/` — who has access to what (exports from Google Workspace/M365 admin,
  password-manager reports, domain registrar/hosting account lists)
- `data/website/` — hosting/DNS details, speed test exports, uptime reports,
  analytics-tag inventory
- `data/security/` — MFA status exports, security-tool reports, past incident notes,
  phishing-test results
- `data/backups/` — backup configurations, last-restore-test notes, retention docs
- `data/it-vendors/` — hosting, domain, SaaS security docs, IT support agreements

## Channel rules
- **Defensive posture only**: this channel hardens the company's own systems and
  never produces offensive tooling or instructions for attacking anything.
- Never store live secrets: no passwords, API keys, recovery codes, or full license
  keys anywhere in this repo — findings reference where a credential lives (e.g.,
  "in 1Password vault X"), never the credential itself. If a data file arrives
  containing secrets, flag it for removal instead of quoting it.
- Findings ranked by risk = likelihood × impact, in plain business language ("one
  compromised email account exposes client billing" beats CVSS jargon).
- Security/backup recommendations state cost (money + effort) honestly — a small
  business needs the 20% that stops 80% of harm, not an enterprise checklist.
- Coordinate: tool-cost findings → `cfo-cost-optimizer`; departing-employee access
  revocation feeds `hr-onboarding-offboarding`'s checklist; privacy safeguards
  align with `legal-privacy-officer` (PIPEDA); website conversion issues →
  marketing channel (this channel owns *technical* health).
