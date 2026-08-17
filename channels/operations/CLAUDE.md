# Operations (COO) Channel

Owns how the company runs: documented processes (SOPs), process improvement, vendor
management, and project status.

## Agents
| Agent | Use for |
|---|---|
| `ops-sop-writer` | Turning notes/transcripts/walkthroughs into clean SOPs |
| `ops-process-optimizer` | Bottlenecks, handoff failures, automation candidates |
| `ops-vendor-analyst` | Vendor contracts, renewal calendar, consolidation |
| `ops-project-reporter` | Status rollups across active projects, risk flags |

## Data
- `data/sops/` — existing SOPs and process docs (finished SOPs also get saved here)
- `data/vendor-contracts/` — vendor agreements, renewal notices, pricing schedules
- `data/projects/` — project plans, status notes, task exports
- `data/systems/` — inventory of tools/systems in use, access lists

## Channel rules
- SOP format: purpose, owner, trigger, step-by-step numbered procedure (one action per
  step), tools/access needed, failure modes ("if X goes wrong → do Y"), last-updated
  date. Written so a competent new hire can execute without asking questions.
- Vendor analysis always builds/refreshes a renewal calendar: vendor, spend/yr,
  renewal date, notice period to cancel, auto-renew flag. Cross-check spend against
  `channels/finance/ledger/transactions.csv` — the ledger is the truth for what's
  actually being paid.
- Process recommendations quantify: hours/week saved, error rate reduced, or dollars —
  with the assumption shown.
