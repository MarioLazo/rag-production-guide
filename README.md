# Agentic CoE

**The practitioner's map for industrializing AI agents: the operating model, governance, and quality gates that move agents from pilots to production.**

Most enterprise AI programs don't fail on the technology. They fail because nothing around the technology is built to fund it, govern it, or scale it. Agents get deployed by whoever had budget, nobody can say how many are running, and the first real incident arrives before anyone has designed what happens next.

This repository holds the working tools for fixing that: the templates, scorecards, and checklists an Agentic Center of Excellence actually runs on.

> **Status: active, unevenly deep: deliberately.** Grounding (Layer 2) is the developed layer: failure modes, chunking, hybrid search, evaluation, cost engineering, and platform guides, built over six years of applied work. The other six layers are mapped but thinner. Tools are published when they're finished and field-tested, never as placeholders.

*This repository was previously `rag-production-guide`. The RAG material is intact under [`docs/`](docs/), it's now framed as one layer of a larger operating model rather than the whole subject. Old links redirect automatically.*

---

## Where this comes from

This work is drawn from:

- **623+ case studies and production implementations** reviewed and analyzed
- **65+ practitioner interviews**: Data Scientists, CTOs, CIOs, VPs, and the people actually running these systems
- Direct enterprise delivery experience across healthcare, financial services, telecom, and complex operations

The bias throughout is toward what survived contact with production. Where something is a hypothesis rather than an observed pattern, it says so.

### What this is not

- **Not a vendor playbook.** Platform guides exist ([Azure](docs/platform-guides/azure-ai-search.md), [AWS](docs/platform-guides/aws-bedrock.md), [GCP](docs/platform-guides/gcp-vertex-ai.md), [Databricks](docs/platform-guides/databricks-mosaic.md)) but the frameworks are deliberately vendor-agnostic.
- **Not a tutorial.** It assumes you've built something and hit the wall.
- **Not claimed to be current.** Pages carry a last-reviewed date and a confidence score. Trust them accordingly.
- **Not a playbook to follow.** The goal is first principles and honest lessons, including the ones that cost me something to learn.

The bias throughout is toward **how things fail and how you'd know**, rather than how to build them. Failure modes are more transferable than success stories, and far less written about.

---

## The tools

Each one stands alone. You don't need the others, or the book, to use any of them.

| Tool | What it does | Use it when |
|---|---|---|
| **[Agent Card](tools/agent-card.md)** | One-page spec every production agent needs, owner, risk tier, autonomy, escalation, kill switch | Before any agent reaches production |
| **[Pre-Flight Checklist](tools/pre-flight-checklist.md)** | Ten quality gates between "it works on my machine" and "it's live" | At the deployment gate, every time |
| **[BXT Scorecard](tools/bxt-scorecard.md)** | Scores use cases on Business value, eXecutability, and Trust, so funding goes to what can actually ship | Portfolio and roadmap planning |
| **[RAG Smell Test](cheatsheets/rag-smell-test.md)** | Fast diagnostic for whether a retrieval system is actually working | Reviewing someone else's RAG build |
| **[Danger Zones Checklist](cheatsheets/danger-zones-checklist.md)** | The failure modes worth checking before they find you | Design review |
| **[MCP Catalog](tools/mcp-catalog.md)** | Model Context Protocol servers organized by blast radius, with the governance each tier requires | Choosing what your agents can reach |
| **[Skills Catalog](tools/skills-catalog.md)** | Agent skills across Claude Code, Codex, Cursor, and Copilot, portability, context cost, and how to evaluate whether one actually helped | Choosing how your agents work |

### Reference

**[Agent Factory: Regulated Industries Edition](reference/agent-factory-regulated-industries.md)**: a curated 11,000-word index for finance, healthcare, and supply chain: agent frameworks and orchestration, vetted repos by vertical, MCP servers for finance and healthcare, ontologies and knowledge graphs, datasets, papers and associations, a regulatory reference guide, and deployment checklists.

Where domain expertise is critical and governance isn't optional, the hard part is knowing what's already been built and what's actually usable. This is that map.

---

## The framework spine

Nine frameworks, each with one job, sequenced by where they apply. Tools above map to the stages in bold.

| Stage | The question it answers | Framework |
|---|---|---|
| **Select** | Which use cases deserve funding? | **BXT**, Business value × eXecutability × Trust |
| **Diagnose** | Are we solving the right problem? | **The Meaning Gap**, Run × Reason |
| **Classify** | What are we actually building? | **Application Modes** → **Agent Patterns** → **Risk Tiers** |
| **Build** | How does it get assembled? | **The Seven-Layer Stack** |
| **Ship** | Is it ready? | **Production Gate Question** → **Pre-Flight Checklist** → **Agent Card** |
| **Operate** | Is it still working? | **The Three Drifts** |
| **Scale** | Where are we as an organization? | **Agent Factory Maturity Model** |

<sub><b>On the name.</b> This was called "Four Modes" until 2026-08-20, when it turned
out two different frameworks were sharing that name. <b>Application Modes</b> classifies
what the <i>AI</i> does: automating a task, augmenting a decision, generating an artifact,
orchestrating other agents. Its companion, <b>Five Modes</b>, classifies what the
<i>human</i> does as capability increases: Doing, Directing, Delegating, Designing,
Defining. Use both. One tells you what you are building; the other tells you what your job
is while it runs.</sub>

Two of these carry most of the weight:

**The Meaning Gap**: the distance between what a system optimizes and what the organization actually needs. Assessed on two axes: *Run* (can it execute reliably?) and *Reason* (is it reasoning about the right problem?). Most organizations measure only Run. The dangerous quadrant is **Precise but Wrong**, high operational confidence in a system solving the wrong problem. *Presented at the Toronto Machine Learning Summit.*

**The Production Gate Question**: *"If this agent gives the right answer to the wrong question, how would you know?"* Not rhetorical. It needs a specific operational answer before architecture work begins. The most dangerous response is a confident, fast one from a team that has never considered it.

---

## The courses

The CoE material answers *how does an organisation industrialise this*. Two
companion courses answer *how does a practitioner build one that survives*.

| | |
|---|---|
| **[From Vibe Coding to Agent Engineering](https://github.com/MarioLazo/vibe-coding-to-agent-engineering)** | Part 1, free. For people who have never measured an agent. Opens on an RCT where developers predicted they would be 24% faster, believed afterwards they had been 20% faster, and were measured **19% slower** |
| **[Agent Reliability Engineering](https://github.com/MarioLazo/agent-reliability)** | Part 2. **The 3pm Test.** Everything after it works. Six notebooks that run offline and deterministically in about ten seconds, with no API key and no dependencies |

Same bias as this repository: **how things fail, and how you would know.**

---

## The Agent Factory

If you've run manufacturing, supply chain, or distribution, you already have the mental model:

| Manufacturing | Agent Factory |
|---|---|
| Supply chains | Data pipelines |
| Assembly line | CI/CD |
| Defect rates | Hallucination rates |
| Safety protocols | Governance |

The value of the metaphor is that it makes the CFO conversation tractable. "How much will this cost?" becomes a unit-economics answer, cost per unit, quality threshold, and a trajectory, instead of a platform license discussion.

---

## Who this is for

- **CIOs, CDOs, and transformation leaders** who need to fund and govern agent programs, not just approve them
- **Architects and platform teams** standing up the CoE and the quality gates
- **Practitioners** who have production scar tissue and want to compare notes

---

## Stay with it

New tools, case breakdowns, and the thinking behind them get published as they're finished.

- **Follow along:** [LinkedIn](https://www.linkedin.com/in/mariolazo/), where new tools get announced
- **Go deeper:** the newsletter, for the reasoning behind each framework and what didn't work
- **Collaborate:** I'm actively looking for research collaboration and thought partnership, practitioners with production experience, researchers working on evaluation and governance, and people building community around this. Open an issue or reach out on LinkedIn.

---

## About

Maintained by **[Mario Lazo](https://github.com/MarioLazo)**, Data & AI transformation, enterprise AI strategy, and AI governance. Co-author of *AI Data Privacy and Protection* (Technics Publications, 2024). Currently writing a book on building the Agentic Center of Excellence.

---

## License

Licensed under **[CC BY 4.0](LICENSE)** ([plain-language summary](NOTICE.md)), use it, adapt it, build on it, including
commercially. **Attribution is required.**

> "Agentic CoE" by Mario Lazo (https://github.com/MarioLazo), licensed under CC BY 4.0.

Frameworks, curriculum, and written material here are original work. Copyright is
retained; the license grants reuse with credit, it does not transfer ownership.

*Previously MIT-licensed. Material published before 2026-08-15 remains available
under the terms it was released with.*
