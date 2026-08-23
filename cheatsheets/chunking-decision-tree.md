# 🌳 Chunking Decision Tree

> **Quick reference for selecting the right chunking strategy**

---

## Decision Flowchart

```mermaid
flowchart TD
    START["🚀 Start: What document type?"] --> Q1{Structured data?<br/><i>Tables, forms, JSON, tickets</i>}
    
    Q1 -->|"Yes"| A1["✅ Field-aware chunking<br/>Preserve structure boundaries"]
    Q1 -->|"No"| Q2{Clear section markers?<br/><i>Headers, chapters, markdown</i>}
    
    Q2 -->|"Yes"| A2["✅ Document-aware chunking<br/>Split by headers/sections"]
    Q2 -->|"No"| Q3{Primary query type?}
    
    Q3 -->|"Factoid<br/>(Who, What, When)"| A3["256-512 tokens<br/>10% overlap"]
    Q3 -->|"Analytical<br/>(Why, How, Compare)"| A4["1024-2048 tokens<br/>20% overlap"]
    Q3 -->|"Mixed / Unknown"| A5["512 tokens<br/>15% overlap"]
    
    A1 --> Q4{Retrieval accuracy ≥80%?}
    A2 --> Q4
    A3 --> Q4
    A4 --> Q4
    A5 --> Q4
    
    Q4 -->|"Yes"| DONE["✅ Deploy!"]
    Q4 -->|"No"| Q5["Add Contextual Retrieval"]
    
    Q5 --> Q6{Still issues?}
    Q6 -->|"Yes"| Q7["Try semantic chunking"]
    Q6 -->|"No"| DONE
    
    Q7 --> DONE
    
    style START fill:#e3f2fd
    style DONE fill:#c8e6c9
    style Q5 fill:#fff9c4
```

<br>
<br>

## Quick Reference Table

| Document Type | Strategy | Size | Overlap | Key Consideration |
|--------------|----------|------|---------|-------------------|
| **ITSM tickets** | Field-aware | By field | N/A | Keep description/resolution together |
| **Technical docs** | Header-based | By section | N/A | Preserve hierarchy |
| **FAQs** | Q&A pairs | Per pair | N/A | Keep question with answer |
| **Legal contracts** | Clause-based | By clause | 10% | Exact references matter |
| **Product manuals** | Section-based | 512-1024 | 15% | Step sequences intact |
| **Research papers** | Semantic | Variable | 20% | Concept boundaries |
| **Code files** | AST-based | By function | 0% | Syntax-aware splitting |
| **Chat logs** | Turn-based | By turn | Context | Conversation flow |

<br>
<br>

## Size Guidelines

```
┌─────────────────────────────────────────────────────────────────┐
│                    CHUNK SIZE SPECTRUM                          │
├─────────────────────────────────────────────────────────────────┤
│                                                                 │
│  128     256     512     1024    2048    4096                  │
│   │       │       │        │       │       │                   │
│   ▼       ▼       ▼        ▼       ▼       ▼                   │
│  ┌─┐     ┌──┐    ┌───┐    ┌────┐  ┌─────┐ ┌──────┐            │
│  │ │     │  │    │   │    │    │  │     │ │      │            │
│  └─┘     └──┘    └───┘    └────┘  └─────┘ └──────┘            │
│   │       │       │        │       │       │                   │
│   │       │       │        │       │       │                   │
│ Precise  Facts   General  Analysis Deep    Full               │
│ lookup          purpose           dive    context             │
│                                                                 │
│ ←── Higher Precision          Higher Recall ──→                │
│                                                                 │
└─────────────────────────────────────────────────────────────────┘
```

<br>
<br>

## Anti-Patterns to Avoid

| ❌ Don't | ✅ Do Instead |
|----------|--------------|
| Fixed-size without overlap | Add 10-20% overlap |
| Same strategy for all docs | Match strategy to document type |
| Chunks > 2048 tokens | Split into smaller semantic units |
| Chunks < 128 tokens | Increase to preserve context |
| Hardcode without measuring | Iterate based on retrieval metrics |

<br>
<br>

## Contextual Retrieval Checklist

Add Contextual Retrieval when:

- [ ] Retrieval accuracy < 80%
- [ ] Chunks lose document context
- [ ] Many similar documents in corpus
- [ ] Users report "found but not helpful" results

**Implementation cost:** ~$1 per million tokens (one-time)  
**Expected improvement:** 49-67% retrieval failure reduction

<br>
<br>

## Platform-Specific Notes

### AWS Bedrock Knowledge Bases
```
Supports: FIXED_SIZE, SEMANTIC, HIERARCHICAL, NONE
Recommended: SEMANTIC with maxTokens=512
```

### Azure AI Search
```
Use Document Intelligence for structure detection
Chunk by detected sections/headers
```

### Google Vertex AI
```
Automatic chunking with configurable size
Set chunk_size=500 as baseline
```

<br>
<br>

<div align="center">

[← Back to Cheatsheets](../README.md#-cheatsheets)

</div>
