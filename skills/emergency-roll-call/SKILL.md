---
name: emergency-roll-call
description: Use in an emergency or evacuation drill at a site using GuestTrack, when someone asks who is still on site, wants a fire roll call or muster list, or wants to text the people not yet accounted for.
---

# Emergency roll call

Be quick and plain: lives may depend on it.

1. `who_is_on_site` for the project: give the total first, then names by check-in point.
2. If they want a roll call, `start_roll_call` (it lists everyone on site to mark off).
3. As people are found, `update_roll_call` with `mark` for each. `text_missing` texts everyone not yet marked: confirm
   before sending.
4. Never end a roll call unless the person asks; then `update_roll_call` with `end`.

`list_roll_calls` shows a running or past roll call.
