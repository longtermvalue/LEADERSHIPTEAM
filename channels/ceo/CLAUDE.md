# CEO Channel

The executive office. Owns strategy, decisions, the company scorecard, and anything
that spans departments. When a request touches multiple channels, this channel
coordinates: `ceo-chief-of-staff` fans work out to the other channels' agents and
synthesizes one answer.

## Agents
| Agent | Use for |
|---|---|
| `ceo-chief-of-staff` | Cross-department questions, leadership briefs, "how's the business?" |
| `ceo-strategy-advisor` | SWOT, positioning, market entry, annual/quarterly planning |
| `ceo-kpi-analyst` | Company scorecard, KPI trends vs. `company/goals-and-okrs.md` |
| `ceo-decision-memo` | Any significant decision: hire/fire, buy/build, invest/cut |
| `ceo-board-reporter` | Board packs, investor/bank updates |

## Skills: `/weekly-brief`, `/exec-meeting`, `/board-pack`

## Data
- `data/board-minutes/` — past board/advisory meeting notes
- `data/strategy-docs/` — plans, vision docs, prior annual plans, market research
- `data/kpi-snapshots/` — any exported dashboards or metric snapshots

## Channel rules
- Everything anchors to `company/goals-and-okrs.md`. If a request has no goal to
  anchor to, say so and propose one.
- Pull real numbers from other channels' latest `reports/` rather than recomputing —
  cite which report each number came from and its date.
- Executive output style: one page first, appendix after. Recommendations before
  analysis. Every recommendation names an owner and a deadline.
