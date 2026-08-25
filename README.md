# Agentic CoE

*The operating model, governance, and quality gates that move agents from pilots to production.*

<br>

---

<br>

**This is in beta and built in the open.** It is a working reference rather than a
finished standard: sections are added and revised as engagements teach me something
worth writing down, and anything still thin is marked rather than quietly padded.

<br>
<br>

## Most enterprise AI programs do not fail on the technology

They fail because nothing around the technology is built to fund it, govern it,
or scale it.

Agents get deployed by whoever had budget.

Nobody can say how many are running.

And the first real incident arrives before anyone has designed what happens
next.

<br>

That is not a model problem. It is an **operating model** problem, and it is
the one nobody assigns an owner.

<br>
<br>

## Six years of asking one question

> *"If this agent gives the right answer to the wrong question, how would you know?"*

Not rhetorical. It needs a specific operational answer **before** architecture
work begins.

The most dangerous response is a confident, fast one from a team that has never
considered it.

<br>

This repository is what came out of asking it repeatedly:

- **623+** case studies and production implementations reviewed
- **65+** practitioner interviews with the people actually running these systems
- Direct delivery across healthcare, financial services, telecom, and complex operations

The bias throughout is toward *how things fail and how you would know*, rather
than how to build them. **Failure modes transfer. Success stories mostly do
not.**

<br>
<br>

## The tools

Each stands alone. You need none of the others to use any of them.

<br>

**1 · [Agent Card](tools/agent-card.md)**
One page every production agent needs: owner, risk tier, autonomy, escalation,
kill switch.
*Use it before any agent reaches production.*

**2 · [Pre-Flight Checklist](tools/pre-flight-checklist.md)**
Ten gates between "it works on my machine" and "it is live."
*Use it at the deployment gate, every time.*

**3 · [BXT Scorecard](tools/bxt-scorecard.md)**
Scores use cases on Business value, eXecutability and Trust, so funding goes to
what can actually ship.
*Use it in portfolio and roadmap planning.*

**4 · [RAG Smell Test](cheatsheets/rag-smell-test.md)**
Fast diagnostic for whether a retrieval system is actually working.
*Use it when reviewing someone else's build.*

**5 · [Danger Zones Checklist](cheatsheets/danger-zones-checklist.md)**
The failure modes worth checking before they find you.
*Use it in design review.*

**6 · [MCP Catalog](tools/mcp-catalog.md)**
MCP servers organised by blast radius, with the governance each tier requires.
*Use it when choosing what your agents can reach.*

**7 · [Skills Catalog](tools/skills-catalog.md)**
Agent skills across four harnesses: portability, context cost, and how to
evaluate whether one actually helped.
*Use it when choosing how your agents work.*

<br>

Tools are published when they are finished and field-tested. **Never as
placeholders.**

<br>
<br>

## The spine

*One question per stage. One framework per question.* They are sequenced by
where they apply, and each is defined in
[the wiki](https://github.com/MarioLazo/agentic-coe/wiki/Framework-Spine),
which is canonical.

> **Corrected 2026-08-25.** This line used to open "Nine frameworks." It was
> wrong against its own table, which names eight across seven stages, and it
> disagreed with the wiki published on 2026-08-24, which retired the count
> deliberately: a spine is a sequence of questions, and counting the answers
> invites exactly the drift that produced two different frameworks sharing the
> name "Four Modes." The count is gone rather than corrected to eight.

| | The question | Framework |
|---|---|---|
| **Select** | Which use cases deserve funding? | BXT |
| **Diagnose** | Are we solving the right problem? | The Meaning Gap |
| **Classify** | What are we building? | Application Modes |
| **Build** | How does it get assembled? | The Seven-Layer Stack |
| **Ship** | Is it ready? | Production Gate Question, then Pre-Flight |
| **Operate** | Is it still working? | The Three Drifts |
| **Scale** | Where are we as an organisation? | Agent Factory Maturity Model |

<br>

Two carry most of the weight.

<br>

**The Meaning Gap.** The distance between what a system optimises and what the
organisation actually needs. Two axes: *Run* (can it execute reliably?) and
*Reason* (is it reasoning about the right problem?).

Most organisations measure only Run. The dangerous quadrant is **Precise but
Wrong**: high operational confidence in a system solving the wrong problem.

<sub>Presented at the Toronto Machine Learning Summit.</sub>

<br>

**Three Proofs.** Technology (*does it work?*), Value (*does it matter?*), and
Competence (*can we run it, and fix it when it breaks?*).

Competence is the harder question and the one that predicts whether a pilot
survives. A deployment can be entirely compliant and still fail it, because
nobody on the client side can remediate at 2am.

<sub>These are companions to BXT, not synonyms. **BXT names the dimension.
Three Proofs names the evidence you bring to it.** Trust is the outcome;
Competence is what earns it.</sub>

<br>

<details>
<summary><b>On the word "Modes"</b></summary>

<br>

Until August 2026 this was one framework called "Four Modes," and two different
frameworks were sharing that name.

**Application Modes** classifies what the *AI* does: automating a task,
augmenting a decision, generating an artifact, orchestrating other agents. This
is what an Agent Card records.

**Five Modes** classifies what the *human* does as capability increases: Doing,
Directing, Delegating, Designing, Defining.

Use both. One tells you what you are building. The other tells you what your
job is while it runs, and **autonomy transfers down that ladder while
responsibility does not.**

</details>

<br>
<br>

## The factory metaphor, and why it earns its keep

If you have run manufacturing, supply chain, or distribution, you already have
the model.

| Manufacturing | Agent Factory |
|---|---|
| Supply chains | Data pipelines |
| Assembly line | CI/CD |
| Defect rates | Hallucination rates |
| Safety protocols | Governance |

<br>

The value is that it makes the CFO conversation tractable.

*"How much will this cost?"* stops being a platform license discussion and
becomes a unit-economics answer: cost per unit, quality threshold, and a
trajectory.

<br>
<br>

## The courses

This repository answers *how does an organisation industrialise this.*

Two companion courses answer *how does a practitioner build one that survives.*

<br>

**[From Vibe Coding to Agent Engineering](https://github.com/MarioLazo/vibe-coding-to-agent-engineering)** · *Part 1 · beta*

Opens on a randomised controlled trial where developers predicted they would be
24% faster with AI, believed afterwards they had been 20% faster, and were
measured **19% slower**.

They were reviewing their own work the entire time.

<br>

**[Agent Reliability Engineering](https://github.com/MarioLazo/agent-reliability)** · *Part 2*

**The 3pm Test.** Would you deploy this agent on a Tuesday at 3pm?

Six notebooks that run offline and deterministically in about ten seconds, with
no API key and no dependencies.

<br>

Same bias as this repository: *how things fail, and how you would know.*

<br>
<br>

## Read this before trusting anything here

**Unevenly deep, deliberately.** Grounding is the developed layer: failure
modes, chunking, hybrid search, evaluation, cost engineering, platform guides,
built over six years. The other six layers are mapped but thinner.

**Not a vendor playbook.** Platform guides exist for
[Azure](docs/platform-guides/azure-ai-search.md),
[AWS](docs/platform-guides/aws-bedrock.md),
[GCP](docs/platform-guides/gcp-vertex-ai.md) and
[Databricks](docs/platform-guides/databricks-mosaic.md), but the frameworks are
vendor-agnostic.

**Not a tutorial.** It assumes you have built something and hit the wall.

**Not claimed to be current.** Pages carry a last-reviewed date and a
confidence score. *Trust them accordingly.*

<br>

<sub>Previously `rag-production-guide`. The RAG material is intact under
[`docs/`](docs/), now framed as one layer of a larger operating model rather
than the whole subject. Old links redirect.</sub>

<br>
<br>

## Who this is for

**CIOs, CDOs and transformation leaders** who need to fund and govern agent
programs, not just approve them.

**Architects and platform teams** standing up the CoE and the quality gates.

**Practitioners** with production scar tissue who want to compare notes.

<br>
<br>

## Reference

**[Agent Factory, Regulated Industries Edition](reference/agent-factory-regulated-industries.md)**

A curated 11,000-word index for finance, healthcare and supply chain: agent
frameworks and orchestration, vetted repos by vertical, MCP servers, ontologies
and knowledge graphs, datasets, papers, associations, a regulatory reference,
and deployment checklists.

Where domain expertise is critical and governance is not optional, the hard
part is knowing what has already been built and what is actually usable.

<br>
<br>

## Stay with it

New tools and case breakdowns get published as they are finished.

**Follow along:** [LinkedIn](https://www.linkedin.com/in/mariolazo/), where new tools get announced.

**Collaborate:** I am looking for research collaboration and thought
partnership. Practitioners with production experience, researchers working on
evaluation and governance, and people building community around this. Open an
issue or reach out.

<br>
<br>

<sub>By [Mario Lazo](https://github.com/MarioLazo). Co-author of *AI Data Privacy and Protection* (Technics Publications, 2024).
Licensed CC BY 4.0 for content; see [LICENSE](LICENSE).</sub>
