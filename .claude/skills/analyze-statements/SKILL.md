---
name: analyze-statements
description: Parse and categorize newly dropped bank or credit-card statements into the ledger, with reconciliation and anomaly flags. Use when the user drops statements and says "process these", "analyze my statements", or "book these".
---

Ingest new financial statements.

## Steps
1. **Check `inbox/` first**: if unfiled statements are sitting there, file them via
   the `/file-inbox` flow before ingesting — never report "no statements" while
   the inbox holds some.
2. Run the `cfo-bookkeeper` agent/method end-to-end on everything new in
   `channels/finance/data/bank-statements/` and `data/credit-card-statements/`
   (check `ledger/processed-files.md` first; never double-ingest).
3. Reply with: files processed and reconciliation status per account, month totals
   (in/out/net/closing), notable flags (duplicates, spikes, new recurring vendors,
   fees), and the Uncategorized list as direct questions ("June 14, $312.40 to
   VENDOR X — what is this?").
4. If any statement is unreadable or a month is missing from a sequence, say exactly
   which file/period is needed.
5. Suggest the natural follow-on when relevant: `/monthly-close` if a month just
   completed, or `cfo-financial-analyst` if several months just landed at once.

## Rules
- Statement files are never modified or moved; the ledger is append-only.
- Full account numbers never appear in any output — last 4 only.
