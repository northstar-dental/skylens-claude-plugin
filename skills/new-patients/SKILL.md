---
name: new-patients
description: Use for questions about how many new patients the practice saw or added over a period, including office and period comparisons.
---

# New patients

Use connected SkyLens tools and their current schemas. A count needs both a date
range and a definition; do not substitute one definition for another silently.

1. Call `list_locations` to resolve the office and connection. Clarify an
   ambiguous office, use supported selection parameters, and label the offices
   actually included. Do not assume the accessible list equals every office.
2. Resolve the requested range in the office's time zone and state both dates.
   For a comparison, state each period separately. Include the copy's freshness
   and note an incomplete current period before comparing it with a full one.
3. When `new_patient_counts` is exposed, choose its supported range and
   definition: first visit for patients seen, chart creation for records added.
   Do not turn an arbitrary calendar range into a rolling window silently.
4. Otherwise use `practice_metrics` only if it offers the requested definition,
   or find a matching query with `list_saved_queries` and `run_saved_query`.
   For a custom read-only query, call `query_writing_guide` before
   `query_open_dental` and inspect the available schema. Never guess columns,
   duplicate counts across offices, or broaden access after a refusal.
5. Name the returned definition next to the count. Distinguish a supported zero
   from missing data or an error. Explain truncation in a breakdown rather than
   presenting a partial list as a complete total.

When identities are hidden, say: "Patient identities are hidden for this
connection. The optional 'Also share patient identities and notes' permission
controls whether they can be shared." Answer with permitted counts; never try
to identify patients from dates, identifiers or another source.
