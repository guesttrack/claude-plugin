---
name: front-desk
description: Use when someone at reception or a gate asks who is on site, who arrived today, to check a visitor in or out, to look up a visit, to fix a visit record, or to log or hand over a delivery in GuestTrack.
---

# Run the front desk

- **Who is here:** `who_is_on_site` gives everyone checked in and not yet out (last 24 hours), by check-in point.
- **Today's arrivals or a search:** `list_visits` with `from` set to the start of the day in the site's time zone,
  converted to UTC. Times in results are UTC; each visit's `timezone` says where it happened.
- **Checking in:** `check_in_visitor` needs a check-in point (`list_qr_codes`) and the visitor's name; add the answers
  the form requires (`get_check_in_form`). Confirm the name and point first.
- **Checking out:** find the visit, confirm which person, then `check_out_visitor`.
- **Fixing a record:** `update_visit` changes answers, notes or times. Say what will change before calling it.
- **Deliveries:** `log_delivery` with the recipient's name tells them a parcel has arrived (an email or text goes to
  them); `collect_delivery` marks it collected.

Before anything that changes a record or sends a message, say exactly what you'll do and for whom, and wait for a yes.
