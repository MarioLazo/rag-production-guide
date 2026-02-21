# 🏢 Official Vendor Repositories

> **Curated list of official RAG-related repositories from major cloud providers and AI companies**

---

## Microsoft / Azure

| Repository | Description | Stars |
|------------|-------------|-------|
| [**Azure-Samples/azure-search-openai-demo**](https://github.com/Azure-Samples/azure-search-openai-demo) | The gold standard Azure RAG reference. Hybrid search, semantic ranking, multimodal support, one-command deploy. | ~6K |
| [**microsoft/graphrag**](https://github.com/microsoft/graphrag) | Knowledge graph-augmented RAG using LLMs to build graphs from unstructured text. Excellent for complex, multi-hop queries. | ~20K |
| [**Azure/GPT-RAG**](https://github.com/Azure/GPT-RAG) | Enterprise-scale secure RAG with Azure Landing Zone patterns. Production-ready architecture. | ~1K |
| [**microsoft/generative-ai-for-beginners**](https://github.com/microsoft/generative-ai-for-beginners) | 21-lesson course covering RAG, prompt engineering, and generative AI fundamentals. | ~70K |
| [**microsoft/semantic-kernel**](https://github.com/microsoft/semantic-kernel) | SDK for integrating LLMs with plugins. Memory and RAG patterns included. | ~22K |

### Key Azure Services for RAG
- **Azure AI Search** — Hybrid search with semantic ranking
- **Azure OpenAI Service** — GPT-4, embeddings
- **Azure AI Document Intelligence** — Document parsing
- **Azure Blob Storage** — Document storage

---

## Amazon Web Services

| Repository | Description | Stars |
|------------|-------------|-------|
| [**aws-samples/amazon-bedrock-samples**](https://github.com/aws-samples/amazon-bedrock-samples) | Comprehensive Bedrock examples including Knowledge Bases, RAG patterns, and evaluation with RAGAS. | ~500 |
| [**aws-samples/rag-using-langchain-amazon-bedrock-and-opensearch**](https://github.com/aws-samples/rag-using-langchain-amazon-bedrock-and-opensearch) | Production RAG pattern with LangChain, Bedrock, and OpenSearch. | ~200 |
| [**aws-samples/amazon-bedrock-workshop**](https://github.com/aws-samples/amazon-bedrock-workshop) | Hands-on workshop materials for Bedrock including RAG labs. | ~1K |
| [**aws-samples/generative-ai-cdk-constructs**](https://github.com/aws-samples/generative-ai-cdk-constructs) | AWS CDK constructs for deploying generative AI workloads including RAG. | ~300 |

### Key AWS Services for RAG
- **Amazon Bedrock** — Foundation models (Claude, Llama, Titan)
- **Bedrock Knowledge Bases** — Managed RAG
- **Amazon Kendra** — Enterprise search
- **Amazon OpenSearch** — Vector search
- **Amazon S3 Vectors** — Cost-effective vector storage (new)

---

## Google Cloud

| Repository | Description | Stars |
|------------|-------------|-------|
| [**GoogleCloudPlatform/generative-ai**](https://github.com/GoogleCloudPlatform/generative-ai) | Vertex AI samples including RAG, embeddings, and Gemini integration. | ~8K |
| [**google/generative-ai-docs**](https://github.com/google/generative-ai-docs) | Official documentation and examples for Google's generative AI products. | ~1K |
| [**GoogleCloudPlatform/applied-ai-engineering-samples**](https://github.com/GoogleCloudPlatform/applied-ai-engineering-samples) | Production AI engineering patterns from Google Cloud. | ~500 |

### Key GCP Services for RAG
- **Vertex AI Search** — Managed RAG solution
- **Vertex AI** — Foundation models, Gemini
- **Document AI** — Document parsing
- **AlloyDB / Cloud SQL** — pgvector support
- **Vertex AI Vector Search** — Scalable vector search

---

## Databricks

| Repository | Description | Stars |
|------------|-------------|-------|
| [**databricks/genai-cookbook**](https://github.com/databricks/genai-cookbook) | GenAI patterns on the Lakehouse architecture. RAG, fine-tuning, evaluation. | ~500 |
| [**databricks-demos/llm-rag-chatbot**](https://github.com/databricks-demos/llm-rag-chatbot) | End-to-end RAG chatbot demo with MLflow evaluation and monitoring. | ~200 |
| [**databricks/databricks-ml-examples**](https://github.com/databricks/databricks-ml-examples) | ML examples including embedding models and retrieval patterns. | ~300 |

### Key Databricks Services for RAG
- **Mosaic AI Vector Search** — Managed vector search
- **Mosaic AI Model Serving** — LLM deployment
- **MLflow** — Experiment tracking, evaluation
- **Unity Catalog** — Governance

---

## NVIDIA

| Repository | Description | Stars |
|------------|-------------|-------|
| [**NVIDIA-AI-Blueprints/rag**](https://github.com/NVIDIA-AI-Blueprints/rag) | GPU-accelerated enterprise RAG with NIM microservices. Production-ready. | ~100 |
| [**NVIDIA/GenerativeAIExamples**](https://github.com/NVIDIA/GenerativeAIExamples) | Reference implementations for RAG and other generative AI workflows. | ~2K |
| [**NVIDIA/NeMo-Guardrails**](https://github.com/NVIDIA/NeMo-Guardrails) | Programmable guardrails for LLM applications including RAG. | ~4K |

### Key NVIDIA Technologies for RAG
- **NIM (NVIDIA Inference Microservices)** — Optimized model serving
- **TensorRT-LLM** — LLM inference optimization
- **RAPIDS** — GPU-accelerated data processing
- **NeMo** — LLM training and customization

---

## UiPath

| Repository | Description | Stars |
|------------|-------------|-------|
| [**UiPath Community**](https://github.com/UiPath) | Official UiPath repositories including automation components. | Various |
| [**UiPath-Services/UiPath-AIChatbot**](https://github.com/UiPath-Services) | AI chatbot integration patterns with UiPath. | - |

### Key UiPath Services for RAG
- **AI Center** — ML model deployment and management
- **Document Understanding** — Intelligent document processing
- **Orchestrator** — Workflow automation
- **Integration Service** — API connectivity

---

## OpenAI

| Repository | Description | Stars |
|------------|-------------|-------|
| [**openai/openai-cookbook**](https://github.com/openai/openai-cookbook) | Official examples including RAG patterns, embeddings, and retrieval. | ~60K |
| [**openai/chatgpt-retrieval-plugin**](https://github.com/openai/chatgpt-retrieval-plugin) | Reference implementation for ChatGPT retrieval. | ~21K |

---

## Anthropic

| Repository | Description | Stars |
|------------|-------------|-------|
| [**anthropics/anthropic-cookbook**](https://github.com/anthropics/anthropic-cookbook) | Official recipes including Contextual Retrieval implementation. | ~5K |

**Key contribution:** Anthropic's Contextual Retrieval research (September 2024) demonstrated 49-67% retrieval failure reduction.

---

## How to Use These Resources

### For Learning
1. Start with **microsoft/generative-ai-for-beginners** for fundamentals
2. Move to **openai/openai-cookbook** for practical patterns
3. Study **Azure-Samples/azure-search-openai-demo** for production architecture

### For Implementation
1. Choose your cloud provider
2. Clone their reference implementation
3. Adapt to your use case
4. Add evaluation from the beginning

### For Advanced Topics
- **GraphRAG**: microsoft/graphrag
- **Guardrails**: NVIDIA/NeMo-Guardrails
- **GPU Optimization**: NVIDIA-AI-Blueprints/rag

---

## Staying Updated

Most of these repositories are actively maintained. Watch/star repositories relevant to your stack:

```bash
# Using GitHub CLI
gh repo clone Azure-Samples/azure-search-openai-demo
gh repo clone aws-samples/amazon-bedrock-samples
gh repo clone GoogleCloudPlatform/generative-ai
```

---

<div align="center">

[← Back to Resources](../README.md#-resources)

</div>
