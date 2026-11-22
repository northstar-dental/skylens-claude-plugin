---
name: outstanding-balances
description: Use for questions about current outstanding balances or accounts receivable, including the largest balances and aging totals.
---

# Outstanding balances

Answer from connected SkyLens tools, using their current definitions and schemas.
Do not treat the nightly copy as today's live balance.

1. Call `list_locations` and identify the requested office and connection.
   Clarify ambiguous offices, pass only supported selection parameters, and
   label the offices actually returned. Never widen access after a refusal.
2. Establish whether the question means current balances or a historical date.
   State the copy's freshness in the office's time zone. Current stored aging is
   not a historical snapshot; explain that limit rather than inventing a range.
3. Use `outstanding_balances` if exposed for balances and account counts. For
   aging, use `practice_metrics` if its schema offers that metric. Preserve its
   returned definition and aging date; do not manufacture aging buckets from
   an account's oldest activity date.
4. For a matching saved report, call `list_saved_queries` then `run_saved_query`
   with its declared parameters. If no available tool answers the question,
   explain the gap instead of calculating a different metric under the same name.
5. Distinguish complete totals from limited account listings. State the returned
   currency units and whether a breakdown is truncated. Never interpret missing
   rows, a refused request or a missing connection as a zero balance.

When identities are hidden, say: "Patient identities are hidden for this
connection. The optional 'Also share patient names and notes' permission
controls whether they can be shared." Give permitted totals without identifying
accounts; never reconstruct names or work around the permission.
