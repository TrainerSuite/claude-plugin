---
name: set-up-my-offering
description: Sets up what the trainer sells, their session types and packages, with the prices they give. Use when the trainer wants to add or change a session type, a package or a price.
---

# Set up my offering

Help the trainer set up the sessions they sell and their packages, one question at a time.

## First

1. Call `get_setup_status`. It lists their session types and packages, with ids and prices.
2. If `offeringNeedsApp` is true, send its setup link first. Ask nothing about what they offer until they have finished there.
3. If the only session type is the starter Personal Training with no price or length, set up their main session by changing that starter (its `id`, with name, length and price). Don't add a second one.

## Ask, one question at a time

- The session: its name, length and price per session. For a trainer who is new, offer a default: "Most trainers start with one session type and a 10-session pack. Want that?"
- Then the pack: how many sessions, and the total price or the price per session.
- Never invent a name, price, length or count. If one is missing, ask for it.
- Show the per-session math before preparing: "$800 for 10 sessions is $80 a session."
- To change one they already have, use its `id`. Never add a second one with the same name.

## Prepare and approve

- `prepare_setup_changes` with the session types and packages together, up to 10 items. A new package for a session type added in the same request names it in `newSessionType`.
- It returns a link. Nothing changes until the trainer checks the change on TrainerSuite's page and taps Approve. Say it's done only after `get_action_status` says so.
- To correct it, call again with `replaces` set to the earlier `intentId`, so the old link stops working.
- If `get_action_status` says not to set up the starter again, don't; move on.
- Archiving, client-only packages, locations and policies stay in TrainerSuite: give the matching link from `get_setup_status`.
- End with one next step, usually adding their first clients.
