# Shopify: AI-first engineering

> Notes by Jinto Jose on a public source. Summarised for study; practices, figures and quotes belong to Shopify as documented by Bessemer Venture Partners. Part of [ai-native-sdlc-playbooks](../README.md).

**Source:** Bessemer Venture Partners, [Inside Shopify's AI-first engineering playbook](https://www.bvp.com/atlas/inside-shopifys-ai-first-engineering-playbook), detailing Farhan Thawar, Head of Engineering, Shopify. 2026.
**Document type:** Case study. Not a framework: a five-year operating story of what worked, what broke, and what it cost.
**Why it's here:** it is the only one of the four written by a company *using* AI across its own SDLC rather than selling it.

## Five years in, not five months

Shopify started with GitHub Copilot in 2021, before ChatGPT existed, and has since adopted AI across all functions. In 2026 the focus is agentic harnesses.

**Thesis.** The opportunity is not full automation that removes human judgement. It is giving every employee superpowers: engineers testing 10 approaches instead of 2, salespeople building their own dashboards, leaders deciding with AI-powered analysis in minutes.

## 1. Core infrastructure: centralise the plumbing, not the choice

| Layer | What it does |
|---|---|
| **LLM proxy** | Bulk token purchasing, usage tracking per team and project, spend alerts |
| **MCP servers** | Unified access to company data: Salesforce, GitHub, G Suite, Slack |
| **Quick deployment** | Drag-and-drop internal app deployment |

**Multi-tool philosophy:** "In the world of AI, we don't know yet what's gonna win." Engineering uses Cursor, Claude Code, GitHub Copilot, OpenAI Codex and Gemini Jules. Non-engineering uses Gumloop workflows and an internal LibreChat. The enablement layer is centralised; the choice of assistant is not.

## 2. Cultural adoption: "make it look easy"

Four tactics, all pull rather than push:
- **Nudging over forcing:** showcase what is possible rather than mandate usage
- **Leadership by example:** leaders visibly use AI in their own work
- **Prompt library:** a shared home for workflows that work, so wins spread
- **Hack Days:** twice a year, purely for experimentation

**Accountability without punishment.** Questions on "AI reflexiveness" are part of twice-yearly impact reviews. No punishment for non-adoption, only visibility on usage.

## 3. Quality and security

"We're building the infrastructure for commerce; we need to understand it."
- Extensive automated testing of existing infrastructure
- Human PR review still required for production code ("but this will change")
- **Reversion rates unchanged despite increased output**: more code shipped, no more of it came back
- AI used as a pairing partner for vulnerability detection and fuzzing, not only for generating code

## 4. Results

- **~20% overall productivity increase**, called a conservative estimate. Thawar has since [said on X](https://x.com/fnthawar/status/2036033400012689631) that he made up the 20% figure, while noting P90 engineers see 10x or more. Treat it as a gut number.
- More prototyping and exploration (10 approaches instead of 2)
- Higher-fidelity deliverables from designers and PMs
- Sales, finance and HR building "N-of-1" software for themselves
- Designers shipping interactive prototypes instead of static mockups

Four of the five gains sit outside engineering. The productivity story is a company story.

## 5. Two lessons learned the hard way

| Lesson | What happened | The fix |
|---|---|---|
| Wrong tool for non-engineers | Cursor spread too far outside R&D: expensive and the wrong UX for people who don't code | Workflow tools for non-technical teams. Match the tool to the user, not to the enthusiast who introduced it |
| Unlimited token usage | One person could run up a five-figure weekly token bill | Max iteration depth on agent loops plus spend alerts, but deliberately no hard limits |

## 6. Two problems they have not solved

- **The review bottleneck.** Humans still review all production code. As generation speeds up, review becomes the constraint.
- **Comprehension debt.** "The brain is a muscle. If you stop using it, it atrophies." The risk is a team that ships more than it understands.

Four guardrails against comprehension debt:
1. Engineers must understand systems 2–3 layers below their work
2. AI should reduce toil, not thinking
3. Use AI to accelerate learning, not replace understanding
4. The Formula One mindset: the best drivers understand the engine

## 7. 2026: agentic harnesses

"If you don't figure out how to harness agents in 2026, you will be behind."
- **Breadth: parallel agents.** Ten agents at once, then a single human review and merge. Scales output, and pushes the whole load onto the review gate.
- **Depth: sequential critique loops.** Reasoning models interrogating their own answers across sessions of 45 minutes or more. Trades wall-clock time for rigour.

Both bet on the same thing: the scarce resource is no longer generation. It is review, judgement and comprehension.

## What to take from it

- Enable aggressively. Protect comprehension vigilantly.
- Centralise the plumbing (proxy, data access, deployment). Decentralise tool choice.
- Nudge, showcase and measure. Don't mandate.
- Match the tool to the user.
- Use iteration-depth limits and spend alerts rather than hard caps.
- Treat review capacity and comprehension as the two things that break first.
