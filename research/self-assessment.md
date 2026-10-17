# Self-assessment: how AI-native is your SDLC?

> Part of [ai-native-sdlc-playbooks](../README.md). My own rubric, built from the four playbooks. Not endorsed by any of them.

Score each dimension from 0 to 5. Be honest: a blank or a low score is a finding, not a failure.

## The scale

| Score | Meaning |
|---|---|
| **0 · Absent** | No practice, no owner, no artifact |
| **1 · Ad hoc** | Happens in some teams, undocumented, depends on individuals |
| **2 · Defined** | A documented standard exists; adherence isn't enforced or measured |
| **3 · Enforced** | Mechanically enforced (blocks, not advises); exceptions need approval |
| **4 · Measured** | Enforced *and* instrumented; the control's own effectiveness is tracked |
| **5 · Self-improving** | Measured, and failures automatically feed back into the standard |

## The 16 dimensions

| # | Dimension | Comes from | Your score | Evidence |
|---|---|---|---|---|
| 1 | Intent is captured as a version-controlled artifact | Anthropic | | |
| 2 | Specs are checked against org policy while they're written | Anthropic | | |
| 3 | No code without an approved plan | Anthropic | | |
| 4 | Institutional knowledge is machine-readable (CLAUDE.md, skills, standards) | Anthropic, Atlassian | | |
| 5 | The agent's configuration is regression-tested (evals) | Anthropic | | |
| 6 | AI review happens before human review | Anthropic, Atlassian | | |
| 7 | An author can't approve their own code, agents included | Anthropic | | |
| 8 | Production gates need a named human approval | Anthropic | | |
| 9 | Agents have no standing production access | Anthropic | | |
| 10 | Full audit trail from intent to production | Anthropic, Atlassian | | |
| 11 | Context is connected and permission-aware | Atlassian | | |
| 12 | A measurement baseline exists *before* scaling | Atlassian | | |
| 13 | Qualitative developer signal is captured next to the numbers | Atlassian, Shopify | | |
| 14 | Generated code gets no review exemption | Google, Shopify | | |
| 15 | Dependencies are audited for hallucinated or outdated packages | Google | | |
| 16 | Data-privacy rules for prompts are published | Google | | |

**Total: ___ / 80**

## Reading your score

| Range | What it means | Do next |
|---|---|---|
| 0–20 | Pre-foundational | Context and measurement before any agent rollout |
| 21–40 | Foundations partial | Enforcement is likely the gap, not policy |
| 41–60 | Governed adoption is viable | Measurement and closing the loop |
| 61–80 | Mature | Review capacity and comprehension debt |

## The one question to ask first

Can you trace a production change back to the business intent that caused it, through a chain of timestamped, approved artifacts? If not, which link is missing?
