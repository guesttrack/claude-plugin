---
name: visitor-reports
description: Use when someone asks how many visitors or check-ins a GuestTrack site had, busiest days or entrances, trends by week or month, or wants a summary or export of visits for a period.
---

# Visitor reports

- **Counts:** `visit_stats` with `from` (and `to`, default now) and `by`: `day`, `week`, `month` or
  `check_in_point`. Pass the site's `timezone` so days split where the site is. If `complete` is false, say the count
  stopped at its limit.
- **Details:** `list_visits` for the visits themselves (page with `cursor`), `get_visit` for one.
- Show counts as a short table or a chart, and say the period and time zone you used.
- Visitor names and contact details are personal: include them only when the person asked for them.
