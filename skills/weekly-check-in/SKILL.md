---
name: weekly-check-in
description: Gives the trainer a short check-in on what needs them this week, from sessions to confirm and clients who are low or owe to this week's schedule and how the week is going. Use when the trainer asks what needs them this week, for a weekly check-in, or how their week looks.
---

# Weekly check-in

A short look at what needs the trainer this week. Reading only: nothing changes unless the trainer asks for a change.

## Read

1. `get_connected_workspace` for the time zone, if you haven't this chat. Weeks start Monday.
2. `get_business_pulse` with period `week`: sessions and money collected this week.
3. `list_pending_sessions_preview`: past sessions to confirm. Leave out any marked `alreadySettled`.
4. `list_clients_needing_attention`: who is low, who owes, who has an open payment request.
5. `get_schedule` from today through Sunday.

## Answer

- Start with one line: sessions and money collected this week, exactly as the tool returned them.
- Then up to three short parts, in this order, leaving out any that is empty:
  - To confirm: how many past sessions, and the oldest one's date. Old ones mean sessions left are out of date.
  - Clients: each name with its reason in a few words ("2 left", "owes 1", "request open since Oct 3").
  - This week: the sessions still to come, by day, in the trainer's time zone.
- Keep it short. No advice they didn't ask for, and no price or plan talk.
- End with one next step, the first that applies: confirm the past sessions, then a client who is low or owes, then the next session.

## If they want to act

- Confirming: `prepare_pending_resolution`, with the status the trainer says for each session.
- A client who is low or owes: offer a payment request (`prepare_payment_request`) or recording a payment they already made (`prepare_record_payment`).
- Each returns a link. Nothing changes until the trainer taps Approve in TrainerSuite. Say it's done only after `get_action_status` says so.
- If there are no clients yet, say so and offer to help them get started instead.
