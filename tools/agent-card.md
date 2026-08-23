# The Agent Card

**A one-page specification every production agent needs before it goes live.**

The Agent Card exists to answer a question that sounds trivial until an incident happens: *who owns this thing, what is it allowed to do, and what happens when it's wrong?*

Most organizations can't answer that for agents already running in production. The card is the minimum documentation standard that makes an agent inventory possible, an audit survivable, and an incident response coherent.

**Rule: no card, no production.** It takes twenty minutes to fill out. If it can't be filled out, the agent isn't ready — the gaps in the card *are* the gaps in the design.

---

## The template

Copy this into your agent registry, one per agent.

```markdown
# Agent Card — <agent name>

## Identity
- **Agent ID:**              <stable unique identifier>
- **Version:**               <semver; bump on prompt, model, or tool change>
- **Status:**                Proposed | Pilot | Production | Deprecated | Retired
- **Deployed:**              <date>
- **Last reviewed:**         <date — see Review cadence below>

## Ownership
- **Business owner:**        <named person — accountable for outcomes, not a team>
- **Technical owner:**       <named person — accountable for the system>
- **Escalation contact:**    <who gets paged, and how>

## Purpose
- **What it does:**          <one sentence, in business terms>
- **Business outcome:**      <the metric it moves — not the proxy>
- **Who it serves:**         <internal team, customer segment, or system>
- **What it explicitly does NOT do:** <the boundary, stated>

## Classification
- **Application mode:**      DOING | DECIDING | DESIGNING | DIRECTING
                             <what the AI does. see note below>
- **Pattern:**               <retrieval | classification | generation | reasoning |
                              transactional | orchestration | research>
- **Risk tier:**             1 (read-only) | 2 (internal write) | 3 (external/regulated) |
                              4 (irreversible or financial)
- **Autonomy level:**        <1–5; see Seniority Ladder>

> **On "Application mode".** This field was labelled `Mode` until 2026-08-20.
> The values are unchanged; only the name was ambiguous. **Application Modes**
> classifies what the *AI* does. Its companion, **Five Modes** (Doing,
> Directing, Delegating, Designing, Defining), classifies what the *human*
> does while it runs. An Agent Card documents the system, so it carries the
> first. Accountability lives with the second.

## Data
- **Reads from:**            <systems, and the classification of the data>
- **Writes to:**             <systems — or "none">
- **Sensitive data:**        PII | PHI | PCI | financial | none
- **Retention:**             <how long inputs/outputs are kept, and where>

## Guardrails
- **Human in the loop:**     Always | On exception | Sampled (__%) | None
- **Approval required for:** <which actions, if any>
- **Rate/spend limits:**     <cap per hour/day, and what happens at the cap>
- **Kill switch:**           <exact mechanism, and who can trigger it>

## Evaluation
- **Accuracy threshold:**    <number — the go/no-go bar, not an aspiration>
- **How it's measured:**     <eval set, method, cadence, and who runs it>
- **Last eval result:**      <score + date>
- **Production Gate answer:** <If it gives the right answer to the wrong
                               question, how would you know? Be specific.>

## Monitoring
- **Drift detection:**       <what's watched, thresholds, alert destination>
- **Review cadence:**        Tier 1–2: quarterly · Tier 3–4: monthly
- **Incident history:**      <link to log>

## Lifecycle
- **Retirement trigger:**    <the condition that ends this agent's life>
- **Dependencies:**          <agents or systems that break if this is removed>
```

---

## Field notes

**Business owner must be a named person.** "The Data team" is not an owner. When an agent makes a bad call, an accountable individual is what turns an incident into a decision instead of a meeting.

**"What it explicitly does NOT do" is the most-skipped and most-valuable field.** Scope creep in agents is silent — a retrieval agent quietly starts drafting customer emails because someone added a tool. Writing the boundary down makes the drift visible.

**Business outcome, not proxy metric.** If the card says "improves response time," ask what response time is standing in for. Optimizing a measurable proxy instead of the real outcome is the single most common Meaning Gap failure — the classic case being an agent that improved email open rates by writing clickbait subject lines that converted worse.

**The Production Gate answer cannot be "we monitor accuracy."** Accuracy against a held-out test set says nothing about whether the agent is working on the right problem. A good answer describes a feedback loop between agent output and a real-world outcome: a sampled human review by someone blind to the agent's answer, a downstream business metric tracked against a baseline, a quarterly review of whether the question itself is still the right one.

**Version bumps on prompt changes, not just code.** A prompt edit can change behavior more than a library upgrade. If your versioning only tracks code, your audit trail has a hole in it.

**A card that can't be completed is a finding.** Empty fields aren't an admin problem — each one is a design gap that will surface later at a worse time. Treat the blanks as the output of the exercise.

---

## Using it in an inventory

Once every agent has a card, questions that were previously unanswerable become queries:

- How many Tier 3+ agents are running without a named business owner?
- Which agents write to systems of record with no human in the loop?
- Which haven't been evaluated in over ninety days?
- If this system goes down, which agents fail with it?

That inventory is the foundation the rest of the CoE is built on. Most organizations discover their first real governance problems just by filling these out for agents that are *already* in production.

---

*Part of [Agentic CoE](../README.md). Licensed [CC BY 4.0](../LICENSE) — reuse freely, including commercially, **with attribution**.*
