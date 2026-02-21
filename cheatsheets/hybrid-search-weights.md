# ⚖️ Hybrid Search Weights

> **Domain-specific BM25/vector weight recommendations**

---

## Weight Selection Matrix

| Domain | BM25 | Vector | Rationale | Example Queries |
|--------|------|--------|-----------|-----------------|
| **Legal/Regulatory** | 70% | 30% | Exact clause/section references critical | "Section 4.2.1 requirements", "GDPR Article 17" |
| **Financial Services** | 65% | 35% | Account numbers, policy codes, amounts | "Policy #A12345", "Q3 2024 revenue" |
| **Healthcare** | 65% | 35% | ICD codes, drug names, exact dosages | "ICD-10 J06.9", "metformin 500mg" |
| **Manufacturing** | 60% | 40% | SKUs, part numbers + descriptions | "SKU-78234", "hydraulic pump assembly" |
| **E-commerce** | 60% | 40% | Product codes + semantic descriptions | "iPhone 15 Pro case", "SKU123456" |
| **Technical Documentation** | 50% | 50% | Balance precision with comprehension | "error 0x8007", "how to configure SSL" |
| **Customer Support** | 30% | 70% | Varied phrasing, semantic understanding | "my order is late", "can't login" |
| **Research/Academic** | 25% | 75% | Concepts over exact terms | "neural network optimization", "climate impact" |
| **Creative/Marketing** | 20% | 80% | Semantic similarity most important | "engaging content ideas", "brand voice" |

---

## Visual Guide

```
BM25-Heavy ←─────────────────────────────────────→ Vector-Heavy

  100%                      50%                      100%
   │                         │                         │
   ▼                         ▼                         ▼
┌──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┬──────┐
│Legal │Financ│Health│Manufa│E-comm│ Tech │Suppor│Resear│Creati│
│ 70%  │ 65%  │ 65%  │ 60%  │ 60%  │ 50%  │ 30%  │ 25%  │ 20%  │
│      │      │      │      │      │      │      │      │      │
│Exact │Codes │ICD   │SKUs  │SKUs+ │Errors│Seman-│Concep│Pure  │
│Match │Policy│Drugs │Parts │Descr │+Docs │tic   │ ts   │Seman-│
│      │      │      │      │      │      │      │      │tic   │
└──────┴──────┴──────┴──────┴──────┴──────┴──────┴──────┴──────┘
```

---

## Query-Based Dynamic Weighting

Instead of fixed weights, adjust based on query characteristics:

| Query Signal | Adjustment | Example |
|-------------|------------|---------|
| Contains quotes `"..."` | +20% BM25 | `"error code 5001"` |
| Contains identifiers | +25% BM25 | `INV-2024-00123` |
| Starts with "how to" | +20% Vector | `how to reset password` |
| Contains "why" or "explain" | +25% Vector | `why did the order fail` |
| > 10 words | +15% Vector | Long descriptive query |
| < 4 words | +15% BM25 | Short lookup query |
| Contains technical jargon | +10% BM25 | Domain-specific terms |

---

## Implementation Examples

### Python (Generic)

```python
def get_weights(query: str, domain: str = "general") -> tuple[float, float]:
    """Return (bm25_weight, vector_weight) based on query and domain."""
    
    # Base weights by domain
    base_weights = {
        "legal": (0.70, 0.30),
        "financial": (0.65, 0.35),
        "healthcare": (0.65, 0.35),
        "manufacturing": (0.60, 0.40),
        "ecommerce": (0.60, 0.40),
        "technical": (0.50, 0.50),
        "support": (0.30, 0.70),
        "research": (0.25, 0.75),
        "general": (0.50, 0.50),
    }
    
    bm25, vector = base_weights.get(domain, (0.5, 0.5))
    
    # Dynamic adjustments
    if '"' in query:  # Quoted phrase
        bm25 += 0.15
    if re.search(r'[A-Z]{2,}-\d+', query):  # Identifier pattern
        bm25 += 0.20
    if query.lower().startswith(("how to", "how do")):
        vector += 0.15
    if any(w in query.lower() for w in ["why", "explain", "describe"]):
        vector += 0.20
    
    # Normalize
    total = bm25 + vector
    return (bm25 / total, vector / total)
```

### Elasticsearch

```json
{
  "retriever": {
    "rrf": {
      "retrievers": [
        {
          "standard": {
            "query": {"match": {"content": "user query"}}
          }
        },
        {
          "knn": {
            "field": "embedding",
            "query_vector": [0.1, 0.2, ...],
            "k": 50
          }
        }
      ],
      "rank_constant": 60
    }
  }
}
```

### Azure AI Search

```python
results = search_client.search(
    search_text=query,  # BM25
    vector_queries=[
        VectorizableTextQuery(
            text=query,
            k_nearest_neighbors=50,
            fields="embedding",
            weight=0.7  # Vector weight
        )
    ],
    top=10
)
```

---

## Common Mistakes

| ❌ Mistake | ✅ Fix |
|-----------|-------|
| Raw score averaging | Use RRF or normalize first |
| Static weights for all queries | Add query classification |
| Ignoring domain characteristics | Tune weights to your content |
| Over-optimizing on test set | Validate on diverse queries |
| Not logging weights used | Log for analysis and tuning |

---

## Quick Decision Guide

```
Is the query looking for a specific ID/code/number?
  → Yes: 70% BM25, 30% Vector
  → No: Continue ↓

Is it a "how to" or explanatory question?
  → Yes: 30% BM25, 70% Vector
  → No: Continue ↓

Is it domain-specific (legal, financial, healthcare)?
  → Yes: 60-70% BM25, 30-40% Vector
  → No: 50% BM25, 50% Vector
```

---

<div align="center">

[← Back to Cheatsheets](../README.md#-cheatsheets)

</div>
