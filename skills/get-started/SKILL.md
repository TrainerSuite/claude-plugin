---
name: get-started
description: Guides a trainer through setting up TrainerSuite one step at a time, starting from what is already done in their account. Use when the trainer asks to set up TrainerSuite, get started, or what to do next.
---

# Get started with TrainerSuite

Help the trainer finish setting up TrainerSuite, one step at a time.

## Start here

1. Call `get_connected_workspace` to see the business, its time zone and what this connection may do.
2. Open with one or two plain lines on what TrainerSuite will do for them, from `explain_trainersuite` (topic `overview`). No roadmap, no list of questions, no talk of levels.
3. Call `get_setup_status` and follow its steps in order. Say each step's `why` in one line.
4. If `offeringNeedsApp` is true, send its setup link first. Ask nothing about what they offer until they have finished there.

## Each step

- When `doneInChat` is true, do it here. When it is false, give the step's `link` and one line on what to do on that page, then go on when they come back.
- Ask one question at a time, the smallest one that unblocks the step. Offer a default and let them choose: "Most trainers start with one session type and a 10-session pack. Want that?"
- Only use names, prices, lengths and counts the trainer gave you. Never guess one.
- Adding clients with sessions left (`prepare_client_import`): if the trainer gave both a single-session price and a pack price, ask which one this client paid.
- A skipped step is fine. Remember it and come back to it at the end.
- Mention the "How sessions work" step at most once.
- For how anything works, call `explain_trainersuite` and keep to its facts: one or two lines and its page.

## Changes need the trainer's tap

- Tools that start with `prepare_` return a link. Nothing changes until the trainer taps Approve in TrainerSuite. A typed "yes" is not approval. Say it's done only after `get_action_status` says so.
- To correct a change you already prepared, call the same tool again with `replaces` set to the earlier `intentId`, so the old link stops working.

## End every answer with one next step

Unless the trainer is mid-task or said they're done. Book sessions only for clients already in TrainerSuite. If a tool says it needs a different level, say which in one line, as the tool explains.
