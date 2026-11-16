---
name: invite-visitors
description: Use when someone wants to invite or pre-register visitors, contractors, guests, students or event attendees in GuestTrack, send or resend an invitation, approve or decline a visitor request, or check who has been invited.
---

# Invite visitors

1. Find the project (`list_projects`) and the check-in point they'll use (`list_qr_codes`).
2. Decide: one visit (`validity: once`, with `expectedAt`) or a regular who keeps coming (`validity: ongoing`,
   optionally in a group from `list_groups`).
3. Decide what is sent: `invite` (an email with their pass), `fill_in` (an email asking them to fill in the form
   before they come) or `nothing` (just add them).
4. Show the list (names, emails, when, what will be sent) and wait for a yes. Then call `invite_people`, at most 100
   people per call; split longer lists.
5. Report who was invited and anyone who failed, with the reason.

`list_invites` shows invites and their status; `update_invite` resends, pauses, resumes, approves or declines one.
Never send to a list the person hasn't seen.
