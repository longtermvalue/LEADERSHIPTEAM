---
name: inventory-review
description: Run the inventory health review — stockout risks with reorder-by dates, dead/slow stock with disposition options, turns, and cash tied up. Use when the user drops inventory/sales exports and says "inventory review", "what should I reorder?", or "how's my stock?"
---

Run the inventory review.

## Steps
1. Check ingredients: newest files in `channels/ecommerce/data/inventory-exports/`
   (with as-of date) and `data/sales-exports/` (velocity history), plus catalog
   costs and supplier lead times. Missing pieces → run what's possible and list
   exactly which export unlocks the rest (e.g., "no lead times on file — add a
   `data/suppliers/lead-times.md` or supplier list with typical delivery days").
2. Run the `ecom-inventory-analyst` method end-to-end (velocity → cover buckets →
   stockout list → reorder proposals → dead stock → turns/cash).
3. Cross-checks: large reorder proposals vs. the latest cash forecast (flag
   conflicts); dead-stock promo candidates → note for marketing.
4. Reply with: the reorder-NOW table (SKU, reorder-by date, qty, cash needed),
   total $ in dead/overstock with top disposition moves, cash-in-stock summary, and
   the report path (`channels/ecommerce/reports/YYYY-MM-DD-inventory-review.md`).

## Rules
- Every reorder shows its math (velocity window, lead time, safety assumption).
- Proposals only — nothing is ordered by this skill; large POs carry the cash-check
  flag.
