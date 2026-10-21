# TrainerSuite for Claude

TrainerSuite is business software for independent personal trainers: clients, schedule,
packages and sessions left, payments and business numbers. Less admin. More training.

This plugin connects Claude to your TrainerSuite account and adds four short skills that help
Claude work the way a trainer does. Ask in plain words:

- "Help me set up TrainerSuite"
- "Who's on my schedule today?"
- "What needs me this week?"
- "Which clients are running low on sessions?"
- "Send Taylor a payment request for her next pack"

You need a TrainerSuite account. You can create one when you connect.

## What's inside

| Part | What it does |
| --- | --- |
| `.mcp.json` | Connects to TrainerSuite's MCP server at `https://mcp.trainersuite.app` |
| `skills/get-started` | Walks a new trainer through setup, one step at a time |
| `skills/weekly-check-in` | Sessions to confirm, clients low or owing, and the week ahead |
| `skills/get-paid` | Who owes or is low, payment requests and recording a payment |
| `skills/set-up-my-offering` | Session types and packages |

The skills are plain instructions for Claude. The plugin has no scripts, hooks or local
programs, and installs nothing on your computer.

## How you stay in control

When you connect, you sign in to TrainerSuite and pick one level:

- **Read**: look only.
- **Draft**: Claude prepares changes; nothing happens until you tap Approve in TrainerSuite.
- **Write**: Claude can also book, move and cancel sessions when you ask.

Claude can't charge a card or move money. A payment request emails your client a link; the
client chooses whether to pay on TrainerSuite's own page. Recording a payment only logs one you
already received. You can disconnect at any time in TrainerSuite under Settings › Connected apps.

## Data and privacy

The plugin talks to one place: TrainerSuite's server at `https://mcp.trainersuite.app`, over
HTTPS, signed in with your own TrainerSuite account (OAuth). Claude sends that server the
requests you make (for example a client's name or a session time) and gets back your
TrainerSuite data needed to answer: your business, schedule, clients, sessions left, payments
and business numbers. Nothing is sent anywhere else.

- Privacy policy: https://trainersuite.app/privacy
- Terms: https://trainersuite.app/terms
- How to use TrainerSuite with an AI assistant: https://trainersuite.app/learn/ai-assistant
- Support: https://trainersuite.app/support

## License

MIT. See `LICENSE`.
