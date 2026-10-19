### Olaoluwa Abiodun

AI engineer in Lagos (UTC+1). I build LLM systems that hold up on real data: assistants that work inside rules they can't override, extraction that keeps only what it can ground, and evals that tell me when a change made things worse.

Most of this I built for [Rentyx](https://rentyx.org), the property-management software I founded, where it runs in production. The repos below show the same patterns in code you can run: two rebuild core pieces of it on fictional data, and one works on real legal texts.

#### Public work

**[Reply Desk](https://github.com/AbiodunOlaoluwa/reply-desk)** ([try it](https://reply-desk-8rzb.onrender.com)): an LLM answers replies to sales outreach as structured drafts. Fourteen server-side rules check every draft; a draft that fails gets one rewrite, then a person. Signed webhooks are processed exactly once, opt-outs are saved first, and everything that sends has a kill switch. Next.js, Postgres, Claude. 51 tests.

**[Lead Engine](https://github.com/AbiodunOlaoluwa/lead-engine)** ([try it](https://lead-engine-yqxv.onrender.com)): messy directories in, a clean, scored contact list out. Grounded LLM extraction (every field must quote the page), entity resolution across sources (surname-first registers, Yoruba short forms), a resumable pipeline with a crash drill, evals scored against ground truth (100% precision on automatic merges, with the misses reported), and a plain-English ICP that drives the scoring. Python, FastAPI, Claude. 48 tests.

**[Cite Desk](https://github.com/AbiodunOlaoluwa/cite-desk)** ([try it](https://cite-desk.onrender.com)): ask the law, get the paragraph it came from. RAG over 11 official texts (outreach rules for the US, EU, UK, Canada and Nigeria, plus Lagos tenancy law): keyword and embedding search fused and re-ranked on CPU, citations to the exact paragraph, and a gate that refuses or flags weak matches. Evals on 90 labelled questions show what each stage adds: the right provision in the top 5 for 89% of questions, against 61% for keyword search. Python, FastAPI, Claude. 34 tests.

#### In production at Rentyx

- A WhatsApp assistant on Meta's Cloud API that handled 200 conversations in two weeks for $1.14 in model costs, and handed 19 of them to me at the right moment.
- A Claude copilot inside the product that answers questions about a property portfolio through typed tools, with spending limits.
- Scheduled AI agents that run prospecting, sending and follow-ups from runbooks, and refuse to act if their instructions fail an integrity check.
- The platform itself: payments through signed, duplicate-safe webhooks, a double-entry ledger, and 5,000+ automated tests.

#### How I build LLM systems

- **The model drafts; code decides.** Structured outputs, then server-side checks the model can't override.
- **Ground it or drop it.** Extracted facts carry evidence from the source, or they aren't stored.
- **Measure before changing.** Evals against labelled data, reported with their misses.
- **People own the consequential calls.** Sends, merges and money go through review or hard rules.
- **Know the cost.** Tokens and dollars recorded per call, with budgets.

#### Tools

Python, TypeScript, FastAPI, Next.js, Postgres, SQLite, Anthropic and OpenAI APIs (structured outputs, tool use, prompt caching), WhatsApp Cloud API, pytest, Vitest, Playwright, GitHub Actions, Claude Code.

#### Contact

[mate.olaoluwa@gmail.com](mailto:mate.olaoluwa@gmail.com) · [LinkedIn](https://linkedin.com/in/abiodunolaoluwa/)
