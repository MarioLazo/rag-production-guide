# 🔄 Feedback Loop Design Cheatsheet

> **Quick reference for designing, implementing, and measuring RAG feedback loops**

---

## Feedback Capture: What to Collect

### Explicit Feedback (Users Tell You)

| Mechanism | Signal Quality | Implementation |
|-----------|---------------|----------------|
| Thumbs up / down | Medium | Button in response UI |
| "Report incorrect" with category | High | Dropdown: wrong, outdated, incomplete, irrelevant |
| User correction ("Actually, it's...") | Very High | Text field on negative feedback |
| Escalation to human | Very High | "Talk to a person" button |

### Implicit Feedback (Users Show You)

| Signal | Interpretation | Detection |
|--------|---------------|-----------|
| Query reformulation | First answer wasn't helpful | Same user, similar query within 2 min |
| Session abandonment | User gave up | No resolution signal before exit |
| Follow-up question chain | Answer was incomplete | 3+ questions on same topic |
| Copy/paste from response | Answer was useful | Clipboard event (with consent) |
| Same query from many users | Knowledge gap or common need | Aggregate query clustering |

---

## Failure Categorization: Where Did It Break?

When you get negative feedback, classify *where* the problem occurred:

```
Negative Feedback
├── 🔍 Retrieval Failure → Right docs not found
│   └── Fix: Chunking, embeddings, search config
├── 🎯 Relevance Failure → Wrong docs found
│   └── Fix: Reranking, metadata filters, query routing
├── ✨ Generation Failure → Right docs, wrong answer
│   └── Fix: Prompt engineering, context assembly
├── 📅 Freshness Failure → Answer was outdated
│   └── Fix: Ingestion pipeline, freshness scoring
└── 📚 Coverage Gap → Info doesn't exist in knowledge base
    └── Fix: Add missing documents
```

---

## HITL Routing: When to Involve Humans

### Quick Decision Matrix

| Confidence | Risk Level | Action |
|-----------|------------|--------|
| High (>0.8) | Low | Auto-approve |
| High (>0.8) | High | Spot-check (sample 10%) |
| Medium (0.5-0.8) | Low | Auto-approve with disclaimer |
| Medium (0.5-0.8) | High | **Human review** |
| Low (<0.5) | Any | **Human review** |

### Confidence Signals to Combine

| Signal | Weight | Source |
|--------|--------|--------|
| Retrieval score (top chunk) | 30% | Vector DB similarity |
| Coverage assessment | 30% | Does context contain the answer? |
| Response consistency | 30% | Do multiple generations agree? |
| Hedging language absence | 10% | No "I'm not sure" phrases |

---

## Retraining Triggers: When to Act

| Trigger | Threshold | Action |
|---------|-----------|--------|
| Human override rate rising | >20% of routed queries | Analyze failures, refine prompts, expand golden dataset |
| Evaluation metrics declining | >5% drop week-over-week | Root cause analysis on weakest metric |
| New topic cluster in queries | Queries on unfamiliar topics | Add documents, update taxonomy, possibly fine-tune embeddings |
| Embedding drift | Mean retrieval score dropping | Re-embed corpus or fine-tune embedding model |
| Knowledge base grew >30% | Document count | Rebuild indexes, check for semantic collapse |
| User trust declining | Usage dropping, escalations rising | Full system audit (this is a lagging indicator) |

---

## Retraining Actions: Lightest Fix First

Always start with the lowest-effort fix that addresses the problem:

```
Effort Scale (try in order):

1. PROMPT REFINEMENT          [Hours]   → Fix generation failures
2. GOLDEN DATASET EXPANSION   [Ongoing] → Better evaluation from user corrections
3. SEARCH CONFIG TUNING       [Days]    → Adjust BM25/vector weights, reranking
4. CHUNKING STRATEGY UPDATE   [Days]    → Requires re-ingestion of affected docs
5. KNOWLEDGE GRAPH UPDATE     [Days]    → New entities, changed relationships
6. EMBEDDING FINE-TUNING      [Weeks]   → Domain vocabulary not captured
7. FULL PIPELINE REBUILD      [Weeks]   → Nuclear option, only when fundamentals wrong
```

---

## Active Learning: Pick the Right Reviews

Don't randomly sample — pick interactions where human feedback teaches the most:

| Priority for Review | Why |
|--------------------|-----|
| System was most uncertain (confidence 0.45-0.55) | Near decision boundary — maximum information gain |
| Novel topic cluster | System hasn't learned this yet |
| High-risk domain queries | Errors here are costly |
| Disagreement between retrieval methods | System is confused |
| First occurrence of new query pattern | Early signal of emerging need |

---

## Key Metrics Dashboard

### Feedback Loop Health

| Metric | Target | Red Flag |
|--------|--------|----------|
| Feedback capture rate (explicit) | >10% of interactions | <5% |
| Time to root cause (P0/P1) | <1 week | >2 weeks |
| Fix verification rate | >70% of fixes show improvement | <50% |
| Golden dataset growth | 10-20 new cases/month | Stagnant |

### HITL Effectiveness

| Metric | Target | Red Flag |
|--------|--------|----------|
| Override rate | 10-20% | >30% (system too wrong) or <5% (routing too conservative) |
| Agreement rate | 70-85% | <60% |
| Review latency | Within SLA | Growing queue |
| Reviewer consistency | >80% agreement | <70% (guidelines need work) |
| Automation rate trend | Increasing monthly | Flat or declining |

---

## Feedback Loop Maturity Model

| Level | Name | You're Here If... |
|-------|------|-------------------|
| 0 | No Feedback | "It seems to work" |
| 1 | Basic Capture | Thumbs up/down exists but nobody looks at the data |
| 2 | Categorized | You know *where* failures happen (retrieval vs. generation) |
| 3 | Root Cause | You systematically trace failures to causes and fix them |
| 4 | Closed Loop | Feedback automatically drives evaluation and improvement |
| 5 | Predictive | You catch failures before users notice them |

**Most teams are at Level 0-1. Getting to Level 3 is a significant competitive advantage.**

---

## Quick Implementation Checklist

- [ ] Explicit feedback UI deployed (minimum: thumbs up/down)
- [ ] Implicit signals captured (reformulation, abandonment)
- [ ] Feedback linked to interaction trace (query → chunks → response)
- [ ] Failure categorization pipeline active
- [ ] HITL routing with confidence scoring
- [ ] Human review queue with SLAs
- [ ] Every human decision stored as training data
- [ ] Golden dataset expanding from corrections
- [ ] Retraining triggers monitored
- [ ] Automation rate trending upward

---

## Related Documentation

| Topic | Guide |
|-------|-------|
| Full feedback loop architecture | [Feedback Loops & Refinement](../docs/10-feedback-loops-and-refinement.md) |
| Complete HITL and retraining guide | [Human-in-the-Loop](../docs/11-human-in-the-loop.md) |
| Metadata for feedback enrichment | [Metadata & Knowledge Layers](../docs/09-metadata-and-knowledge-layers.md) |
| Evaluation metrics baseline | [Evaluation Framework](../docs/07-evaluation-framework.md) |

---

<div align="center">

[← Back to Cheatsheets](README.md)

</div>
