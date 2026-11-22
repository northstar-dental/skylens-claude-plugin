---
name: schedule-and-huddle
description: Use for questions about a day's appointments, tomorrow's schedule, or a team huddle based on the practice's data.
---

# Schedule and huddle

Use only SkyLens tools that the connection exposes. Follow their current schemas
instead of assuming every practice has the same tools or parameters.

1. Call `list_locations` to choose the requested office and its connection.
   Clarify an ambiguous office. Pass the office and connection parameters the
   selected tool accepts; report the offices actually returned.
2. Convert "today" or "tomorrow" to a date in the office's time zone, and state
   that date. Ask for a date if none is clear. A schedule is from the nightly
   copy: give its freshness and do not present it as a live appointment book.
3. Call `schedule_for_day` for that date. Keep appointment statuses visible and
   distinguish booked, completed and broken appointments using the result's
   definitions. Missing patient-name fields do not mean an appointment is empty.
4. If `day_huddle` is available, call it for a briefing on the same date and
   office. Otherwise summarize only what the schedule actually returns; say
   which requested huddle figures are unavailable. Never make up missing counts.
5. Check closure information when returned before calling an empty day quiet.
   Explain missing data and truncation. Do not treat a future huddle's zero
   completed production as a forecast, or offer clinical recommendations.

When identities are hidden, say: "Patient identities are hidden for this
connection. The optional 'Also share patient identities and notes' permission
controls whether they can be shared." Give the permitted schedule details;
never infer names, fetch them elsewhere or work around the permission.
