# ☁️ Platform Guides

> **Practical RAG implementation guidance for major cloud and automation platforms**

---

## Overview

Each guide provides:
- 🔗 Links to official repositories (no reinventing the wheel)
- 🏗️ Architecture decision guidance
- 💰 Cost considerations
- ⚠️ Common pitfalls to avoid

---

## Available Guides

| Platform | Guide | Primary Repository |
|----------|-------|-------------------|
| ![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat&logo=amazon-aws&logoColor=white) | [AWS Bedrock](aws-bedrock.md) | [amazon-bedrock-samples](https://github.com/aws-samples/amazon-bedrock-samples) |
| ![Azure](https://img.shields.io/badge/Azure-0078D4?style=flat&logo=microsoft-azure&logoColor=white) | [Azure AI Search](azure-ai-search.md) | [azure-search-openai-demo](https://github.com/Azure-Samples/azure-search-openai-demo) |
| ![GCP](https://img.shields.io/badge/GCP-4285F4?style=flat&logo=google-cloud&logoColor=white) | [Google Vertex AI](gcp-vertex-ai.md) | [generative-ai](https://github.com/GoogleCloudPlatform/generative-ai) |
| ![Databricks](https://img.shields.io/badge/Databricks-FF3621?style=flat&logo=databricks&logoColor=white) | [Databricks Mosaic AI](databricks-mosaic.md) | [genai-cookbook](https://github.com/databricks/genai-cookbook) |
| ![UiPath](https://img.shields.io/badge/UiPath-FA4616?style=flat&logo=uipath&logoColor=white) | [UiPath Automation](uipath-automation.md) | [UiPath Docs](https://docs.uipath.com/) |

---

## Quick Comparison

| Capability | AWS | Azure | GCP | Databricks | UiPath |
|------------|-----|-------|-----|------------|--------|
| **Managed RAG** | Bedrock KB | AI Search | Vertex AI Search | Vector Search | Via Integration |
| **Vector Search** | OpenSearch, S3 Vectors | AI Search | Vector Search | Mosaic AI | External |
| **Foundation Models** | Claude, Llama, Titan, Nova | GPT-4, GPT-4o | Gemini | DBRX, Llama | External |
| **Document Processing** | Textract | Document Intelligence | Document AI | Spark | Document Understanding |
| **Hybrid Search** | OpenSearch | Built-in | Limited | Custom | Via Integration |
| **GraphRAG** | Custom | microsoft/graphrag | Custom | Custom | Custom |
| **HITL Native** | Step Functions | Logic Apps | Workflows | Jobs | Action Center |

---

## Choosing a Platform

```mermaid
flowchart TD
    A["What's your<br/>starting point?"] --> B{Existing<br/>cloud?}
    
    B -->|"AWS"| C["AWS Bedrock"]
    B -->|"Azure"| D["Azure AI Search"]
    B -->|"GCP"| E["Vertex AI"]
    B -->|"Databricks"| F["Mosaic AI"]
    B -->|"None"| G{Priority?}
    
    G -->|"Simplicity"| H["Azure or GCP<br/>(Best managed)"]
    G -->|"Model Choice"| I["AWS Bedrock<br/>(50+ models)"]
    G -->|"Data Platform"| J["Databricks<br/>(Lakehouse)"]
    G -->|"Automation"| K["UiPath<br/>(RPA + AI)"]
    
    style C fill:#FF9900
    style D fill:#0078D4
    style E fill:#4285F4
    style F fill:#FF3621
    style K fill:#FA4616
```

---

## Cross-Platform Considerations

### What's Portable
- ✅ Chunking strategies
- ✅ Evaluation frameworks (RAGAS, DeepEval)
- ✅ Prompt engineering patterns
- ✅ LangChain / LlamaIndex abstractions

### What's Platform-Specific
- ❌ Vector database APIs
- ❌ Managed RAG configurations
- ❌ Pricing models
- ❌ Security/compliance certifications

---

## Best Practices (All Platforms)

1. **Start with official samples** — Don't reinvent the wheel
2. **Implement evaluation early** — Platform-agnostic tools work everywhere
3. **Plan for hybrid search** — Check platform support upfront
4. **Monitor costs** — Token costs compound quickly
5. **Design for portability** — Use abstraction layers where possible

---

<div align="center">

[← Back to Documentation](../README.md)

</div>
