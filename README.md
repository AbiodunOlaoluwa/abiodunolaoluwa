### Olaoluwa Abiodun

I'm an engineer in Lagos (UTC+1). I like building LLM features that have to behave on real data, and I spend most of my time on the boring parts that make them trustworthy: the checks around the model and the tests that tell me when a change made things worse.

Most of it started at [Rentyx](https://rentyx.org), a property-management platform I built for landlords and agents in Nigeria, where it runs in production. One firm is fully imported and running on a pilot, and two others are close to starting theirs. The three repos below rebuild the core pieces so you can run them yourself: two on fictional data, one on real legal texts.

#### Public work

**[Reply Desk](https://github.com/AbiodunOlaoluwa/reply-desk)** ([try it](https://reply-desk-8rzb.onrender.com)): an LLM drafts replies to sales outreach, and fourteen checks on the server decide whether a draft can go out. A draft that fails gets one rewrite, then a person takes over. Next.js, Postgres, Claude, 51 tests.

**[Lead Engine](https://github.com/AbiodunOlaoluwa/lead-engine)** ([try it](https://lead-engine-yqxv.onrender.com)): takes public directory pages and turns them into a scored contact list. Every extracted field has to quote the page it came from, or it isn't stored. It matches the same firm across sources, including registers that write surname first and Yoruba short forms of names, and it only merges on its own when it's sure: in the evals, none of those automatic merges were wrong, and the uncertain ones go to review. A run that crashes picks up where it left off, and there's a drill to prove it. Python, FastAPI, Claude, 48 tests.

**[Cite Desk](https://github.com/AbiodunOlaoluwa/cite-desk)** ([try it](https://cite-desk.onrender.com)): answers questions about 11 official texts (outreach rules for the US, EU, UK, Canada and Nigeria, plus Lagos tenancy law) and cites the exact paragraph, or flags a weak match instead of guessing. On 90 labelled questions, keyword search alone found the right provision in the top 5 for 61% of them; adding embeddings and re-ranking (on CPU) took it to 89%. Python, FastAPI, Claude, 34 tests.

#### Running in production at Rentyx

- A WhatsApp assistant on Meta's Cloud API that handled 200 conversations in two weeks and handed 19 of them to me.
- A Claude copilot inside the product that answers questions about a property portfolio through typed tools, with spending limits.
- Scheduled agents that run prospecting, sending and follow-ups from runbooks, and refuse to act if their instructions fail an integrity check.
- The platform itself: payments through signed webhooks that can't be processed twice, a double-entry ledger, and 5,000+ automated tests.

#### Things that broke, and what changed

- One day Meta held back half our WhatsApp sends. The cause was where the numbers came from, not our account, so the sender now goes to the cleanest sources first and reports attempts against delivered messages.
- The assistant's playbook page grew past the size the loader accepts, and it quietly ran on an older copy for a day. It now reports which rules are live and why a page was rejected.
- A firm's "Good afternoon" once got a reply asking about their rent records. Automatic greetings are now skipped before the model sees them.

#### Tools

Python, TypeScript, FastAPI, Next.js, Postgres, SQLite, the Anthropic and OpenAI APIs, the WhatsApp Cloud API, pytest, Vitest, Playwright, GitHub Actions and Claude Code.

#### Contact

[mate.olaoluwa@gmail.com](mailto:mate.olaoluwa@gmail.com) · [LinkedIn](https://linkedin.com/in/abiodunolaoluwa/)
