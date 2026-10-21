---
name: get-paid
description: Helps the trainer get paid, from who owes or is running low to sending a payment request or recording a payment a client already made. Use when the trainer asks who owes them, who to follow up with, to send a payment request, or to record a payment.
---

# Get paid

Help the trainer see who owes them and get paid. Every change waits for the trainer's tap in TrainerSuite.

## Who owes or is low

1. `list_clients_needing_attention`: who owes sessions, who is low and who has open payment requests.
2. Name each client with the reason in a few words. For one client, `get_client_summary` shows sessions left and owed, open requests and their usual package.
3. If the trainer hasn't said which client, ask.

## Send a payment request

- `prepare_payment_request` with a package (`packageId` from `get_setup_status`) at its listed price, or an amount with a few plain words on what it's for.
- If the client has a usual package, offer it as the default: "Her usual is the 10-session pack. Send that?" Otherwise ask which package or amount.
- If the client already has an open request, say so and ask before sending another.
- Add a message or a due date only if the trainer gave one.
- Say what happens after the tap: the client gets a link to pay, in their client app and by email. Nothing is charged; the client chooses whether to pay.

## Record a payment they already made

- `prepare_record_payment` for cash, Venmo, a check and the like: the amount and method as the trainer said them, and the package or sessions it pays for.
- If the tool lists the trainer's payment methods, ask which one. If it asks whether this pays an open request, ask the trainer.

## Rules

- You can't charge a card or move money. If asked to, say so and offer, in words, a payment request or recording a payment they already made. Prepare either only after the trainer picks one.
- Never invent an amount: use what the trainer said or a package's listed price.
- Each tool returns a link. Nothing changes until the trainer taps Approve in TrainerSuite. A typed "yes" is not approval. Say it's done only after `get_action_status` says so.
- To correct one you already prepared, call the same tool again with `replaces` set to the earlier `intentId`.
