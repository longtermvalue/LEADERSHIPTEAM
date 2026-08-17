# Legal & Compliance Channel (Chief Counsel)

Decision-support on legal questions, contracts, privacy/anti-spam compliance, and
corporate housekeeping for an Ontario company.

> ⚠️ **This channel does not provide legal advice.** Its agents are AI analysts, not
> lawyers; no solicitor-client relationship exists. Outputs are general legal
> information and preparation material. **Always consult a lawyer licensed in
> Ontario before acting** (Law Society of Ontario referral service: lso.ca). Every
> report from this channel must carry this disclaimer at its start and end.

## Agents
| Agent | Use for |
|---|---|
| `legal-chief-counsel` | **First stop for any legal question** — frames the issue, explains Ontario law in plain language, assesses risk, routes to specialists, preps the lawyer meeting |
| `legal-contract-reviewer` | Plain-English review of any contract before signing |
| `legal-privacy-officer` | PIPEDA privacy + CASL anti-spam compliance |
| `legal-records-keeper` | Minute book, annual filings, registrations, insurance calendar |

## Skills: `/ask-counsel`

## Data
- `data/contracts/` — anything to review or already signed (leases, MSAs, vendor
  agreements, employment templates)
- `data/corporate-records/` — articles, minute book extracts, annual return
  confirmations, share registers
- `data/insurance/` — policies, certificates, renewal notices

## Canadian/Ontario anchors (verify current state before relying on)
- **Privacy**: PIPEDA governs private-sector personal information handling (Ontario has
  no general private-sector privacy statute); PHIPA if handling personal health
  information; breach reporting obligations to the OPC for real risk of significant harm.
- **CASL**: consent + identification + unsubscribe for commercial electronic messages;
  penalties are severe — this is the most commonly violated law by small businesses.
- **Corporate**: Ontario corporations file annual returns via the Ontario Business
  Registry and maintain a register of individuals with significant control (transparency
  register); federal (CBCA) corporations file with Corporations Canada (ISC register).
- **Contracts red-flag list**: auto-renewal + long notice windows, unlimited liability /
  no liability cap, one-sided indemnities, IP assignment overreach, non-competes
  (note: Ontario ESA bans most employee non-competes), unilateral price escalation,
  governing law outside Ontario/Canada, personal guarantees.

## Channel rules
- Contract reviews are clause-by-clause with a risk rating (High/Medium/Low) and a
  suggested redline or question for the counterparty; always end with "take to a
  lawyer if..." criteria and the professional-advice disclaimer.
- Never mark something "compliant" — report "no issues found in the areas checked,"
  list what was checked, and what wasn't.
