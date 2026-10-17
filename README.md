# AI-native SDLC: four playbooks compared

**Anthropic · Atlassian · Google Cloud · Shopify**: what each says about the software development lifecycle once agents write most of the code, where they agree, where they genuinely disagree, and how much of it is actually measured.

👉 **Scroll the visual version:** https://jintomjose.github.io/ai-native-sdlc-playbooks/
📄 **Swipeable PDF (LinkedIn carousel):** [docs/four-ai-sdlc-playbooks.pdf](docs/four-ai-sdlc-playbooks.pdf)
📚 **Full notes per source:** [research/](research/)
🧭 **Score your own organisation:** [research/self-assessment.md](research/self-assessment.md)

> Personal research by [Jinto Jose](https://www.linkedin.com/in/jintojose). My own reading of public material. It does not represent the view of my employer, and none of the four companies has reviewed or endorsed it. All frameworks, figures and quotes belong to their publishers (see [Sources](#sources)).

---

## The one-line summary

**Nobody disagrees about the destination.** They disagree about where the source of truth lives, how hard the limits should be, and how much to standardise the tools.

## Four sources, four altitudes

They are not four answers to one question. They answer four different questions.

| | Anthropic | Atlassian | Google Cloud | Shopify |
|---|---|---|---|---|
| **Document** | The AI-Native SDLC Playbook (Aug 2026) | The AI SDLC Transformation Playbook (Oct 2026) | AI in the SDLC (use-case page, Sep 2026) | AI-first engineering (Bessemer case study, 2026) |
| **Question it answers** | What artifact does each stage commit? | What must the platform provide? | What can AI do in each phase? | What happened when a whole company went AI-first? |
| **Shape** | 6 stages, each ending in a committed file; skills advise, hooks enforce | 5 workflow shifts on 2 platform foundations (context graph, measurement) | Capability map across 5 phases, plus risks and best practices | 5-year operating story: enablement layer, culture, lessons |
| **Type** | Vendor playbook | Vendor playbook | Marketing page | Case study |

## Five things all four agree on

1. **Code generation is no longer the constraint.** The bottleneck moved to the work around the code: planning, review, maintenance.
2. **Human review becomes the binding constraint.** Anthropic, Atlassian and Shopify reach this independently. Google names it as a risk.
3. **Context quality decides output quality.** Not model choice. What the agent is told about your systems is the differentiator.
4. **Humans stay accountable for judgement.** Agents execute and enforce. People decide, approve and own.
5. **It is an operating-model change, not a tool purchase.** Explicit for Atlassian and Shopify, implied by Anthropic, not stated by Google.

When organisations competing for the same budget agree this precisely, the agreement is the finding.

## The same lifecycle, four treatments

| Stage | Anthropic | Atlassian | Google Cloud | Shopify |
|---|---|---|---|---|
| **Plan** | `intent.md` committed by the person with the problem | AI drafts specs from code + customer context | NLP turns feedback into requirements | Non-engineers build their own tools |
| **Design** | `spec.md`, constrained by org skills | A continuous thread; designers ship UI code | Pattern and compliance recommendations | Designers ship prototypes, not mockups |
| **Build** | `plan.md` approved before any code | Agents + context graph; context compounds | Scaffolding and boilerplate absorbed | Multi-tool by choice; no single standard |
| **Test** | Feedback loop + continuous evals (20–50 real tasks) | *Folded into development and review, on purpose* | Generated edge cases and regression suites | Automated testing; reversion rates unchanged |
| **Deploy** | Layered AI review; hooks as approval gates; agent can't approve its own code | AI reviews first; standards enforced centrally | Cloud Deploy, release notes | Human PR review still mandatory |
| **Maintain** | Monitoring breaches write the next `intent.md` | Agents triage; loops resolve routine work | ML anomaly detection, auto-rollback | Comprehension debt as the live risk |

## Three real disagreements

Not differences in emphasis. Places where following one source means not following another.

**1. Where does the source of truth live?**
Anthropic: in the repo. Markdown artifacts are authoritative and the commit history is the audit trail.
Atlassian: in the graph. One connected context layer across tools is authoritative, and the repo is one input.
*An architecture decision, and expensive to reverse.*

**2. One standard tool, or many?**
Anthropic and Atlassian: a governed, standardised agent surface.
Shopify: deliberately multi-tool, because "we don't know yet what's gonna win." Centralise the plumbing, not the choice.
*Governance appetite decides this, not engineering preference.*

**3. How hard are the limits?**
Anthropic: hooks that block, managed settings engineers can't override.
Google: policy and practice guidance, no enforcement mechanism.
Shopify: iteration-depth limits and spend alerts, deliberately no hard caps, so experimentation survives.
*A regulated organisation will land closer to Anthropic. Know what it costs in developer friction.*

## How much is measured, and how much is asserted

| Source | What it publishes | Caveat |
|---|---|---|
| **Atlassian** | +44% agent accuracy and −48% tokens with the context graph · issue cycle time 11.5 → 6.7 days · 51% of potential vulnerabilities auto-resolved | Self-reported internal benchmarks, no methodology published |
| **Shopify** | ~20% overall productivity · reversion rates unchanged as output rose | Farhan Thawar has since [said on X](https://x.com/fnthawar/status/2036033400012689631) that the 20% was his own rough number |
| **Anthropic** | No outcome figures. A leading/lagging indicator per play instead | Tells you what to measure, not what they measured |
| **Google Cloud** | No figures, no customers, no research cited | Six benefits asserted without evidence |

**Not one of the four publishes a methodology.** Every number is a vendor claim: directional, not a benchmark to commit to.

## Governance: what each gives a regulated organisation

Scored on what you'd need to show an auditor. ●●● = explicit, implementable guidance.

| Dimension | Anthropic | Atlassian | Google Cloud | Shopify |
|---|---|---|---|---|
| Audit trail | ●●● | ●●● | ●○○ | ●○○ |
| Enforceable gates (block, not advise) | ●●● | ●●○ | ●○○ | ●○○ |
| Separation of duties | ●●● | ●●● | ●○○ | ●●○ |
| Data residency / tenancy controls | ●●● | ●●○ | ●●○ | ●○○ |
| Measurement and reporting | ●●○ | ●●● | ●○○ | ●●○ |
| Change-management fit | ●●● | ●●○ | ●○○ | ●○○ |

*My reading of the published material, not a vendor assessment.*

## What to take from each

| Source | Take this |
|---|---|
| **Anthropic** | The artifact chain and the enforcement model. Every stage commits a file the next stage reads. Skills advise, hooks block. This is the part that survives contact with auditors. |
| **Atlassian** | The operating model and measurement discipline. Context is a platform investment, not a per-team effort. Measure before you scale. |
| **Google Cloud** | The risk framing and the review policy. Generated code earns no exemption from peer review or security scanning. |
| **Shopify** | The adoption mechanics. Nudge, showcase, make usage visible. Match the tool to the user. Protect comprehension. |

## A composite approach

Taking the strongest element from each, in the order things have to exist:

1. **Context and artifacts.** One source of truth per artifact. Start the committed-artifact chain.
2. **Measurement.** Quantitative and qualitative baselines *before* scaling adoption.
3. **Review policy.** Generated code gets no exemption.
4. **Enforceable gates.** Hooks and managed settings for the controls that must always hold.
5. **Adoption mechanics.** Nudge and make usage visible. No mandate, no punishment.

## The three decisions that are yours to make

1. Repo or platform graph as your source of truth, and for which artifacts?
2. One standardised agent surface, or many tools under a common enablement layer?
3. Hard blocking gates, or alerts and caps that keep experimentation alive?

Want to see where you stand? Use the 16-question [self-assessment](research/self-assessment.md).

---

## What's in this repo

| Path | What it is |
|---|---|
| [`docs/index.html`](docs/index.html) | The scrollable visual version (served on GitHub Pages) |
| [`docs/four-ai-sdlc-playbooks.pdf`](docs/four-ai-sdlc-playbooks.pdf) | Swipeable carousel PDF |
| [`research/anthropic.md`](research/anthropic.md) | Notes on Anthropic's playbook: stages, artifact chain, governance layers |
| [`research/atlassian.md`](research/atlassian.md) | Notes on Atlassian's playbook: seven pillars, figures, five moves for leaders |
| [`research/google-cloud.md`](research/google-cloud.md) | Notes on Google Cloud's page: phases, named risks, best practices |
| [`research/shopify.md`](research/shopify.md) | Notes on Shopify's AI-first engineering story |
| [`research/self-assessment.md`](research/self-assessment.md) | 16-dimension scoring rubric (0–5) to find your own gaps |

Looking for the templates (`intent.md`, `spec.md`, `plan.md`, `REVIEW.md`, evals)? They live in my working example: **[mini-software-factory](https://github.com/jintomjose/mini-software-factory)**.

## Sources

| Source | Document | Date |
|---|---|---|
| Anthropic | [The AI-native SDLC playbook](https://claude.com/blog/the-ai-native-sdlc-playbook) (Louis Claxton) | 21 Aug 2026 |
| Atlassian | [The AI SDLC transformation playbook](https://www.atlassian.com/blog/ai-at-work/ai-sdlc-transformation-playbook) (Matthew Canham) | 1 Oct 2026 |
| Google Cloud | [AI in the Software Development Life Cycle](https://cloud.google.com/use-cases/ai-sdlc) | updated 21 Sep 2026 |
| Shopify | [Inside Shopify's AI-first engineering playbook](https://www.bvp.com/atlas/inside-shopifys-ai-first-engineering-playbook) (Bessemer Venture Partners, with Farhan Thawar) | 2026 |

The synthesis, the comparison tables, the governance scoring and the self-assessment are my own analysis, not the companies'. Corrections welcome: open an issue.

Licence: text and visuals [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Quote freely with a link back.
