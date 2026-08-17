---
name: ecom-audit
description: Run the full e-commerce review — SKU-level profitability, storefront/checkout conversion, inventory posture, and supplier risk — into one prioritized report. Use when the user says "ecom audit", "review my store", or "why isn't the store making money?"
---

Run the e-commerce audit.

## Steps
1. Inventory available data across `channels/ecommerce/data/*` (sales exports,
   inventory, catalog costs, storefront material) and note gaps up front.
2. Run the specialist methods (parallel where possible):
   - `ecom-sku-profitability-analyst` — the economics spine; always runs if sales
     data exists
   - `ecom-store-optimizer` — funnel + page/checkout audit (fetch the live store
     when available)
   - `ecom-inventory-analyst` — condensed posture (stockouts on heroes, $ in dead
     stock)
   - `ecom-supplier-analyst` — single-source risks and landed-cost flags on hero
     SKUs
3. Synthesize ONE report, `channels/ecommerce/reports/YYYY-MM-DD-ecom-audit.md`:
   verdict → contribution-margin picture (heroes, bleeders) → funnel leaks $-sized →
   inventory cash posture → top 10 moves ranked by dollar impact across all four
   areas → 30-day plan → data gaps.
4. Reply with the verdict, top 5 moves, and the report path.

## Rules
- Everything converges on contribution dollars: a storefront fix on a
  negative-margin SKU is not a win — sequence moves accordingly.
- Hero SKUs get priority in every sub-analysis; the long tail goes to appendices.
