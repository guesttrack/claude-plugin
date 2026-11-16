---
name: set-up-guesttrack
description: Use when someone wants to start using GuestTrack, set up visitor check-in, sign-in or a visitor book for a site (office, school, clinic, building site, warehouse gate, event, club), or add an entrance, question, host or group to an existing GuestTrack project.
---

# Set up GuestTrack for a site

GuestTrack calls one site or business a **project**. People check in at a **check-in point** (a door, gate or desk with
its own QR code) by filling in the project's **Check-in form**. **Hosts** are the people visitors come to see, told
when their visitor arrives. **Groups** hold regulars (contractors, students, members).

## Steps

1. Ask, in one message: what kind of site it is, its name, where people arrive (each entrance), its time zone and
   country, and whether visitors should check out when they leave. Don't ask what you can infer.
2. Pick the kind: `office` (offices, reception, schools, clinics), `site` (contractors, building sites), `gate`
   (warehouse and logistics gates), `event`, `community` (clubs and groups).
3. Show the plan as a short list (project, check-in points, the questions you'll add, hosts, groups) and wait for a
   yes.
4. Ask the person to agree to GuestTrack's [Terms](https://guesttrack.io/terms) and
   [Privacy Policy](https://guesttrack.io/privacy-policy). Only after they agree, call `create_project` with
   `acceptTerms: true` and the first entrance as `checkInPointName`.
5. Call `save_check_in_point` for each other entrance.
6. Call `edit_check_in_form` without `action` to see the form the kind of site came with, then add, hide or reorder
   questions. Ask only what the site needs: a school asks who the visitor is here to see and whether they hold a
   Working with Children Check; a building site asks for the company and an induction.
7. If visitors come to see someone, call `set_hosts` with names and emails, and make sure the form has a host
   question (`host: true` on a text box).
8. For regulars, call `save_group`, then add their questions with `askedOf` set to the group's id.
9. Finish with each check-in point's `checkInUrl`, and say the QR codes are printed from GuestTrack's dashboard,
   Check-in points.

## Changing an existing project

Start with `list_projects` and `get_project_overview`. Its `thisConnectionCan.setUp` says whether you may change
setup. If it's false, tell the person to disconnect GuestTrack and connect it again with "Set up and change your
projects" ticked; their role may also not allow it (owners, administrators and project managers can).

## Never

- Create a project without the person's yes to the Terms.
- Change plans, billing, the team or record retention: these are only in the dashboard at guesttrack.io.
