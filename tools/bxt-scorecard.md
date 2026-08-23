# The BXT Scorecard

**Scores candidate use cases on Business value, eXecutability, and Trust: so funding goes to what can actually ship.**

Most agent portfolios are selected on enthusiasm. Someone senior saw a demo, a team had capacity, a vendor ran a workshop. The result is a roadmap full of initiatives that are individually plausible and collectively undeliverable.

BXT forces three questions to be answered separately, because they fail separately:

| Dimension | The question | Failure mode when it's missing |
|---|---|---|
| **B: Business value** | Does it matter? | The system works and nobody uses it, or it moves no metric anyone tracks |
| **X: eXecutability** | Can we actually build it? | It succeeds in a POC and dies on integration, data quality, or scale |
| **T: Trust** | Is it safe to run? | It delivers value and creates audit, regulatory, or reputational exposure |

A use case needs all three. The common pattern is a portfolio strong on B, unexamined on X, and silent on T, which is why so many programs discover their governance requirements after the build is done.

---

## Scoring

Score each dimension 0–3. Score honestly; the tool's only value is as a forcing function, and a scorecard where everything is a 3 is a scorecard nobody used.

### B: Business Value

| Score | Criteria |
|---|---|
| **3** | Tied to a metric an executive already reports on. Baseline is measured. Value is quantified and the owner agrees with the number. |
| **2** | Clear business benefit, quantified but not yet baselined, owner identified. |
| **1** | Benefit is directional, "saves time," "improves experience", with no number attached. |
| **0** | Value is assumed. No named beneficiary. |

**The ROI trap:** a number that only exists in the business case. If nobody is measuring the baseline today, you cannot prove improvement tomorrow: and the initiative will be defended with anecdotes at renewal time. **Score 0 on B if there is no baseline measurement, regardless of how large the projected number is.**

### X: eXecutability

| Score | Criteria |
|---|---|
| **3** | Data exists, is accessible, and is of known quality. Integration points have APIs. The team has shipped something comparable. |
| **2** | Data exists with known gaps. Integration is feasible with effort. Team has adjacent experience. |
| **1** | Data requires significant preparation or new collection. Integration is unproven. Capability gap is real. |
| **0** | Depends on data that doesn't exist, or a system with no integration path. |

**The capability gap:** teams routinely score X on the model and forget the pipeline. The model is rarely the hard part. Ask specifically about data freshness, access approvals, and who maintains the integration after launch, that last one sinks more initiatives than accuracy ever does.

### T: Trust

| Score | Criteria |
|---|---|
| **3** | Risk tier assigned. Governance requirements known and achievable. Compliance stakeholder engaged and supportive. |
| **2** | Risk understood. Governance path is clear but not yet designed. Compliance is aware. |
| **1** | Risk tier is unclear, or governance requirements exceed current capability. |
| **0** | Regulated or irreversible actions with no governance design. Compliance has not been engaged. |

**The governance threshold:** "We'll loop in Compliance once we prove value" is the single most reliable predictor of a stalled program. By the time Compliance is engaged, the model has often already been trained on data it shouldn't have touched. **Score 0 on T if no compliance, legal, or risk stakeholder is named in the charter.**

---

## Reading the scores

Don't average them. Averaging hides exactly what the tool is designed to expose, a 3/3/0 and a 2/2/2 both average to 2, and they are completely different situations.

| Profile | Reading | Action |
|---|---|---|
| **3 / 3 / 3** | Ready | Fund it. This is your proof case. |
| **3 / 3 / 0–1** | Governance-blocked | Do not build yet. Engage compliance first, the work is real but the sequence is wrong. |
| **3 / 0–1 / 3** | Capability-blocked | Fix data or integration first, or descope to what's actually reachable. |
| **0–1 / 3 / 3** | Solution looking for a problem | Usually a demo someone fell in love with. Decline or reframe. |
| **2 / 2 / 2** | Plausible, unproven | Needs a scoping pass before it competes for funding. |
| Any **0** | Disqualified for now | The zero is the work. Address it before rescoring. |

**A zero anywhere is a stop, not a discount.** The purpose is to make the blocker visible early, when fixing it is cheap.

---

## Running it as a portfolio

Score every candidate in one session, with the same people, in one sitting. Comparative scoring is far more reliable than absolute scoring, teams calibrate against each other in a way they can't against an abstract rubric.

In the room, you want: the business owner (for B), the technical lead (for X), and someone from risk, legal, or compliance (for T). If the T voice isn't present, the scores will be optimistic and you'll find out later.

Two things to watch for:

**Score B and X separately, and compare who's talking.** When the technical lead answers the B questions, that's a **framing mismatch**, the problem was defined by the people who will build it rather than the people who need it. Ask who the business sponsor was when the problem was first framed.

**Rescore quarterly.** X and T both move as capability and regulation change. A use case that scored 1 on eXecutability last quarter may be a 3 now because a data platform landed. The portfolio should be re-ranked, not re-litigated.

---

*Part of [Agentic CoE](../README.md). Licensed [CC BY 4.0](../LICENSE), reuse freely, including commercially, **with attribution**.*
