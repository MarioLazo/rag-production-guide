# 📖 Glossary

> **Common RAG terminology explained in plain language**

---

## Core Concepts

### RAG (Retrieval-Augmented Generation)
A technique that enhances LLM responses by first retrieving relevant information from a knowledge base, then using that context to generate grounded answers. Reduces hallucination by providing factual context.

### LLM (Large Language Model)
AI models trained on massive text datasets that can understand and generate human-like text. Examples: GPT-4, Claude, Gemini, Llama.

### Embedding
A numerical representation (vector) of text that captures its semantic meaning. Similar concepts have similar embeddings, enabling semantic search.

### Vector Database
A database optimized for storing and searching embeddings. Enables finding semantically similar content quickly. Examples: Pinecone, Weaviate, Qdrant, Chroma.

### Knowledge Base
The collection of documents, data, or information that a RAG system retrieves from. Can include PDFs, databases, wikis, APIs, etc.

---

## Retrieval Terminology

### BM25 (Best Match 25)
A traditional keyword-based search algorithm that ranks documents by term frequency and document length. Excellent for exact matches.

### Semantic Search
Search based on meaning rather than exact keywords. Uses embeddings to find conceptually similar content even with different wording.

### Hybrid Search
Combining keyword search (BM25) and semantic search (vectors) for better results. The recommended approach for production RAG.

### RRF (Reciprocal Rank Fusion)
A method for combining results from multiple search methods. Merges ranked lists without needing to normalize scores.

```
RRF_score(doc) = Σ 1/(k + rank)
```

### Reranking
A second-pass scoring of retrieved documents using a more sophisticated model (cross-encoder) to improve relevance ordering.

### Top-K
The number of documents retrieved from the knowledge base. Common values: 5-20. Higher K = more context but more noise.

### Query Expansion
Generating multiple variations of a query to improve retrieval recall. Related: RAG Fusion, HyDE.

---

## Chunking Terminology

### Chunking
The process of splitting documents into smaller pieces for embedding and retrieval. Critical for RAG quality.

### Chunk Size
The length of each document piece, typically measured in tokens. Common range: 256-1024 tokens.

### Chunk Overlap
The amount of text shared between adjacent chunks. Prevents information loss at boundaries. Typical: 10-20% of chunk size.

### Semantic Chunking
Splitting documents based on meaning/topic changes rather than fixed sizes.

### Contextual Retrieval
Anthropic's technique of prepending document context to each chunk before embedding. Improves retrieval by 49-67%.

---

## Generation Terminology

### Context Window
The maximum amount of text an LLM can process at once. Measured in tokens. GPT-4: 128K, Claude: 200K.

### Prompt
The instruction and context provided to an LLM to generate a response.

### Grounding
Ensuring LLM responses are based on retrieved context rather than training data. Reduces hallucination.

### Hallucination
When an LLM generates plausible-sounding but false information not supported by the provided context.

### Faithfulness
The degree to which a response is supported by the retrieved context. A key RAG evaluation metric.

### Lost-in-the-Middle
The phenomenon where LLMs pay more attention to information at the beginning and end of context, ignoring the middle.

---

## Evaluation Terminology

### RAG Triad
The three core metrics for RAG evaluation:
1. **Answer Relevancy** — Does the response address the question?
2. **Faithfulness** — Is the response grounded in context?
3. **Context Relevancy** — Is the retrieved context relevant?

### Golden Dataset
A curated set of question-answer pairs with verified correct answers, used for evaluation.

### Ground Truth
The known correct answer for evaluation purposes.

### RAGAS
An open-source framework for RAG evaluation. Reference-free metrics using LLM-as-judge.

### DeepEval
A testing framework for LLM applications with pytest-style syntax and CI/CD integration.

---

## Architecture Terminology

### Ingestion Pipeline
The process of loading, chunking, embedding, and indexing documents into a RAG system.

### Orchestration
Managing the flow between retrieval, context assembly, and generation. Tools: LangChain, LlamaIndex, custom.

### HITL (Human-in-the-Loop)
Design pattern where humans review or approve AI outputs, especially for low-confidence or high-risk responses.

### Agentic RAG
RAG systems with autonomous agents that decide when, what, and where to retrieve using tool-calling patterns.

### GraphRAG
RAG augmented with knowledge graphs for better handling of entity relationships and global queries.

### Knowledge Layer (Semantic Layer)
A structured representation of entities, relationships, and concepts built on top of raw documents. Transforms a pile of text into a connected knowledge base that supports relationship queries and multi-hop reasoning.

### Metadata Enrichment
The process of automatically extracting and attaching descriptive information (topics, entities, domain, authority level, timestamps) to documents and chunks. Enables filtering, boosting, and smarter retrieval.

### Feedback Loop
A system that captures signals about RAG quality (explicit user feedback, implicit behavioral signals) and uses them to systematically improve retrieval, generation, and evaluation over time.

### Active Learning
A strategy for selecting which AI outputs to route to human reviewers for maximum learning value. Instead of random sampling, active learning prioritizes uncertain, novel, or high-risk cases.

### Retraining Trigger
A measurable condition (e.g., human override rate >20%, evaluation metrics declining, new topic cluster emerging) that signals when the RAG system needs adjustment — from prompt refinement to embedding fine-tuning.

---

## Infrastructure Terminology

### Embedding Model
The model used to convert text into vectors. Examples: OpenAI text-embedding-3, Cohere embed, Sentence Transformers.

### Cross-Encoder
A model that scores query-document pairs together (more accurate but slower than bi-encoders). Used for reranking.

### Bi-Encoder
A model that encodes queries and documents separately (faster but less accurate). Used for initial retrieval.

### ANN (Approximate Nearest Neighbor)
Algorithms for fast vector similarity search. Trade small accuracy for large speed gains. Example: HNSW.

### HNSW (Hierarchical Navigable Small World)
A popular ANN algorithm used in most vector databases. Provides fast, accurate approximate search.

### Quantization
Reducing vector precision (e.g., float32 → int8) to save storage and improve speed with minimal accuracy loss.

---

## Cost Terminology

### Token
The basic unit of text processing for LLMs. Roughly 4 characters or 0.75 words in English.

### Semantic Caching
Storing query-response pairs indexed by embedding similarity. Similar queries return cached responses.

### Model Routing
Directing queries to different models based on complexity. Simple queries → cheap models, complex → expensive.

### Batch Inference
Processing multiple requests together for cost savings. Typically 50% cheaper than real-time.

---

## Abbreviations Quick Reference

| Abbreviation | Full Term |
|-------------|-----------|
| RAG | Retrieval-Augmented Generation |
| LLM | Large Language Model |
| BM25 | Best Match 25 |
| RRF | Reciprocal Rank Fusion |
| ANN | Approximate Nearest Neighbor |
| HNSW | Hierarchical Navigable Small World |
| HITL | Human-in-the-Loop |
| NER | Named Entity Recognition |
| FCR | First-Call Resolution |
| AHT | Average Handling Time |
| ROI | Return on Investment |
| CI/CD | Continuous Integration/Continuous Deployment |

---

<div align="center">

[← Back to Resources](../README.md#-resources)

</div>
