---
name: production-and-collections
description: Use for questions about the practice's production or collections over a period, including comparisons between periods or offices.
---

# Production and collections

Use only the connected SkyLens tools and their current input schemas. Ground
every number in a tool result; never estimate from general dental knowledge.

1. Call `list_locations`. Identify the requested office and connection from its
   result. If several offices could match, ask which; never guess an identifier.
   Use only the offices the tools allow and label the scope actually returned.
2. Resolve relative dates in the office's time zone. For month-to-date use the
   first of the month through today. State both dates and the time zone; clarify
   an ambiguous comparison before running it. Note the copy's freshness.
3. Prefer `practice_metrics` when available for production and collections. Use
   its returned definitions and dates. If `production_summary` is exposed instead,
   use it only for a supported rolling window, not an arbitrary calendar period.
4. For a question the available metrics do not cover, look for a matching saved
   query with `list_saved_queries` and run it with `run_saved_query`. If writing
   SQL is needed and `query_open_dental` is available, call `query_writing_guide`
   first and inspect the schema with the available schema tools. Never invent a
   tool, column or metric, or broaden office access to make a query work.
5. Keep production, adjustments, write-offs and collections distinct. Follow
   returned units and collection settings; do not double-count prepayments.
   Explain incomplete periods, stale copies, errors and truncated breakdowns.

When patient names are hidden, say: "Patient names are hidden because this
assistant was connected without 'Also share patient names and notes'. If your
practice has decided to share patient information with this assistant, disconnect
SkyLens in the assistant. Then connect again and allow that permission." Answer
from the permitted totals; never infer identities, retrieve them elsewhere or
work around the permission.
