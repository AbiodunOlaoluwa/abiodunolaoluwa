### Olaoluwa Abiodun

I build automation that keeps working when the data gets messy: lead pipelines, AI reply desks, payments and the integrations between them.

I'm the founder of [Rentyx](https://rentyx.org), software that Nigerian property firms use to run rent, receipts, leases and tenant records. Everything below runs Rentyx's own sales and operations. I'm based in Lagos (UTC+1) and also work as a technical sourcer at Sourcing Sprints.

#### What I've built and run

**Lead Engine.** Sources business contacts from public directories and registers, enriches them across several providers, verifies every email before use, and catches the same person under a second number or a short form of their name. It scores each lead with points anyone can read and loads only approved records into the CRM. It has built a list of 11,000+ de-duplicated contacts, and bounces fell to 2.9% once verification went in.

**Reply Desk.** Answers WhatsApp replies in seconds using an LLM, inside server-side rules the model cannot override. Webhooks are signed and processed exactly once, drafts are structured and validated, and anyone who wants a call, asks about contracts or complains is handed to a person. Opt-outs are saved before anything else happens. It handled 200 conversations in two weeks for $1.14 in model costs.

**Rentyx.** A production SaaS with payments through signed, duplicate-safe webhooks, a double-entry ledger, an AI copilot with spending limits, and 5,000+ automated tests, with the unit suite gating every deploy.

The code for these is private because it touches real customer data. Versions that run on sample data are being prepared and will be pinned here.

#### How I build

- **Nothing happens twice.** Idempotency keys, resumable jobs with ledgers, and replay-safe webhooks.
- **Empty beats invented.** Missing data stays missing. Nothing is guessed.
- **AI drafts, rules check, people decide.** Model output passes server-side checks, and sensitive cases wait for a person.
- **Every sender has an off switch.** Each one has a kill switch, a daily cap and a dry-run mode.

#### Tools

TypeScript, Next.js, Node.js, Python, Postgres, Prisma, Redis and BullMQ, Vercel, WhatsApp Cloud API, OpenAI and Anthropic APIs, Notion API, Resend, Flutterwave, Vitest, Playwright.

#### Get in touch

I take on a small number of automation projects. Email is the fastest way to reach me: [mate.olaoluwa@gmail.com](mailto:mate.olaoluwa@gmail.com). You can also find me on [LinkedIn](https://linkedin.com/in/abiodunolaoluwa/).
