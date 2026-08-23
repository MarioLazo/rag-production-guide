# The Pre-Flight Checklist

**Ten gates between "it works on my machine" and "it's live."**

Pilots are forgiving. Production is not. The checklist exists because the failures that make the news are almost never novel, they're the same handful of missing controls, repeated. An agent that quotes a price it shouldn't honor, drains a rate limit overnight, or keeps answering confidently after its data went stale.

Every gate below maps to a failure that has actually happened to somebody.

**Rule: all ten pass, or it doesn't ship.** Gates can be waived, deliberately, by a named person, in writing, with an expiry date. A waiver is a decision. Skipping is an accident.

---

## The ten gates

### 1. The agent has a completed Agent Card
Owner, risk tier, autonomy level, kill switch, boundaries, all filled in. Empty fields are design gaps, not paperwork. See [Agent Card](agent-card.md).

**Automatable:** yes, fail the build if the card is missing required fields.

### 2. Accuracy is measured against a held-out set, by someone who didn't build it
A defined threshold, agreed before the test, not after. Self-evaluation by the building team is the most common source of false confidence.

**Automatable:** partly, run the eval in CI, but independence is a process control.

### 3. The Production Gate Question has a specific answer
*If this gives the right answer to the wrong question, how would you know?* The answer must describe a feedback loop to a real-world outcome, not a test-set score. "We monitor accuracy" is a failing answer.

**Automatable:** no, this is a human review gate.

### 4. Failure modes are enumerated and handled
What happens on: no result, low confidence, a tool timeout, malformed input, an upstream outage. Each needs defined behavior. Silent failure is the worst outcome, an agent that returns something plausible when it should return nothing.

**Automatable:** yes, test each failure path explicitly.

### 5. Adversarial inputs have been tested
Prompt injection, jailbreak attempts, and data exfiltration probes, at minimum. If the agent reads untrusted content, customer emails, web pages, uploaded documents, this gate is mandatory, not optional.

**Automatable:** yes, run an injection probe suite in CI.

### 6. Rate and spend limits are enforced in code
Per-hour and per-day caps, with defined behavior at the cap. Enforced at the system level, not by an alert someone reads in the morning. Runaway loops are cheap to prevent and expensive to discover on an invoice.

**Automatable:** yes.

### 7. The kill switch has been tested: not just built
Someone has actually triggered it in a non-production environment and confirmed the agent stops. An untested kill switch is a belief, not a control. Confirm who is authorized to pull it and that they know they are.

**Automatable:** partly, automate the mechanism, rehearse the procedure.

### 8. Human-in-the-loop matches the risk tier
Tier 3+ agents need a designed review step, not an assumed one. "A human will notice" is not a control. Check that the reviewer has enough context to catch a *subtly* wrong answer, not just an obviously wrong one.

**Automatable:** no, design review.

### 9. Logging is sufficient to reconstruct any decision
Inputs, retrieved context, tool calls, model version, prompt version, and output. If you cannot answer "why did it do that?" three months later, you cannot run an incident review or survive an audit.

**Automatable:** yes, assert on log schema completeness.

### 10. Drift monitoring is live before launch, not after
Thresholds set, alerts routed to someone who will act on them. Agents degrade quietly; the gap between degradation and detection is where trust is lost.

**Automatable:** yes.

---

## Automated vs. manual

Seven of the ten can be enforced in CI. Three require human judgment.

| Gate | Automated |
|---|---|
| 1, Agent Card complete | ✅ |
| 2, Independent accuracy eval | ⚠️ partial |
| 3, Production Gate answer | ❌ human |
| 4, Failure modes handled | ✅ |
| 5, Adversarial testing | ✅ |
| 6, Rate and spend limits | ✅ |
| 7, Kill switch tested | ⚠️ partial |
| 8, HITL matches risk tier | ❌ human |
| 9, Reconstructable logging | ✅ |
| 10, Drift monitoring live | ✅ |

The point of automating seven is to make the three human gates worth people's attention. A review meeting that spends its time checking whether logging exists is a review meeting that won't think hard about the Production Gate Question.

---

## Wiring it into CI/CD

Make the gate structural rather than cultural:

1. Agent definitions live in version control alongside code, prompts included.
2. The pipeline runs gates 1, 4, 5, 6, 9, 10 on every change.
3. A merge to the release branch requires the eval suite (gate 2) to pass its threshold.
4. Gates 3 and 8 are a required human approval on the release PR, recorded there.
5. Deployment writes the agent into the registry automatically, the inventory maintains itself instead of being reconstructed later.

The failure mode to avoid: a checklist that lives in a wiki, gets filled out from memory after the fact, and becomes a compliance artifact instead of a control.

---

## Waivers

Real programs ship with known gaps. Make that explicit rather than silent:

```
Gate waived:     <number and name>
Reason:          <why shipping without it is acceptable now>
Compensating control: <what covers the gap in the meantime>
Approved by:     <named person with authority>
Expires:         <date, not "TBD">
```

A waiver with no expiry is a permanent gap wearing a temporary label.

---

*Part of [Agentic CoE](../README.md). Licensed [CC BY 4.0](../LICENSE), reuse freely, including commercially, **with attribution**.*
