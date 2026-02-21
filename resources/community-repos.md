# 🌟 Community Repositories

> **Open-source RAG projects from the community — with gratitude for their contributions**

---

## 🙏 A Note of Thanks

The RAG ecosystem thrives because of the generosity of open-source contributors. These projects represent countless hours of work shared freely with the community. We encourage you to:

- ⭐ **Star** repositories you find valuable
- 🐛 **Report issues** when you find them
- 🔧 **Contribute** improvements back
- 💬 **Share** your production experiences

---

## Production-Ready RAG Systems

| Repository | Stars | Description | Best For |
|------------|-------|-------------|----------|
| [**infiniflow/ragflow**](https://github.com/infiniflow/ragflow) | ~70K | Production-ready RAG with deep document understanding, GraphRAG, visual chunking. The most complete open-source RAG system. | Teams wanting a full solution |
| [**langchain-ai/langchain**](https://github.com/langchain-ai/langchain) | ~95K | The pioneering LLM application framework. Extensive RAG support with many integrations. | Rapid prototyping, flexibility |
| [**run-llama/llama_index**](https://github.com/run-llama/llama_index) | ~35K | Data framework for LLM applications. Excellent abstractions for indexing and querying. | Data-centric RAG |
| [**chroma-core/chroma**](https://github.com/chroma-core/chroma) | ~15K | AI-native embedding database. Simple API, excellent for getting started. | Quick experiments |
| [**qdrant/qdrant**](https://github.com/qdrant/qdrant) | ~20K | High-performance vector similarity search engine with extended filtering. | Production vector search |
| [**weaviate/weaviate**](https://github.com/weaviate/weaviate) | ~11K | Open-source vector database with GraphQL API and modules for ML models. | Enterprise deployments |

---

## Evaluation & Testing

| Repository | Stars | Description | Best For |
|------------|-------|-------------|----------|
| [**explodinggradients/ragas**](https://github.com/explodinggradients/ragas) | ~12K | Reference-free RAG evaluation. The standard for measuring RAG quality. Published at EACL 2024. | Evaluation without ground truth |
| [**confident-ai/deepeval**](https://github.com/confident-ai/deepeval) | ~12K | Production RAG testing with pytest-like syntax. 50+ metrics, CI/CD integration, red-teaming. | CI/CD integration |
| [**Marker-Inc-Korea/AutoRAG**](https://github.com/Marker-Inc-Korea/AutoRAG) | ~5K | AutoML-style pipeline optimization. Automatically finds the best RAG configuration. | Pipeline optimization |

---

## Educational & Cookbooks

| Repository | Stars | Description | Best For |
|------------|-------|-------------|----------|
| [**athina-ai/rag-cookbooks**](https://github.com/athina-ai/rag-cookbooks) | ~500 | The most complete taxonomy: Naive → Advanced → Agentic RAG with built-in evaluation. | Learning RAG patterns |
| [**ibm-granite-community/granite-snack-cookbook**](https://github.com/ibm-granite-community/granite-snack-cookbook) | ~200 | Modular recipes with Docling parsing, Granite RAG 3.0 LoRA, multimodal RAG. | IBM Granite users |
| [**pinecone-io/examples**](https://github.com/pinecone-io/examples) | ~2K | Comprehensive RAG examples from Pinecone. Good for learning patterns. | Pinecone users |

---

## Specialized RAG Patterns

### Agentic RAG
| Repository | Stars | Description |
|------------|-------|-------------|
| [**langchain-ai/langgraph**](https://github.com/langchain-ai/langgraph) | ~7K | Framework for building stateful, multi-actor LLM applications. Agent orchestration. |
| [**microsoft/autogen**](https://github.com/microsoft/autogen) | ~35K | Multi-agent conversation framework. Complex reasoning with multiple agents. |

### Graph RAG
| Repository | Stars | Description |
|------------|-------|-------------|
| [**microsoft/graphrag**](https://github.com/microsoft/graphrag) | ~20K | Official Microsoft GraphRAG. Knowledge graphs from unstructured text. |
| [**neo4j/neo4j-graphrag-python**](https://github.com/neo4j/neo4j-graphrag-python) | ~100 | Neo4j's GraphRAG implementation with property graphs. |

### Multimodal RAG
| Repository | Stars | Description |
|------------|-------|-------------|
| [**Unstructured-IO/unstructured**](https://github.com/Unstructured-IO/unstructured) | ~9K | Universal document parser. PDFs, images, HTML, and more. |
| [**VikParuchuri/marker**](https://github.com/VikParuchuri/marker) | ~18K | Convert PDFs to markdown with high accuracy. Excellent for RAG ingestion. |

---

## Infrastructure & Tooling

| Repository | Stars | Description | Best For |
|------------|-------|-------------|----------|
| [**pgvector/pgvector**](https://github.com/pgvector/pgvector) | ~12K | Vector similarity search for PostgreSQL. Use your existing database! | PostgreSQL users |
| [**zilliztech/GPTCache**](https://github.com/zilliztech/GPTCache) | ~7K | Semantic caching for LLM applications. Reduce costs and latency. | Cost optimization |
| [**mlflow/mlflow**](https://github.com/mlflow/mlflow) | ~19K | ML lifecycle management. Excellent for tracking RAG experiments. | Experiment tracking |
| [**traceloop/openllmetry**](https://github.com/traceloop/openllmetry) | ~2K | OpenTelemetry-based observability for LLM applications. | Production monitoring |

---

## Embedding Models

| Repository | Stars | Description | Best For |
|------------|-------|-------------|----------|
| [**sentence-transformers/sentence-transformers**](https://github.com/sentence-transformers/sentence-transformers) | ~15K | State-of-the-art sentence embeddings. Many pre-trained models available. | General embeddings |
| [**FlagOpen/FlagEmbedding**](https://github.com/FlagOpen/FlagEmbedding) | ~7K | BGE embedding models. Top performers on MTEB leaderboard. | High-quality embeddings |
| [**jina-ai/jina**](https://github.com/jina-ai/jina) | ~21K | Neural search framework with multimodal embedding support. | Multimodal search |

---

## How to Choose

### For Getting Started
1. **Chroma** — Simplest to set up, great for learning
2. **LangChain** — Most flexible, extensive documentation
3. **RAGAS** — Start evaluating from day one

### For Production
1. **RAGFlow** — Full-featured, production-ready
2. **Qdrant** or **Weaviate** — Scalable vector search
3. **DeepEval** — CI/CD integration for testing

### For Advanced Use Cases
1. **LangGraph** — Multi-agent orchestration
2. **GraphRAG** — Complex reasoning over documents
3. **Unstructured** — Complex document parsing

---

## Contributing to These Projects

Many projects welcome contributions:

```bash
# Example contribution workflow
gh repo fork confident-ai/deepeval
git clone https://github.com/YOUR-USERNAME/deepeval
cd deepeval
git checkout -b my-feature
# Make changes
git commit -m "Add feature"
gh pr create
```

### Ways to Contribute
- 📝 Improve documentation
- 🐛 Fix bugs
- ✨ Add features
- 🧪 Add tests
- 🌐 Translate docs

---

## Keeping Up with the Ecosystem

The RAG ecosystem evolves rapidly. Stay updated:

- **Awesome lists**: [awesome-rag](https://github.com/topics/awesome-rag)
- **Hugging Face**: [huggingface.co/blog](https://huggingface.co/blog)
- **arXiv**: Search for "retrieval augmented generation"
- **Twitter/X**: Follow maintainers of projects you use

---

<div align="center">

*Thank you to all open-source contributors who make this ecosystem possible.* 🙏

[← Back to Resources](../README.md#-resources)

</div>
