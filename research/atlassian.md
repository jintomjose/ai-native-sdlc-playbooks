# Atlassian — The AI SDLC Transformation Playbook

> Notes by Jinto Jose on a public source. Summarised for study; framework, figures and wording belong to the publisher. Part of [ai-native-sdlc-playbooks](../README.md).


**Source:** Atlassian blog, "The AI SDLC transformation playbook," 1 October 2026. Author: Matthew Canham, Senior Group Product Manager, AI. Informed by Atlassian's own internal transformation and collaborative learnings from top engineering organisations.
**Document type:** Vendor playbook.
**Organising principle:** *Platform foundations first; workflow shifts stand on them.*

## Core thesis

The AI-native SDLC goes far beyond having developers adopt coding agents. As less time is spent writing code by hand, **coding itself evolves from a synchronous, single-threaded task into an asynchronous, multi-threaded one**. This exposes the processes *before* and *after* code — planning, design, review, and maintenance — as the largest bottlenecks and opportunities. Team collaboration becomes an even greater bottleneck as the rate of work accelerates.

To transform the entire SDLC, organisations must **simultaneously** invest in platform foundations (context and measurement) and shift from traditional SDLC processes to AI-native ways of working. Together these become the modern software factory: faster, more autonomous, more event-driven, and reshaped around critical human judgement.

## The seven pillars

**Five workflow shifts:** Planning · Design · Development · Review · Maintenance
**Two platform foundations:** Context graph · Measurement

Platform investments and new SDLC workflows are **mutually dependent**:
- New SDLC workflows only work effectively when supported by powerful enterprise context and feedback loops
- Reliable context and measurement are only possible when metadata from new SDLC workflows is consistently captured and accessible
- Developer–agent interactions themselves become a new form of context, making the whole workflow smarter over time

**Systems of record tie these pillars together, wherever development happens.** They support humans in applying critical judgement — planning, evolving designs, aligning on goals, acting on customer feedback, responsibly shipping code. Agents rely on those same systems for the structured, connected data that lets people and AI work together.

## Traditional vs AI-native, by workflow

| Workflow | Traditional SDLC | AI-native SDLC | Atlassian approach |
|---|---|---|---|
| **Planning** | Requirements defined manually with incomplete knowledge of the code, causing downstream problems and significant time aligning teams | AI synthesises customer needs and code context into requirements, captured as versioned spec files in the repo | Teamwork Graph pulls context from across the org (Jira, Confluence, third-party). Jira Product Discovery evaluates ideas against customer feedback; Jira turns them into connected, agent-ready tasks |
| **Design** | Static mockups and manually written briefs handed off to developers for every change | Agent sessions guided by standards stored alongside the code. Live prototypes replace static frames; designers contribute UI code and bug fixes directly | Design standards grounded in the Teamwork Graph. Agents in Jira let designers and PMs ship UI updates and bug fixes directly; Loom video feedback drives AI revisions |
| **Development** | Developers pick up tasks, research and plan, then write code. Velocity and quality bottlenecked by individual throughput and skill | Developers work with agents for planning, generating and testing code. Quality depends on AI context; velocity relies on effective agent orchestration | Coding agents use the Teamwork Graph CLI to combine code and organisational context. Each session's decisions flow back to the graph |
| **Review** | Humans manually review every change, standards inconsistent, feedback slow | AI reviews changes first, applying shared standards across new and existing code | AI Reviewer and third-party coding agents validate changes across teams and services against dependencies mapped in the Teamwork Graph. Standards centrally defined, governance auditable in the system of record |
| **Maintenance** | Incidents and errors manually triaged and resolved; KTLO and reliability work deprioritised due to limited capacity | Agents help triage, resolve and document routine work, escalating only when needed. Teams shift capacity toward new capabilities | Jira Service Management automates incident triage. Agents trace impact across teams via the graph. Governed agent loops in Jira scan for well-defined work and turn backlog items into pull requests |

**Note:** Atlassian has **no standalone Test workflow**. Verification is folded into Development and Review. This is a stated position, not an omission.

## Platform foundation 1 — Context graph

### Why it matters
AI agents may have the intelligence to write, refactor and review code, but they face the same challenge development teams always have: making sense of the context surrounding each task. Humans accumulate that context over years. **Agents need the same context supplied to them for every task** in order to produce high-quality output.

### What good looks like
A context graph containing interconnected data spanning:
- Code repositories
- Work items
- Documentation
- Technical standards
- Meeting recordings
- Chat

This data must be accessible to both humans and agents through a **permissions-aware layer**, so AI acts as a knowledgeable teammate rather than guessing at the shape of the system.

### Atlassian approach — Teamwork Graph
- Combines data from **50+ connected sources** with Jira, Confluence and Loom
- A living map of work, code, people, decisions and dependencies
- **Governance and permissions enforced at the data layer** — what a person can see is exactly what an agent can act on
- Reachable from Atlassian apps, terminals, IDEs, or any agent surface via **MCP or CLI**
- Agent and human activity flows back into the graph, so the system of record maintains itself autonomously and context compounds every time the graph is used

### Published figures
> In internal benchmarks, agents with access to the Teamwork Graph delivered **44% more accurate results** while using **48% fewer tokens** compared to agents operating without it. Because every agent run generates more structured context, each subsequent run becomes higher quality and lower cost.

## Platform foundation 2 — Measurement

### Why it matters
Amid rapid change, it is difficult to know what is working without data. With the right feedback loops and metrics, organisations can track the impact of AI tools and workflows alongside cost, productivity and ROI, while enabling teams to continuously improve.

### What good looks like
Work and agent activity must be **observable and measurable**. By integrating data from systems of record, third-party APIs, and agent sessions, organisations build real-time visibility into AI effectiveness, impact and ROI — paired with **qualitative signals from the developers doing the work**.

### Atlassian approach
Atlassian uses **DX** to measure and report on how AI is impacting the SDLC and overall productivity. DX combines quantitative data from tools like Jira, Cursor and Claude Code with qualitative developer feedback. Analysing and benchmarking this dataset helps set targets, guide investment, and ensure organisational excellence.

## Workflow detail — friction, shift, approach

### Planning
- **Friction:** Planning relies on manual effort and committee-driven consensus. PMs and analysts spend weeks drafting requirements and aligning stakeholders. Because those defining the work have incomplete knowledge of the codebase, specifications miss architectural constraints and technical debt, causing friction and costly rework during implementation.
- **Shift:** Agents synthesise customer needs and organisational context into requirements and specs, drafting from a real understanding of both the business and the codebase. Human teams focus on applying judgement: refining, deciding, ensuring plans are grounded in reality before engineering begins.

### Design
- **Friction:** Design is an isolated phase between requirements gathering and implementation. Designers spend significant time on static mockups and briefs, then hand off. Because designers lack direct access to the codebase, even minor visual tweaks require developer intervention — recurring bottlenecks that drag out release timelines.
- **Shift:** Design becomes a continuous thread integrated with planning and development rather than a distinct step. AI-assisted tooling lets designers build live interactive prototypes, generate UI code, and commit bug fixes independently.

### Development
- **Friction:** Work is scoped and logged in backlogs before any code is written. Code quality is constrained by individual developer skill and domain expertise; velocity is bounded by human throughput.
- **Shift:** Development becomes fluid and automated. Tasks are spawned from operational signals and captured automatically as work happens. **Code quality is no longer determined by raw developer skill — it depends on the quality of context supplied to AI.** Velocity depends on effective agent orchestration.
- **Published figure:** AI-native development processes at Atlassian have **cut issue cycle time by nearly half, from 11.5 days to 6.7 days** — attributed to tighter feedback loops, faster reviews, and agents handling routine work in parallel.

### Review
- **Friction:** Manual reviews create persistent bottlenecks and slow feedback cycles: PRs sit unattended for hours or days, and standards vary in scrutiny from reviewer to reviewer. Code is validated for correctness, but intent and requirements aren't validated until staging or production.
- **Shift:** Agents move onto the critical path for review, so PRs move within **minutes instead of days**. Engineering standards are encoded into shared context, enabling AI to continuously apply them across new and existing code. Human reviewers still hold the judgement call, but arrive better informed, with routine feedback already handled.

### Maintenance
- **Friction:** Maintenance is reactive and labour-intensive. Engineers manually triage production errors, analyse stack traces, route incident tickets. Because capacity is finite, KTLO work and reliability improvements are routinely deprioritised in favour of features, leading to accumulated technical debt and operational risk.
- **Shift:** Maintenance becomes a proactive, automated operating model. Agents classify incoming errors and generate root cause analyses before humans engage, escalating only when needed. Routine maintenance, dependency updates and recurring fixes are delegated to autonomous coding agents.
- **Published figure:** Agent loops in Jira **automatically resolve 51% of potential vulnerabilities** at Atlassian.
- **Audit note:** Because every loop writes its actions back into the graph as it runs, the system of record captures a live audit trail of what agents did and why.

## Navigating change — five moves for engineering leaders

AI-native SDLC is an **operating-model transformation**. It changes how work is scoped, how quality is achieved, how decisions get made, and how teams learn from every release. Leaders who treat it primarily as a procurement exercise — selecting agents, licensing models, adopting a new IDE — will see incremental gains at best.

1. **Anchor on context.** Treat connected, permissioned organisational context as the foundation everything else rests on. Without it, every workflow shift underperforms.
2. **Invest in measurement early.** Establish quantitative and qualitative feedback loops *before* scaling adoption, so you can distinguish real productivity gains from hype.
3. **Choose a starting workflow.** Pick the SDLC stage where AI-native ways of working will unlock the most value for your teams and go deep before broadening.
4. **Preserve accountability.** Keep humans clearly in charge of judgement, quality and governance while AI handles execution and enforcement. Governed agent loops — scoped, standards-aware, and captured in systems of record — are the ones that scale.
5. **Build the operating model, not just the toolkit.** Update rituals, roles and success metrics alongside the tooling; the biggest gains come from the changes AI enables in how teams work together.

## Published figures summary

| Metric | Value | Context |
|---|---|---|
| Agent accuracy with context graph | +44% | Internal benchmark vs. agents without graph access |
| Token consumption with context graph | −48% | Same benchmark |
| Issue cycle time | 11.5 → 6.7 days | Atlassian internal, AI-native processes |
| Vulnerabilities auto-resolved | 51% | Agent loops in Jira |

Related research referenced: *The Agentic Pivot* — a 2026 survey of 1,000+ software professionals on the state of AI-native engineering.


