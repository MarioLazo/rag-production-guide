# 🏭 Agent Factory Reference: Regulated Industries Edition

**Healthcare · Finance · Supply Chain & Distribution**

A practical directory of tools, frameworks, datasets, and standards for building AI agents in production environments where compliance matters.

**Curated by Mario Lazo · February 2026**

---

## 📣 What This Is

<!-- 
💡 PLAIN ENGLISH: This is a starting point, not a complete manual.
Think of it like a well-organized toolbox, we've gathered the tools that 
actually work, but you still need to know how to use them for your specific job.
-->

This reference started as a simple list. It grew into what I wish had existed when I was in front of hospital CIOs and bank risk committees trying to explain why most AI pilots fail, not because the technology is bad, but because nobody had a map.

If it saves one team from rebuilding what already exists, or helps one practitioner find the right ontology before spending six months on the wrong one, it was worth the effort.

**, Mario Lazo**

---

## 🧭 Before You Begin: Setting Expectations

### This Is a Starting Point, Not a Complete Manual

<!-- 
💡 PLAIN ENGLISH: An "Agent Factory" is a system for building and running 
AI assistants that can take actions on your behalf, like automating 
paperwork, analyzing data, or answering questions from your systems.
-->

**What is an "Agent Factory"?**
An Agent Factory is a structured approach to building AI systems that can take actions, reading documents, querying databases, making recommendations, or automating workflows. Unlike simple chatbots that just answer questions, these agents interact with your real systems.

**Why does this require expertise?**
Building agents for regulated industries (healthcare, finance, supply chain) isn't like building a demo. In these environments:

- **A wrong answer can cause real harm**: misdiagnosed patients, bad investment advice, supply chain failures
- **Regulations have teeth**: HIPAA violations can cost millions, SEC infractions can end careers
- **Trust is everything**: one bad AI decision can destroy years of institutional credibility

**What you'll need beyond this reference:**

| What | Why |
|------|-----|
| **Domain expertise** | Someone who deeply understands healthcare workflows, financial regulations, or supply chain operations |
| **Compliance knowledge** | A person (or team) who knows your specific regulatory obligations, not generic AI ethics, but actual legal requirements |
| **Technical implementation skills** | Engineers who can build, test, deploy, and monitor production systems |
| **Organizational buy-in** | Stakeholders who understand that AI adoption is a process, not a one-time installation |

> **Bottom line**: This reference shows you *what tools exist*. You still need people who understand *how to use them responsibly* in your specific context.

### What This Guide Is and Isn't

| ✅ This Guide IS | ❌ This Guide IS NOT |
|------------------|---------------------|
| A curated starting point | A complete implementation manual |
| A map of available tools | A guarantee that tools will work for you |
| A compliance checklist starting point | Legal or regulatory advice |
| A living document that evolves | A one-time read-and-forget resource |
| A community effort | The opinion of one person |

### Who Should Use This

- **Technical leads** evaluating agent frameworks for regulated environments
- **Consultants** advising healthcare, finance, or supply chain organizations on AI adoption
- **Product managers** scoping AI capabilities with compliance in mind
- **Compliance officers** understanding what questions to ask about AI systems
- **Researchers** seeking domain-specific datasets and benchmarks

---

## ⚠️ Disclaimer

**Read this before using anything in this guide.**

### Not Legal or Compliance Advice

This is a reference document, a collection of links and descriptions. It is not a product recommendation, legal opinion, or compliance certification. Nothing here substitutes for:

- Your organization's legal counsel
- Your compliance team's evaluation
- Your security team's assessment
- The vendor's own documentation and terms

### Things Change Fast

I will review and update this list **at minimum every two months**. But the AI space moves faster than any document can keep up with:

- Repositories get abandoned
- Standards get superseded
- Regulations change
- Better tools appear weekly
- Companies get acquired or shut down

**If something is outdated, wrong, or missing: open a PR or file an issue.** That's the whole point.

### Data Use Agreements Matter

Several datasets listed here (particularly MIMIC) have strict data use agreements that **prohibit transmission to third-party cloud APIs**. Always read the DUA before touching sensitive data. Violating a DUA can end careers and trigger legal action.

### No Endorsements

Listing a tool here means I found it useful or saw it used in production. It does not mean:

- I have a financial relationship with the creators
- It will work for your use case
- It meets your compliance requirements
- It's the best option available

HIPAA, SOC 2, FDA SaMD, SEC/FINRA, EU AI Act, and other frameworks impose obligations that no curated GitHub list can satisfy. You still have to do the work.

---

## 🤝 Community Curation: Help Each Other

This guide works best as a **community effort**. The AI landscape is too broad and too fast for any one person to maintain well.

**If you're actively building in healthcare AI, finance AI, or supply chain AI: your contributions matter.**

### How to Contribute

| Action | When to Use |
|--------|-------------|
| **File an issue** | Flag outdated links, broken repos, incorrect descriptions, or resources that should be removed |
| **Open a pull request** | Add a repo, paper, dataset, MCP server, or ontology, follow the format in this guide |
| **Join GitHub Discussions** | Suggest new sections, debate architecture choices, share what's working in production |
| **Write a comment** | If you've used something listed here, share your experience, what worked, what didn't |

### What Makes a Good Contribution

**Include:**
- Resources with demonstrated production use OR strong research backing
- Active maintenance (check the last commit date, repos abandoned >18 months are lower priority)
- Relevance to **regulated environments**, tools that don't address compliance, auditability, or domain specificity are lower priority
- Plain-language descriptions a practitioner can read in 60 seconds and understand

**Avoid:**
- Vaporware or pre-launch announcements
- Tools that only work in demos
- Resources behind paywalls (unless exceptional value)
- Self-promotion without substance

### Curators Needed

| Domain | What We Need |
|--------|--------------|
| **Healthcare AI** | EHR integration, clinical NLP, FDA SaMD compliance |
| **Finance AI** | Quantitative research, risk modeling, regulatory reporting |
| **Supply Chain** | Warehouse automation, demand forecasting, IoT/robotics |
| **Ontologies** | Domain terminology standards, knowledge graph architecture |
| **MCP Servers** | New servers, integration patterns, security considerations |
| **Academic Papers** | Identifying landmark papers as the field publishes faster than anyone can read |

**Recognition**: Maintainers who make consistent, high-quality contributions over 6+ months will be listed as co-curators.

---

## 📚 Recommended Companion References

This guide focuses on AI agents for regulated industries. These complementary resources cover areas we don't:

### General AI/ML Engineering

| Resource | What It Covers | Link |
|----------|---------------|------|
| **Awesome Machine Learning** | Foundational ML libraries and tools | [github.com/josephmisiti/awesome-machine-learning](https://github.com/josephmisiti/awesome-machine-learning) |
| **ML Papers of the Week** | Current research worth reading | [github.com/dair-ai/ML-Papers-of-the-Week](https://github.com/dair-ai/ML-Papers-of-the-Week) |
| **Papers With Code** | Research papers with implementations | [paperswithcode.com](https://paperswithcode.com/) |
| **Hugging Face Hub** | Models, datasets, demos | [huggingface.co](https://huggingface.co/) |

### LLM-Specific Resources

| Resource | What It Covers | Link |
|----------|---------------|------|
| **LLM Course** | Comprehensive LLM learning path | [github.com/mlabonne/llm-course](https://github.com/mlabonne/llm-course) |
| **Awesome LLM** | Curated LLM tools and research | [github.com/Hannibal046/Awesome-LLM](https://github.com/Hannibal046/Awesome-LLM) |
| **Open LLM Leaderboard** | Model benchmarks and comparisons | [huggingface.co/spaces/open-llm-leaderboard](https://huggingface.co/spaces/open-llm-leaderboard/open_llm_leaderboard) |

### Prompt Engineering & RAG

| Resource | What It Covers | Link |
|----------|---------------|------|
| **Prompt Engineering Guide** | Prompting techniques that work | [github.com/dair-ai/Prompt-Engineering-Guide](https://github.com/dair-ai/Prompt-Engineering-Guide) |
| **Awesome RAG** | Retrieval-augmented generation patterns | [github.com/frutik/Awesome-RAG](https://github.com/frutik/Awesome-RAG) |
| **LangChain Templates** | Production-ready agent patterns | [github.com/langchain-ai/langchain/tree/master/templates](https://github.com/langchain-ai/langchain/tree/master/templates) |

### AI Safety & Governance

| Resource | What It Covers | Link |
|----------|---------------|------|
| **NIST AI RMF Playbook** | Risk management framework implementation | [airc.nist.gov/AI_RMF_Knowledge_Base](https://airc.nist.gov/AI_RMF_Knowledge_Base/Playbook) |
| **AI Incident Database** | Documented AI failures and harms | [incidentdatabase.ai](https://incidentdatabase.ai/) |
| **Responsible AI Toolbox** | Microsoft's fairness and explainability tools | [github.com/microsoft/responsible-ai-toolbox](https://github.com/microsoft/responsible-ai-toolbox) |

### Data Engineering

| Resource | What It Covers | Link |
|----------|---------------|------|
| **Awesome Data Engineering** | Data pipeline tools and patterns | [github.com/igorbarinov/awesome-data-engineering](https://github.com/igorbarinov/awesome-data-engineering) |
| **Great Expectations** | Data validation and documentation | [github.com/great-expectations/great_expectations](https://github.com/great-expectations/great_expectations) |
| **dbt** | Data transformation in warehouses | [github.com/dbt-labs/dbt-core](https://github.com/dbt-labs/dbt-core) |

### MLOps & Deployment

| Resource | What It Covers | Link |
|----------|---------------|------|
| **Awesome MLOps** | Production ML operations | [github.com/visenger/awesome-mlops](https://github.com/visenger/awesome-mlops) |
| **MLflow** | Experiment tracking and model registry | [github.com/mlflow/mlflow](https://github.com/mlflow/mlflow) |
| **Weights & Biases** | Experiment tracking and monitoring | [wandb.ai](https://wandb.ai/) |

> **Why these?** They fill gaps. This reference focuses on domain-specific tools for regulated industries. The resources above cover general ML/AI infrastructure that you'll also need.

---

## 📌 How to Use This Guide

### Quick Navigation

| Section | What You'll Find | Jump To |
|---------|------------------|---------|
| **Before You Begin** | What this guide is, who should use it, what you need | [→ Setting Expectations](#-before-you-begin-setting-expectations) |
| **1. Agent Frameworks** | Orchestration tools: LangChain, AutoGen, CrewAI, etc. | [→ Section 1](#1--ai-agent-frameworks--orchestration) |
| **2. Finance Repos** | FinGPT, FinRL, Qlib, trading systems | [→ Section 2](#2--finance--core-repos) |
| **3. Healthcare Repos** | Clinical NLP, EHR integration, medical LLMs | [→ Section 3](#3--healthcare--core-repos) |
| **4. Supply Chain** | Warehouse automation, logistics, forecasting | [→ Section 4](#4--supply-chain-warehouse--distribution) |
| **5. MCP Servers (Finance)** | SEC EDGAR, market data, Bloomberg connectors | [→ Section 5](#5--mcp-servers--finance) |
| **6. MCP Servers (Healthcare)** | FHIR, EHR, clinical data connectors | [→ Section 6](#6--mcp-servers--healthcare) |
| **7. Ontologies** | FIBO, SNOMED, UMLS, GS1, domain vocabularies | [→ Section 7](#7--ontologies--knowledge-graphs) |
| **8. Datasets** | MIMIC, FAERS, FRED, M5, training data | [→ Section 8](#8--datasets) |
| **9. Papers & Learning** | Research, associations, where to learn more | [→ Section 9](#9--papers-associations--where-to-learn) |
| **10. Regulations** | HIPAA, FDA, SEC, EU AI Act, compliance checklists | [→ Section 10](#10--%EF%B8%8F-regulatory-reference-guide) |
| **Community Adoption** | How to contribute, spread the word, improve this guide | [→ Recommendations](#-recommendations-for-maximum-community-adoption) |

### Search Tips

- Use `Ctrl+F` / `Cmd+F` to search for specific tools or terms
- Keywords are written in plain English, search for what you need, not acronyms
- Each entry includes a one-line description of what it does

### Reading Time

- **Skim the tables**: ~10 minutes
- **Read descriptions**: ~45 minutes
- **Deep dive with links**: Several hours

---

## 1 · 🤖 AI Agent Frameworks & Orchestration

<!-- 
💡 PLAIN ENGLISH: Think of these as the "operating systems" for AI agents.
Just like Windows or macOS lets you run different applications, these 
frameworks let you build and run AI agents that can do different tasks.
They handle the plumbing so you can focus on what the agent actually does.
-->

The **foundational layer** of any Agent Factory, frameworks that coordinate agents, manage memory, route tools, and handle orchestration logic.

> **In simple terms:** These tools help you build AI assistants that can remember conversations, use other software tools, and work together with other AI assistants to complete complex tasks.

| Framework | Link | Best For |
|-----------|------|----------|
| **LangChain** | [github.com/langchain-ai/langchain](https://github.com/langchain-ai/langchain) | Full-stack agent pipelines, RAG, tool use |
| **LangGraph** | [github.com/langchain-ai/langgraph](https://github.com/langchain-ai/langgraph) | Stateful multi-agent workflows, cycles, human-in-loop |
| **AutoGen (Microsoft)** | [github.com/microsoft/autogen](https://github.com/microsoft/autogen) | Multi-agent conversations, code execution, group chat |
| **CrewAI** | [github.com/crewAIInc/crewAI](https://github.com/crewAIInc/crewAI) | Role-based crew patterns, fast to prototype |
| **Semantic Kernel** | [github.com/microsoft/semantic-kernel](https://github.com/microsoft/semantic-kernel) | Enterprise .NET/Python, plugin architecture, Microsoft stack |
| **Haystack** | [github.com/deepset-ai/haystack](https://github.com/deepset-ai/haystack) | Production RAG pipelines, document-heavy workflows |
| **DSPy** | [github.com/stanfordnlp/dspy](https://github.com/stanfordnlp/dspy) | Programmatic LLM optimization, self-improving pipelines |
| **Swarm (OpenAI)** | [github.com/openai/swarm](https://github.com/openai/swarm) | Lightweight handoff-based multi-agent patterns |
| **Agno (PhiData)** | [github.com/agno-agi/agno](https://github.com/agno-agi/agno) | Fast, lightweight agent library with memory and tools |
| **ControlFlow** | [github.com/PrefectHQ/ControlFlow](https://github.com/PrefectHQ/ControlFlow) | Task-centric agents, Prefect-integrated, observable |
| **Mastra** | [github.com/mastra-ai/mastra](https://github.com/mastra-ai/mastra) | TypeScript-native, workflow + memory |
| **mem0** | [github.com/mem0ai/mem0](https://github.com/mem0ai/mem0) | Long-term agent memory layer, cross-session persistence |

### Choosing for Regulated Industries

**Healthcare**: LangGraph + Haystack gives auditability and traceable reasoning chains, critical for clinical decision support where you must show *why* an agent made a recommendation.

**Finance**: AutoGen or Semantic Kernel integrates well with enterprise Microsoft infrastructure; code execution sandboxing supports quantitative analysis while staying isolated from production systems.

**Agent Factory pattern (production-scale multi-agent)**: LangGraph for orchestration + mem0 for memory + Haystack for retrieval is a proven combination.

**Supply Chain**: CrewAI or LangGraph for inventory management agents; AutoGen for multi-company negotiation scenarios where agents represent different organizational units.

---

## 2 · 💰 Finance: Core Repos

<!-- 
💡 PLAIN ENGLISH: These are specialized AI tools built specifically for 
financial work, analyzing market data, reading SEC filings, understanding 
financial news, and helping with investment research. They understand 
financial language and concepts better than general-purpose AI.
-->

> **In simple terms:** Tools that help AI understand money, markets, and financial documents, like having an analyst who can read millions of pages instantly.

---

**[FinGPT](https://github.com/AI4Finance-Foundation/FinGPT)**
> _Open-source financial LLMs with continuous fine-tuning pipelines_

The standout feature isn't the models themselves, it's the **continuous update mechanism**. Financial markets are relentlessly current; a model trained six months ago on earnings calls is already stale. FinGPT solves this with automated pipelines that ingest market news, SEC filings, and social sentiment to fine-tune lightweight models (LLaMA, Falcon) on an ongoing basis. Most relevant for **sentiment analysis agents** and **market intelligence tools**.

---

**[FinNLP](https://github.com/AI4Finance-Foundation/FinNLP)**
> _NLP data pipelines and benchmarks for financial text_

The data layer that feeds FinGPT and similar models. Standardized connectors for financial news APIs, SEC EDGAR, Reddit/social sentiment, and earnings call transcripts, all formatted for LLM consumption. Includes NLP benchmarks for financial tasks: NER for companies and people, sentiment classification, and QA over financial documents. Saves weeks of ETL work when building **document intelligence agents**.

---

**[TradingAgents](https://github.com/virattt/ai-hedge-fund)**
> _Multi-agent trading system with specialized analyst roles_

A fully realized multi-agent architecture where distinct agents take on analyst personas: fundamentals analyst, technical analyst, sentiment analyst, risk manager, and portfolio manager who synthesizes their recommendations. Best open-source demonstration of the **role-based agent factory pattern** in finance. Excellent reference architecture for decision-support systems where multiple specialist AI perspectives are reconciled before a human makes a final call.

---

**[AI Hedge Fund](https://github.com/virattt/ai-hedge-fund)**
> _Complete AI-powered investment research and portfolio simulation_

End-to-end simulation of an AI-driven hedge fund: data ingestion, LLM-based analysis, trade signal generation, portfolio tracking. Not production-ready for live trading, but the most complete **reference implementation** for understanding how all the pieces fit together.

---

**[FinRL](https://github.com/AI4Finance-Foundation/FinRL)**
> _Deep reinforcement learning for quantitative finance_

The go-to library for RL-based trading strategy development. Provides a standardized gym environment for financial markets, multiple RL algorithm implementations (PPO, SAC, TD3), and integration with real market data sources. Most relevant for **algorithmic trading teams** and **quantitative researchers**. Requires extensive backtesting before any production consideration.

---

**[FinRobot](https://github.com/AI4Finance-Foundation/FinRobot)**
> _AI agent platform connecting finance data to LLMs_

Middleware between raw financial data and conversational AI. Agent SDK with built-in connectors to market data APIs, pre-built financial analysis tools (DCF modeling, ratio analysis, peer comparison), and agent templates for common finance workflows. If your team is building a **financial analyst copilot** or **client-facing research assistant**, FinRobot provides domain-specific tooling that generic agent frameworks lack.

---

**[Qlib (Microsoft)](https://github.com/microsoft/qlib)**
> _Enterprise quantitative investment AI platform from Microsoft Research_

Microsoft Research's production-grade quant platform, the most enterprise-ready option on this list. Covers the entire quant workflow: data handling, feature engineering, model training, backtesting, portfolio optimization, and live trading integration. Modular architecture allows replacing individual components. Best for **quantitative research teams** at institutional investors.

---

**[FinRL-DeepSeek](https://github.com/AI4Finance-Foundation/FinRL-DeepSeek)**
> _FinRL enhanced with DeepSeek reasoning models_

Integrates FinRL's RL infrastructure with DeepSeek's chain-of-thought reasoning. More interpretable trading rationales, a significant advantage in regulated environments where you need to **explain why an AI system recommended a trade**. Directly addresses core compliance challenges in AI-assisted trading.

---

**[AI4Finance Foundation](https://github.com/AI4Finance-Foundation)**
> _Umbrella organization for all open-source finance AI research_

Parent org for FinGPT, FinRL, FinNLP, FinRobot, and related projects. Follow as an organization to track what's coming next in finance AI.

---

**[FinLLM-Leaderboard / PIXIU](https://github.com/chancefocus/PIXIU)**
> _Benchmarking LLMs on financial tasks_

Before deploying any LLM in finance, know how it performs on domain-specific tasks: financial QA, NER, sentiment. PIXIU provides standardized benchmarks and a leaderboard for objective model comparison. Critical for **model selection decisions** and for justifying those choices to compliance and risk teams.

---

**[Open-Finance-Lab](https://github.com/Open-Finance-Lab)**
> _Collaborative research lab for open financial AI_

Focused on open, reproducible research in financial AI. Valuable for teams wanting to access peer-reviewed paper implementations or contribute to the community.

---

**[FinanceBench](https://github.com/patronus-ai/financebench)**
> _QA benchmark for financial reasoning over real documents_

Tests LLM performance on questions from actual 10-K and 10-Q filings, numerical reasoning, document understanding, financial logic. Use it to **validate models before finance deployments**.

---

**[OpenBB Terminal](https://github.com/OpenBB-finance/OpenBBTerminal)**
> _Open-source Bloomberg Terminal alternative_

Aggregates 100+ financial data sources. Useful as both a **reference data layer** for agent builds and a standalone analyst tool. Increasingly integrating with AI agents through its API layer.

---

**[500 AI Agents Projects: Finance Section](https://github.com/ashishpatel26/500-AI-Agents-Projects)**
> _Curated use cases with working implementations_

Concrete, runnable examples for: fraud detection, risk assessment, customer support, compliance monitoring, and more. Best as an **idea catalog** when scoping new agent capabilities.

---

## 3 · 🏥 Healthcare: Core Repos

<!-- 
💡 PLAIN ENGLISH: These are AI tools designed for medical and clinical 
settings, reading patient records, understanding medical terminology, 
helping with diagnoses, and automating paperwork. They're built to 
understand healthcare-specific language and workflows.

⚠️ IMPORTANT: Healthcare AI has strict regulations (HIPAA, FDA) and
can directly impact patient safety. These tools require careful 
evaluation and proper clinical oversight before any use.
-->

> **In simple terms:** AI tools that understand medical language and healthcare workflows, like having a medical librarian and administrator who never sleeps.

---

**[Awesome AI Agents for Healthcare](https://github.com/AgenticHealthAI/Awesome-AI-Agents-for-Healthcare)**
> _The definitive curated list of agentic AI in clinical settings, updated weekly_

The healthcare equivalent of AI4Finance Foundation, continuously updated catalog covering clinical decision support agents, EHR-interacting systems, multi-agent diagnostic frameworks, surgical AI, mental health agents, and practical tooling (MCP servers, FHIR tools, prior auth agents, clinical trial automation). Start here when scoping any healthcare AI project.

---

**[Awesome AI Agents in Medicine (AIM-Research-Lab)](https://github.com/AIM-Research-Lab/Awesome-AI-Agents-Medicine)**
> _Systematic taxonomy and survey of medical LLM agent systems_

Backed by a formal peer-reviewed survey (TechRxiv, 2025), provides a structured **taxonomy of medical agent architectures**: single-agent, multi-agent, tool-augmented, RAG-augmented, multimodal. More academically rigorous, valuable for justifying architectural choices to clinical or regulatory stakeholders.

---

**[MedLLMsPracticalGuide](https://github.com/AI-in-Health/MedLLMsPracticalGuide)**
> _Nature Reviews Bioengineering, complete guide to medical LLM applications_

Accompanies a comprehensive review published in Nature Reviews Bioengineering. Covers model architectures (BioBERT, ClinicalBERT, BioGPT, MedPaLM), training approaches, evaluation benchmarks, and deployment considerations. Essential for **selecting a foundation model** for healthcare.

---

**[Awesome Healthcare Foundation Models](https://github.com/Jianing-Qiu/Awesome-Healthcare-Foundation-Models)**
> _Curated large AI models across every clinical modality_

Organized by modality: language models for clinical text, vision models for medical imaging, audio models for clinical conversations, multimodal models combining them. When your agent needs to process something other than text, an X-ray, ECG signal, pathology slide, this is where to find the relevant pre-trained model.

---

**[OpenMEDLab](https://github.com/openmedlab)**
> _Open platform for medical foundation models_

Multi-modal model hub covering imaging, NLP, bioinformatics, with evaluation benchmarks alongside models. For organizations working with Chinese-language patient populations, OpenMEDLab's multilingual support is particularly strong.

---

**[HealthFlow](https://github.com/yhzhu99/HealthFlow)**
> _Self-evolving AI agent with meta-planning for healthcare research_

An agent that learns from its own task history and evolves planning strategies over time. Particularly relevant for **healthcare research automation**, literature review, hypothesis generation, data analysis orchestration. Important: self-modification requires audit trails in clinical settings.

---

**[AgentClinic](https://agentclinic.github.io)**
> _Multimodal benchmark for AI agents in simulated clinical environments_

The most rigorous **evaluation framework** for clinical AI agents in open source. Grounded in USMLE Step 2/3 cases and NEJM case challenges. Also measures how cognitive biases affect diagnostic accuracy, directly relevant to FDA AI/ML bias evaluation guidance.

---

**[Awesome Specialized Medical LLMs](https://github.com/FreedomIntelligence/Awesome-Specialized-Medical-LLMs)**
> _Disease-specific LLMs organized by ICD-10 chapters_

When your agent needs expertise in a specific clinical area, this is your first stop. Organized by ICD-10 categories, maps specialty-specific models (Zodiac for cardiology, EpilepsyLLM for neurology) so you can find and evaluate them efficiently.

---

**[Medical Model Library](https://github.com/ExpertOpsAI/MedicalModelLibrary)**
> _Pre-trained healthcare AI models inventory_

Practical inventory of ready-to-use models across clinical NLP (BioBERT, ClinicalBERT, SciBERT, BioGPT) and medical imaging (U-Net, nnU-Net). A **model shopping list** organized by task.

---

**[LLM Agents in Scientific Discovery](https://github.com/zjlrock777/Awesome-LLM-Agents-Scientific-Discovery)**
> _AI agents for biomedical research, drug discovery, and genomics_

Bridges clinical AI and research AI. Covers agents for literature synthesis, hypothesis generation, experimental design, multi-omics analysis, and drug repurposing. Particularly relevant for **pharmaceutical and biotech teams**.

---

**[Agentic Clinical Dialogue](https://github.com/xqz614/Awesome-Agentic-Clinical-Dialogue)**
> _Medical agents for clinical conversation and patient interaction_

Focused on the conversational interface layer: how agents structure doctor-patient dialogue, gather symptoms, handle clinical uncertainty. Covers clinician-facing tools (SOAP note completion) and patient-facing tools (symptom checkers, medication adherence). Includes safety evaluation frameworks for clinical dialogue agents.

---

**[AI Agents for Medical Diagnostics](https://github.com/ahmadvh/AI-Agents-for-Medical-Diagnostics)**
> _Multi-specialist LLM agent system for complex case analysis_

Multi-specialist clinical agents running in parallel (cardiologist, pulmonologist, general medicine), each analyzing independently, then synthesizing findings. Mirrors how clinical consultation works at major medical centers. Valuable reference architecture for **clinical decision support tools**.

---

## 4 · 📦 Supply Chain, Warehouse & Distribution

<!-- 
💡 PLAIN ENGLISH: These tools help AI manage the flow of goods, from 
predicting what products you'll need, to figuring out the best shipping 
routes, to managing warehouse inventory. Think of it as AI that helps 
get the right stuff to the right place at the right time.
-->

> **In simple terms:** AI tools for moving and managing physical goods, like having a logistics coordinator who can see the entire supply chain at once.

> **Why this section exists**: Supply chain and logistics is one of the fastest-growing domains for AI agent deployment. Real-time data (IoT, WMS, logistics APIs), hard optimization problems (routing, inventory, scheduling), and high-stakes decisions (disruptions propagate fast) make it a natural fit for agentic AI. Unlike healthcare and finance, supply chain has fewer regulatory constraints, which means faster deployment cycles but also less structured best-practice guidance.

---

### 4.1 Core Repos & Frameworks

---

**[Responsive AI Clusters in Supply Chain](https://github.com/Appointat/Responsive-AI-Clusters-in-Supply-Chain)**
> _Multi-agent system for real-time adaptive supply chain coordination_

A complete multi-agent implementation for **warehouse resource allocation and outlet replenishment**. Agents represent individual outlets and a central hub, coordinating in real-time to manage inventory based on demand signals, events, and capacity constraints. One of the most complete open-source demonstrations of the multi-agent pattern applied to actual logistics operations. Built with CAMEL-AI's multi-agent framework. Excellent starting architecture for **autonomous replenishment systems**.

---

**[Intelligent Supply Chain Management (Microsoft Azure)](https://github.com/MSUSAzureAccelerators/Intelligent-Supply-Chain-Management)**
> _Azure ML + Ray Cluster + PowerApps supply chain optimization accelerator_

Microsoft's Azure accelerator for supply chain AI, leverages deep learning forecasting, distributed computing via Ray Cluster, and simulation environments to model inventory optimization. Integrates with PowerApps for business user interaction. Best for teams in the Azure ecosystem building **enterprise-grade demand forecasting and inventory simulation** systems. Includes infrastructure-as-code for deployment at scale.

---

**[frePPLe: Open Source Supply Chain Planning](https://github.com/frePPLe/frepple)**
> _Production-ready open-source supply chain planning platform_

A full-featured supply chain planning system implementing time series forecasting, production scheduling, and inventory optimization using theory of constraints, pull-based planning, and lean manufacturing best practices. Unlike most research repos, frePPLe is **actually used in production** by manufacturers and distributors. Available as Docker container, Ubuntu package, or from source. Strong foundation for building **planning agents** on top of a robust optimization engine.

---

**[Supply Chain Optimization (Python)](https://github.com/ankitrajsh/Supply-Chain-Optimization)**
> _ML for demand forecasting, inventory, logistics, and supplier selection_

A practical, well-structured repo covering the core ML problems in supply chain: demand forecasting, inventory level optimization, route optimization, supplier ranking, and production scheduling. Includes Jupyter notebooks and datasets. Good starting point for data science teams **new to supply chain AI**.

---

**[Supply Chain Forecasting with Deep Learning](https://github.com/milonigada09/Supply-Chain-forecasting-deep-learning)**
> _CNN-LSTM and Transformer models for demand forecasting_

Rigorous comparison of deep learning architectures (GRU, CNN+LSTM, Transformers) for demand forecasting, with focus on inventory optimization and replenishment. The CNN+LSTM combination consistently outperforms in experiments. Useful for teams benchmarking **forecasting model architectures** before committing.

---

**[SupplyChain-AI (RAG + LLM)](https://github.com/VaishnaviThakre/SupplyChain-AI)**
> _RAG-powered LLM chatbot for supply chain Q&A_

An AI-powered conversational interface combining LLMs, RAG architecture, and predictive analytics. Useful reference for teams building **natural language interfaces** over supply chain data, allowing planners to query inventory status, forecasts, and supplier data in plain English.

---

**[InvAgent (arXiv 2024)](https://arxiv.org/abs/2407.11966)**
> _LLM agents for zero-shot inventory management_

Research implementation of dialogue-driven LLM agents for inventory management tasks: demand forecasting, safety-stock calculation, and replenishment ordering, all via natural language without task-specific fine-tuning. Demonstrates that general-purpose LLM agents can handle inventory management through zero-shot learning, with implications for **rapid deployment across diverse product categories** without custom training per SKU.

---

### 4.2 Key Supply Chain AI Use Cases & Agent Patterns

| Use Case | Agent Pattern | Key Tools |
|----------|--------------|-----------|
| **Demand Forecasting** | Single forecasting agent + time-series tools | Prophet, N-HiTS, TFT, XGBoost |
| **Inventory Optimization** | EOQ/safety stock agent with real-time data | InventoryPy, frePPLe, custom RL |
| **Supplier Risk Monitoring** | Multi-agent disruption monitoring with news + KG | LangGraph + NewsAPI + graph DB |
| **Route Optimization** | Combinatorial optimization agent | OR-Tools (Google), VRPy |
| **Warehouse Picking** | Embodied agents + robotics interfaces | ROS2, Isaac Sim, OpenAI Gym |
| **Procurement Automation** | Negotiation agents across supplier APIs | CrewAI, AutoGen |
| **Demand Sensing** | Real-time signal aggregation agent | Kafka + LLM summarization |
| **Digital Twin Simulation** | Simulation agent + LLM planner | NVIDIA Omniverse, AnyLogic |

---

### 4.3 Supply Chain Standards & Ontologies

- **GS1 Standards** (gs1.org), Global supply chain language: barcodes, RFID, EDI, product data. If your agents identify products, locations, or shipments across trading partners, GS1 is the standard.
- **SCOR Model**: APICS/ASCM framework for supply chain process standardization; defines Plan, Source, Make, Deliver, Return, Enable processes and their KPIs.
- **UN/CEFACT**: UN trade and logistics standards; EDI message formats for cross-border trade.
- **Open Supply Hub** (opensupplyhub.org), Open database of supply chain facility data with standardized identifiers.

---

### 4.4 Supply Chain Datasets

| Dataset | Access | Description |
|---------|--------|-------------|
| **M5 Forecasting (Walmart)** | [Kaggle](https://www.kaggle.com/c/m5-forecasting-accuracy) | 5 years Walmart sales across 3 US states; 42,840 time series. Gold standard for demand forecasting benchmarks. |
| **Favorita Grocery Sales** | [Kaggle](https://www.kaggle.com/c/favorita-grocery-sales-forecasting) | Ecuadorian grocery sales with promotions, oil prices, holidays. |
| **UCI Supply Chain Datasets** | [archive.ics.uci.edu](https://archive.ics.uci.edu/) | Multiple SCM classification and regression datasets. |
| **US Freight Data** | [data.gov](https://www.data.gov/) | Government freight, shipping, and logistics datasets. |
| **Open Supply Hub** | [opensupplyhub.org](https://opensupplyhub.org/) | Global open database of supply chain facilities with standardized identifiers. |

---

## 5 · 🔌 MCP Servers: Finance

<!-- 
💡 PLAIN ENGLISH: MCP servers are like "power adapters" that let AI agents 
plug into real data sources and services. Instead of the AI just making 
things up, it can actually look up real SEC filings, pull live stock 
prices, or read actual bank statements through these connections.
-->

> **In simple terms:** These are the cables that connect AI agents to real financial data, so they're working with facts, not guesses.

MCP (Model Context Protocol) servers are the **tool layer** of your agent stack, exposing structured, auditable APIs that agents use to query data, execute actions, and interact with external systems.

---

**[SEC EDGAR MCP](https://github.com/stefanoamorelli/sec-edgar-mcp)**
> _Direct AI access to SEC filings with exact numeric precision_

Real-time access to the full SEC EDGAR database: 10-K/10-Q filings, 8-K events, insider trading (Form 3/4/5), XBRL-parsed financial statements. Responses include source URLs for verification, critical for compliance audits. Exact numeric precision design prevents rounding errors in quantitative workflows.

```json
{
  "mcpServers": {
    "sec-edgar": {
      "command": "docker",
      "args": ["run", "-i", "--rm", "stefanoamorelli/sec-edgar-mcp:latest"]
    }
  }
}
```

---

**[EdgarTools + MCP Server](https://github.com/dgunning/edgartools)**
> _AI-native SEC EDGAR library with built-in MCP server_

10-30x faster than alternatives for EDGAR data extraction. Production MCP server included. Parses XBRL statements, tracks insider trading via Form 4, extracts institutional holdings from 13-F filings. Text formatted for LLM context, not raw HTML.

```json
{
  "mcpServers": {
    "edgartools": {
      "command": "python",
      "args": ["-m", "edgar.ai"],
      "env": {"EDGAR_IDENTITY": "Your Name your@email.com"}
    }
  }
}
```

---

**[Financial MCP Suite: 8 Specialized Servers](https://github.com/luisrincon23/sec-mcp)**
> _Institutional-grade financial research platform, 8 MCP servers in one_

Eight servers replicating institutional research capabilities: SEC scraping, news sentiment, analyst ratings, institutional holdings, alternative data, industry assumptions, economic data, and research administration. Best for **comprehensive equity research agents** needing all data types integrated.

---

**[Financial Modeling Prep MCP Server](https://github.com/imbenrabi/Financial-Modeling-Prep-MCP-Server)**
> _Complete financial data platform with 20+ toolsets_

Covers quotes, financials, earnings calendar, analyst estimates, insider trades, congressional trading, ESG scores, technical indicators, crypto, forex, and commodities. Dynamically enables/disables toolsets to reduce token overhead. Useful for **wealth management and advisory agents**.

---

**[Bloomberg MCP (blpapi-mcp)](https://github.com/djsamseng/blpapi-mcp)**
> _AI agent access to Bloomberg Terminal data_

For organizations with Bloomberg Terminal access, bridges Bloomberg's professional data to AI agents. Bloomberg has built enterprise middleware on top of MCP for SSO, audit trails, rate limiting, and compliance, a preview of where institutional finance AI infrastructure is heading.

---

**[Financial Datasets MCP](https://github.com/financial-datasets/mcp-server)**
> _Stock market API integration for AI agents_

Clean, simple MCP interface for stock market data, prices, fundamentals, financials. Good starting point for teams building **internal analytics agents**.

---

## 6 · 🔌 MCP Servers: Healthcare

<!-- 
💡 PLAIN ENGLISH: These connections let AI agents read and write to 
electronic health record (EHR) systems like Epic or Cerner. They use 
FHIR, a standard way for health systems to share data, so the AI 
can actually look up real patient information (with proper authorization).

⚠️ CRITICAL: Healthcare data is protected by law. Any connection to 
patient data requires proper security, access controls, and compliance review.
-->

> **In simple terms:** Cables that connect AI to hospital record systems, allowing the AI to look up real patient data (when authorized) instead of making things up.

---

**[FHIR MCP Server (WSO2)](https://github.com/wso2/fhir-mcp-server)**
> _Production-grade MCP bridge between AI agents and any FHIR server_

Most enterprise-ready FHIR MCP server available. Supports OAuth 2.0 for Epic, Cerner, and other major EHR vendors. Full CRUD across all major FHIR resource types. Compatible with Claude Desktop, VS Code MCP, and any MCP client. For teams integrating with **Epic or Cerner EHR systems**, this handles OAuth complexity that trips most teams up.

---

**[FHIR MCP Server (The Momentum)](https://github.com/the-momentum/fhir-mcp-server)**
> _Developer-first FHIR MCP with automatic LOINC validation and semantic search_

Key differentiator: **automatic LOINC code validation**, prevents AI from hallucinating lab codes, a genuine patient safety concern. RAG-ready with vector embeddings. Works with Medplum, HAPI FHIR, Azure Health Data Services, and Epic.

---

**[AWS HealthLake MCP Server](https://awslabs.github.io/mcp/servers/healthlake-mcp-server)**
> _AI access to AWS HealthLake FHIR, with read-only safety mode_

Official AWS Labs server. 11 FHIR tools, advanced search, and critical **read-only mode** for compliance, lock agents to read-only until explicit human approval for write operations. 235 tests, 96% coverage. Best for organizations already on AWS.

---

**[Google Cloud Healthcare API MCP](https://github.com/Kartha-AI/google-cloud-healthcare-api-mcp)**
> _FHIR via GCP with PubMed, ClinicalTrials.gov, and FDA integration_

Connects to GCP Healthcare API with Firebase auth, plus PubMed, ClinicalTrials.gov, and FDA drug information. The **complete clinical intelligence stack** that decision support agents need. Best for GCP-first organizations.

---

**[Medplum MCP](https://github.com/rkirkendall/medplum-mcp)**
> _33 FHIR utility tools via Medplum's open-source EHR_

Ideal for teams **building EHR-adjacent applications** (clinical trial management, specialty clinic workflows, digital health apps). Medplum's sandbox is freely accessible, excellent for development and testing.

---

**[Enhanced FHIR MCP with Data Quality Assessment](https://github.com/jcafazzo/fhir-mcp)**
> _FHIR tools with built-in data quality validation_

Adds **data quality assessment** before agent action, validates completeness, consistency, and conformance. Essential for organizations migrating between EHR systems or working with multiple institutional data sources.

---

## 7 · 🧠 Ontologies & Knowledge Graphs

<!-- 
💡 PLAIN ENGLISH: An "ontology" is basically a shared vocabulary with 
clear definitions. It tells the AI "when we say 'bond' in finance, we 
mean THIS specific thing." Without this, AI might confuse a bail bond 
with a savings bond with James Bond.

A "knowledge graph" is like a giant connected map of facts, "Company A 
bought Company B, which makes Product C, which competes with Product D."
-->

> **In simple terms:** These are the dictionaries and relationship maps that help AI understand domain-specific language, so it knows what words actually mean in your industry.

Ontologies are the **semantic foundation** of domain-aware agents. Without them, agents hallucinate terminology, misclassify entities, and make unreliable connections. This is the layer most teams skip, and then wonder why their agents make embarrassing domain errors.

### 7.1 Finance Ontologies

**[FIBO: Financial Industry Business Ontology](https://github.com/edmcouncil/fibo)**
> _Standard ontology for financial contracts, instruments, and entities_

Developed post-2008 crisis when it became clear firms were using the same terms with incompatible meanings. Standardized by OMG; covers business entities, contracts, securities, derivatives, market data, regulatory reporting. Published in OWL/RDF for direct use in knowledge graphs. Mandatory for agents supporting **regulatory reporting** (Basel III, MiFID II, Dodd-Frank).

- Published: [spec.edmcouncil.org/fibo](https://spec.edmcouncil.org/fibo/)
- Hugging Face: [FIBO 2023 Q3](https://huggingface.co/datasets/wikipunk/fibo2023Q3)

**[ACTUS](https://www.actusfrf.org/)**
> _Machine-readable financial contract standards_

Defines algorithmic representations of financial contracts so cash flows and risk exposures can be computed deterministically. Essential for **risk calculation agents** simulating portfolio behavior under different market scenarios.

**Additional Finance Standards**: XBRL Taxonomy (FASB/IFRS), LEI (Legal Entity Identifier), CFI Codes (ISO 10962)

---

### 7.2 Healthcare Ontologies & Terminology

**[UMLS: Unified Medical Language System](https://www.nlm.nih.gov/research/umls/)**
The backbone of clinical NLP. Maps concepts across 200+ medical vocabularies, 3M+ unique concepts, 15M+ concept names. Free with registration.
- GitHub tool: [UMLS to Graph](https://github.com/blpercha/umls-to-graph), converts UMLS to Neo4j

**[SNOMED CT](https://www.snomed.org/)**
350,000+ clinical concepts in a rich hierarchical ontology. Designed for clinical documentation and decision support. Any agent reasoning about clinical concepts needs SNOMED CT grounding.
- SNOMED KG embeddings: [github.com/dchang56/snomed_kge](https://github.com/dchang56/snomed_kge)

**[ICD-10/ICD-11 (WHO)](https://www.who.int/standards/classifications/classification-of-diseases)**
Every hospital claim and public health report uses ICD codes. Essential for revenue cycle, claims processing, prior authorization, and population health agents.

**[RxNorm](https://www.nlm.nih.gov/research/umls/rxnorm/)**
Standard drug naming system. Prevents dangerous errors like treating "metoprolol succinate" and "metoprolol tartrate" as identical drugs (they have different clinical profiles).

**[LOINC](https://loinc.org/)**
Universal codes for lab tests and clinical measurements. Essential for any agent processing lab results or clinical observations.

**[BioPortal](https://bioportal.bioontology.org/)**
Repository of 1,000+ biomedical ontologies, Gene Ontology, ChEBI, HPO, NCI Thesaurus, MeSH. Essential for research-oriented AI in genomics, drug discovery, or precision medicine.

**[Awesome Healthcare Knowledge Bases](https://github.com/lujiaying/Awesome-HealthCare-KnowledgeBase)**
Comprehensive catalog including Hetionet, DrugBank, SPOKE, and Monarch Initiative. Start here for drug repurposing reasoning or gene-disease association lookups.

---

## 8 · 📊 Datasets

### 8.1 Healthcare

| Dataset | Access | Description | Compliance Note |
|---------|--------|-------------|-----------------|
| **MIMIC-IV** | [physionet.org](https://physionet.org/content/mimiciv/) | De-identified ICU EHR data (2008-2019): vitals, labs, meds, notes, diagnoses. 40K+ patients. | ⚠️ Requires DUA. Do NOT send to cloud LLM APIs, local models only. |
| **MIMIC-CXR** | [physionet.org](https://physionet.org/content/mimic-cxr/) | 227,835 chest X-rays with de-identified radiology reports. | ⚠️ Same DUA. |
| **eICU Collaborative Research DB** | [physionet.org](https://physionet.org/content/eicu-crd/) | Multi-center ICU data from 200K+ stays. | Credentialed access required. |
| **MIMIC Code Repository** | [github.com/MIT-LCP/mimic-code](https://github.com/MIT-LCP/mimic-code) | SQL/Python code for MIMIC analysis; BigQuery and AWS available. | Open-source; data requires DUA. |
| **PhysioNet** | [physionet.org](https://physionet.org/) | ECG, EEG, waveform, vital sign datasets. | Varies by dataset. |
| **CheXpert (Stanford)** | [stanfordmlgroup.github.io](https://stanfordmlgroup.github.io/competitions/chexpert) | 224,316 chest X-rays with uncertainty labels. | Registration required. |
| **FAERS** | [fda.gov](https://www.fda.gov/drugs/drug-approvals-and-databases/fda-adverse-event-reporting-system-faers) | FDA adverse drug event reports, pharmacovigilance database. | Publicly available. |
| **ClinicalTrials.gov** | [clinicaltrials.gov](https://clinicaltrials.gov/) | 500K+ clinical trial records via API. | Publicly available. |

### 8.2 Finance

| Dataset | Access | Description |
|---------|--------|-------------|
| **SEC EDGAR Full-Text** | [efts.sec.gov](https://efts.sec.gov/) | All SEC filings since 1993, 10-K, 10-Q, 8-K, proxy statements. Free, public. |
| **FRED (St. Louis Fed)** | [fred.stlouisfed.org](https://fred.stlouisfed.org/) | 800K+ economic time series: GDP, inflation, employment, rates. Free API. |
| **Alpha Vantage** | [alphavantage.co](https://www.alphavantage.co/) | Stock quotes, indicators, fundamentals. Free tier with rate limits. |
| **OpenBB** | [github.com/OpenBB-finance/OpenBBTerminal](https://github.com/OpenBB-finance/OpenBBTerminal) | Aggregates 100+ financial data sources. Open-source. |
| **FinanceBench** | [github.com/patronus-ai/financebench](https://github.com/patronus-ai/financebench) | QA benchmark over real 10-K/10-Q filings. |
| **FinQA** | [github.com/czyssrs/FinQA](https://github.com/czyssrs/FinQA) | Expert-annotated numerical reasoning over financial reports. |
| **PIXIU / TiE** | [github.com/chancefocus/PIXIU](https://github.com/chancefocus/PIXIU) | Financial NLP benchmarks: sentiment, NER, QA, relation extraction. |

### 8.3 Supply Chain

| Dataset | Access | Description |
|---------|--------|-------------|
| **M5 Forecasting (Walmart)** | [Kaggle](https://www.kaggle.com/c/m5-forecasting-accuracy) | 5 years Walmart sales; 42,840 time series. Gold standard for demand forecasting. |
| **Favorita Grocery Sales** | [Kaggle](https://www.kaggle.com/c/favorita-grocery-sales-forecasting) | Ecuadorian grocery sales with promotions, oil prices, holidays. |
| **UCI Supply Chain Datasets** | [archive.ics.uci.edu](https://archive.ics.uci.edu/) | Multiple SCM classification and regression datasets. |
| **Open Supply Hub** | [opensupplyhub.org](https://opensupplyhub.org/) | Global open database of supply chain facilities with standardized identifiers. |

---

## 9 · 📚 Papers, Associations & Where to Learn

### 9.1 Landmark Academic Papers

#### 🏥 Healthcare AI

| Paper | Venue | Why It Matters |
|-------|-------|---------------|
| **"Large Language Models Encode Clinical Knowledge"**: Singhal et al. (MedPaLM) | *Nature* 2023 | First to demonstrate expert-level USMLE performance; set the benchmark for clinical LLM capability claims. |
| **"Towards Expert-Level Medical QA with LLMs"** (MedPaLM 2) | arXiv 2023 | Showed LLMs approaching physician-level performance; defines the evaluation standard. |
| **"LLM-based Agentic Systems in Medicine and Healthcare"** | *Nature Machine Intelligence* 2024 | Formal framework for understanding agentic AI in clinical settings; introduced the field's core taxonomy. |
| **"MDAgents: Adaptive Collaboration of LLMs for Medical Decision-Making"** | *NeurIPS Oral* 2024 | Demonstrates dynamic multi-agent collaboration outperforms static ensembles in clinical reasoning. |
| **"AgentClinic: A Multimodal Agent Benchmark"**: Schmidgall et al. | arXiv 2024 | First open benchmark for evaluating clinical AI agents in interactive environments; now the standard. |
| **"EHRAgent: Code Empowers LLMs for Tabular EHR Reasoning"** | arXiv 2024 | Shows code generation agents outperform direct LLM reasoning on structured EHR data, practically important for revenue cycle agents. |
| **"Polaris: Safety-focused LLM Constellation for Healthcare"** | 2024 | Addresses multi-agent safety architecture in healthcare; foundational for safe clinical agent design. |
| **Application of LLMs in Medicine** (MedLLMsPracticalGuide) | *Nature Reviews Bioengineering* 2024 | The most comprehensive practitioner survey of medical LLM deployment; referenced by regulators. |

#### 💰 Finance AI

| Paper | Venue | Why It Matters |
|-------|-------|---------------|
| **"FinGPT: Open-Source Financial LLMs"**: Yang et al. | arXiv 2023 | Introduced continuous fine-tuning for financial LLMs; most cited paper in open-source finance AI. |
| **"FinBERT: Financial Language Representation"**: Yang et al. | 2020 | Foundational paper for financial NLP; established fine-tuning on financial text as standard practice. |
| **"PIXIU: LLM Benchmark for Finance"** | arXiv 2023 | Created the most comprehensive finance LLM benchmark; now the standard for finance AI model evaluation. |
| **"A Survey of LLMs for Finance (FinLLMs)"** | arXiv 2024 | Comprehensive overview; essential for teams evaluating the landscape. |
| **"FinAgent: Multimodal Foundation Agent for Financial Trading"** | arXiv 2024 | Demonstrates multimodal agents (text + charts + news) outperforming single-modality in trading contexts. |
| **"Can LLMs be Good Financial Advisors?"** | arXiv 2023 | Critical evaluation of LLM limitations in financial reasoning; important for setting appropriate expectations. |
| **"TradingGPT: Multi-Agent System with Layered Memory"** | arXiv 2023 | Introduced layered memory architecture for trading agents; influenced downstream architectures. |

#### 📦 Supply Chain AI

| Paper | Venue | Why It Matters |
|-------|-------|---------------|
| **"Agentic LLMs in the Supply Chain: Towards Autonomous Multi-Agent Consensus-Seeking"**: Jannelli, Schoepf, Brintrup et al. | *IJPR* 2025 (arXiv 2411.10184) | Open-sourced code; LLM agents reduce bullwhip effect better than traditional restocking policies. The most cited agentic SCM paper. |
| **"How Generative AI Improves Supply Chain Management"**: Menache, Simchi-Levi et al. | *Harvard Business Review* 2025 | High-impact practitioner publication; widely referenced by enterprise teams and executives. |
| **"LLMs in Supply Chain Management: Opportunities and a Case Study"** | *ScienceDirect* 2025 | Integration case study of LLMs with decentralized agent-based SCM systems; practical architecture guidance. |
| **"The Potential of LLMs in Supply Chain Management"** | arXiv 2501.15411, 2025 | Comprehensive review with integration of IoT, blockchain, and robotics. |
| **"Automating Supply Chain Disruption Monitoring via Agentic AI"** | arXiv 2601.09680, 2026 | Multi-agent disruption monitoring with graph-based propagation; state of the art in supply chain risk AI. |
| **"Leveraging LLM-Based Agents for Intelligent Supply Chain Planning"** (SCPA) | arXiv 2509.03811, 2025 | JD.com case study at 10M+ SKUs; most practical production reference for large-scale supply chain AI. |
| **"Will Bots Take Over the Supply Chain?"**: Xu, Mak, Brintrup | *IJPE* 2021 | Foundational review of agent-based supply chain automation from earlier generations; establishes what works and what doesn't. |
| **"InvAgent: LLM Agents for Inventory Management"**: Quan & Liu | 2024 | Introduced zero-shot inventory management via LLM agents; showed generalization without task-specific training per SKU. |

---

### 9.2 Key Regulatory Frameworks

#### Healthcare
- **FDA AI/ML-Based SaMD**: [fda.gov](https://www.fda.gov/medical-devices/software-medical-device-samd/artificial-intelligence-and-machine-learning-software-medical-device)
- **ONC TEFCA**: National FHIR interoperability framework
- **HL7 FHIR R4**: [hl7.org/fhir/R4](https://hl7.org/fhir/R4/), the EHR interoperability standard
- **HIPAA Security Rule Technical Safeguards**: Required reading for any AI accessing PHI
- **CDS Hooks Standard**: How CDS integrates with EHR workflows
- **EU AI Act: High-Risk AI**: Healthcare AI falls in the high-risk category

#### Finance
- **SR 11-7: Model Risk Management**: OCC/Fed guidance; applies to every ML/AI model in banking
- **SEC AI Guidance**: [sec.gov/ai](https://www.sec.gov/ai)
- **FINRA Regulatory Notice 24-09**: AI in broker-dealer supervision
- **Basel Committee on Banking Supervision: AI in Finance**
- **CFPB Guidance on AI**: Automated decision-making and fair lending
- **EU AI Act: Finance**: Algorithmic trading and credit scoring as high-risk AI

#### Cross-Industry
- **NIST AI RMF**: [nvlpubs.nist.gov](https://nvlpubs.nist.gov/nistpubs/ai/NIST.AI.100-1.pdf), gold standard for AI governance
- **ISO/IEC 42001**: AI management system standard
- **OWASP LLM Top 10**: Security vulnerabilities for LLM-based systems
- **MITRE ATLAS**: Adversarial threat landscape for AI systems

---

### 9.3 Associations & Professional Organizations

| Organization | Domain | What They Do |
|-------------|--------|--------------|
| **AMIA** (amia.org) | Healthcare | American Medical Informatics Association, professional home for clinical informatics; annual symposium is the top clinical AI conference |
| **HIMSS** (himss.org) | Healthcare | Health IT industry body; publishes Digital Health reports |
| **HL7 International** (hl7.org) | Healthcare | Develops and maintains FHIR and interoperability standards |
| **IEEE EMBS** (embs.org) | Healthcare | IEEE Engineering in Medicine and Biology Society; publishes J-BHI |
| **NLM / NIH** (nlm.nih.gov) | Healthcare | Maintains UMLS, MeSH, PubMed; public infrastructure for biomedical AI |
| **GARP** (garp.org) | Finance | Global Association of Risk Professionals |
| **PRMIA** (prmia.org) | Finance | Professional Risk Managers' International Association |
| **EDM Council** (edmcouncil.org) | Finance | Maintains FIBO; drives data governance standards |
| **ISDA** (isda.org) | Finance | International Swaps and Derivatives Association; derivatives data standards |
| **ASCM** (ascm.org) | Supply Chain | Association for Supply Chain Management; publishes SCOR framework |
| **GS1** (gs1.org) | Supply Chain | Global supply chain standards body (barcodes, RFID, EDI) |
| **MIT CTL** (ctl.mit.edu) | Supply Chain | MIT Center for Transportation and Logistics; leading academic research |
| **CSCMP** (cscmp.org) | Supply Chain | Council of Supply Chain Management Professionals |
| **MLOps Community** (mlops.community) | Cross-Industry | Practitioners forum for production ML/AI |
| **IEEE** (ieee.org) | Cross-Industry | IEEE AI standards working groups; relevant for regulated AI deployment |

---

### 9.4 Key Publications by Domain

**Healthcare AI**: npj Digital Medicine (Nature), NEJM AI, JAMIA, The Lancet Digital Health, JMIR Medical Informatics

**Finance AI**: Journal of Financial Data Science, Risk.net, Journal of Portfolio Management, SSRN Finance, Harvard Business Review

**Supply Chain & Logistics AI**: International Journal of Production Research, International Journal of Production Economics, European Journal of Operational Research, Supply Chain Management: An International Journal, Logistics Viewpoints

---

---

## 10 · ⚖️ Regulatory Reference Guide

<!-- 
💡 PLAIN ENGLISH: These are the laws and rules you MUST follow when 
building AI for healthcare, finance, or supply chain. Breaking them 
can result in massive fines, lawsuits, or even criminal charges. 

This section isn't optional reading, it's the "don't go to jail" section.
-->

> **In simple terms:** The legal rules for AI in regulated industries. Read this before you build anything, or find someone who has.

> This section maps the specific regulations your Agent Factory must navigate in healthcare, finance, and supply chain. Each entry covers what it is, who it applies to, key requirements for AI systems, and concrete actions for your agent builds. The AI regulatory landscape is moving fast, check effective dates carefully.

---

### 10.1 🏥 Healthcare Regulations

---

#### HIPAA Security Rule (2025 Updates)
**Authority:** U.S. Department of Health & Human Services (HHS)
**Status:** Proposed rule published Jan 6, 2025; compliance timeline TBD
**Applies to:** Covered entities (hospitals, clinics, health plans) and Business Associates (AI vendors, third parties processing ePHI)

**What Changed**: The 2025 update **eliminates the distinction between "required" and "addressable" safeguards: all controls are now mandatory.**

| Requirement | Specific Mandate |
|---|---|
| **PHI Minimization** | AI tools access only minimum necessary PHI; document exactly which fields each model uses |
| **MFA** | Multi-factor authentication required at all ePHI access points, including AI APIs |
| **Encryption** | PHI must be unusable/unreadable in transit and at rest |
| **Vulnerability Scanning** | Every 6 months minimum; annual penetration testing |
| **Disaster Recovery** | Critical system restoration within 72 hours of incident |
| **Business Associate Agreements (BAAs)** | Ongoing vendor verification, not just onboarding; governs all AI vendors touching ePHI |
| **De-identification** | Safe Harbor or Expert Determination required when using PHI for AI/ML training |
| **Audit Logging** | Activity logs for all AI model access to ePHI; must be reviewable |

**Agent Factory Actions**:
- Embed PHI minimization checks into prompt engineering and data pipelines
- Require BAAs from all AI platform vendors (Azure, OpenAI, Anthropic, etc.)
- Use synthetic data generation for model training to avoid PHI exposure
- Log all agent access to health records with user/role attribution

---

#### FDA AI/ML Medical Device Guidance: Total Product Life Cycle (TPLC)
**Authority:** U.S. Food and Drug Administration
**Status:** Draft guidance issued Jan 7, 2025; phased review ongoing
**Applies to:** AI-enabled Software as a Medical Device (SaMD), diagnostic AI, clinical NLP tools, predictive analytics for patient care

**Core Framework**: FDA requires AI governance across the **entire device lifespan**, design, training, deployment, and postmarket monitoring, not just at the point of approval.

| Phase | Requirement |
|---|---|
| **Pre-market Submission** | Data lineage, train/test splits, performance validation tied to clinical claims, demographic bias analysis |
| **Change Control** | Predetermined Change Control Plan (PCCP) for adaptive/continuously learning models |
| **Human Oversight** | Document level of clinician oversight required for each AI-assisted decision |
| **Post-market Monitoring** | Ongoing real-world performance tracking; incident reporting plan |
| **Bias Analysis** | Subgroup performance reporting across race, age, gender for clinical AI |

**Agent Factory Actions**:
- Build PCCP templates into your agent governance checklists for adaptive models
- Document AI decision boundaries for any clinical workflow agent
- Apply TPLC lifecycle tagging in your AI inventory (pre-market → deployed → monitored)

---

#### U.S. State-Level AI Laws (Healthcare)
**Status:** 46 states introduced 250+ bills in 2025; 17 states enacted 27 laws
**Key States:** California (AB 3030, SB 1120), Pennsylvania, Colorado, Arizona, Texas

| Category | Requirement |
|---|---|
| **Transparency** | Disclose when AI is interacting with or making decisions about patients (90+ bills include this) |
| **Anti-discrimination** | Validate AI does not produce biased outcomes by demographic group |
| **Use-case Restrictions** | Prohibit AI-only coverage denials (5 states); require human verification |
| **Clinical Context Oversight** | AI recommendations must be reviewed by licensed clinicians before execution |

**Agent Factory Actions**:
- Build disclosure headers into all patient-facing agent responses
- Implement bias monitoring for any AI touching insurance, clinical, or administrative workflows
- Enforce human-in-the-loop gates for high-stakes decisions (coverage, diagnosis, triage)

---

### 10.2 💳 Finance Regulations

---

#### EU AI Act: Financial Services
**Authority:** European Union
**Status:** In force Aug 2024; high-risk obligations effective **Aug 2, 2026**
**Applies to:** Any AI system used for credit scoring, underwriting, pricing, fraud detection, or automated financial decisions, including non-EU companies if EU consumers are impacted

| AI Use Case | Risk Tier | Oversight Level |
|---|---|---|
| Credit adjudication / underwriting | **High Risk** | Full compliance required |
| Pricing algorithms | **High Risk** | Full compliance required |
| Fraud detection (automated denial) | **High Risk** | Full compliance required |
| Customer chatbots | **Limited Risk** | Transparency notice required |
| Marketing/segmentation tools | **Minimal Risk** | Baseline controls |

| Requirement | What It Means |
|---|---|
| **Risk Management System** | Continuous identification, evaluation, mitigation across the model lifecycle |
| **Training Data Governance** | Demographic fairness audits; document data lineage and representativeness |
| **Explainability** | SHAP/LIME documentation required; decisions interpretable to regulators and consumers |
| **Human Oversight** | Mandatory human-in-the-loop for credit, pricing, and denial decisions |
| **Technical Documentation** | Lifecycle records from design through decommission |
| **Accuracy & Robustness** | Validated performance metrics; resilience against adversarial inputs |
| **Conformity Assessment** | Self-assessment for most financial AI; third-party audit for highest-risk categories |

**Agent Factory Actions**:
- Risk-tier all finance agents before POC approval (use EU Act categories as your template)
- Attach SHAP/LIME explainability outputs to every credit/fraud agent decision log
- Implement human review gates for any agent making binding financial decisions

---

#### OSFI Guideline E-23: Model Risk Management (Canada)
**Authority:** Office of the Superintendent of Financial Institutions (Canada)
**Status:** Final guideline released Sept 2025; **effective May 1, 2027**
**Applies to:** All federally regulated financial institutions (FRFIs) in Canada, including scaled fintechs

| Pillar | Key Obligations |
|---|---|
| **Model Inventory** | Living registry with risk ratings, lifecycle status, decommission records; covers all AI/ML models |
| **Risk-Tiered Governance** | Oversight intensity proportional to model risk; allocate resources accordingly |
| **Independent Validation** | Required for high-risk models; multi-disciplinary teams (legal, ethics, data science) |

| Requirement | Detail |
|---|---|
| **Pre-deployment Assessment** | Cybersecurity risk, infrastructure vulnerability, explainability review before go-live |
| **Drift Monitoring** | Processes for detecting model drift, performance degradation, autonomous re-parametrization |
| **Autonomous Decision Risk** | Specific controls for AI making decisions without human review |
| **Documentation** | Full lifecycle model records; survivable through staff turnover |
| **Remediation Tracking** | Incident history and stabilization steps tracked in inventory |

**Agent Factory Actions**:
- Map E-23 inventory requirements into your AI inventory template (owners, risk tier, cadence, incidents)
- Build pre-deployment checklists aligned to E-23 pillars for all financial agents
- Assign independent validation workflows for high-risk financial agents before production

---

#### NIST AI Risk Management Framework (AI RMF)
**Authority:** U.S. National Institute of Standards and Technology
**Status:** Voluntary; widely referenced baseline globally
**Applies to:** All sectors, particularly useful as a foundational governance scaffold for fintech and any enterprise AI program

| Function | Purpose |
|---|---|
| **Govern** | Establish policies, roles, accountability structures, and culture of AI risk awareness |
| **Map** | Identify AI risks in context, business, technical, and societal impacts |
| **Measure** | Quantify and test risks: bias, accuracy, drift, explainability |
| **Manage** | Prioritize and treat risks; document decisions and residual risk |

**Agent Factory Actions**:
- Use Govern → Map → Measure → Manage as the backbone of your CoE governance cycle
- Apply as the cross-cutting baseline across healthcare, finance, and supply chain programs

---

#### U.S. Treasury AI Guidance
**Authority:** U.S. Department of the Treasury
**Status:** Released **Feb 18, 2026**
**Applies to:** Financial services organizations deploying AI in consumer-facing and operational contexts

Focuses on responsible AI deployment, consumer protection, and systemic risk awareness. Two new resources released to guide financial institutions on AI governance alignment. Signals that federal financial regulators are moving toward more prescriptive AI guidance, watch for follow-on publications.

---

### 10.3 📦 Supply Chain Regulations

---

#### EU AI Act: Supply Chain Applications
**Authority:** European Union
**Status:** GPAI obligations active Aug 2025; high-risk obligations effective **Aug 2, 2026**
**Applies to:** Supply chain AI for procurement, logistics, quality control, supplier selection, demand forecasting, especially tools from third-party AI vendors

| AI Use Case | Risk Level | Requirement |
|---|---|---|
| Automated vendor disqualification | **High** | Human verification required before execution |
| AI-driven contract rejection | **High** | Bias validation, human review gate |
| Quality inspection AI (robotics) | **High** | Transparency + monitoring from vendor |
| Demand forecasting / planning | **Minimal–Limited** | Baseline logging, performance tracking |
| Carrier/route optimization | **Minimal** | Light governance, audit trail |

| Requirement | Detail |
|---|---|
| **Vendor Transparency** | AI suppliers must provide risk and performance documentation; include in supplier reviews |
| **Bias Monitoring** | Validate procurement AI doesn't systematically disadvantage supplier categories |
| **Human Oversight** | High-impact decisions (vendor termination, contract awards) require human review |
| **Incident Escalation** | Define how AI behavior issues are reported and remediated across vendor chain |
| **Documentation** | Evidence of testing, updates, and contractual security responsibilities |

**Agent Factory Actions**:
- Identify all AI-based vendor tools in your supply chain; tag risk tier per EU Act
- Include AI governance obligations in supplier contracts
- Build escalation workflows in your orchestration layer for high-risk automated supply decisions

---

#### 2026 NDAA: AI Supply Chain & Security (U.S. Defense)
**Authority:** U.S. Congress (National Defense Authorization Act)
**Status:** Effective 2026; primarily targets defense/government supply chains
**Applies to:** Companies supplying AI to U.S. defense and intelligence agencies

- Strict supply chain restrictions prohibiting "covered" technologies from adversary nations
- Cybersecurity standards expanding on CMMC (Cybersecurity Maturity Model Certification)
- DOD directed to develop AI-specific security standards
- Non-compliance = exclusion from the Defense Industrial Base

**Agent Factory Actions**:
- If serving government clients, map AI components against prohibited vendor lists
- Build CMMC-aligned cybersecurity controls into agent deployment pipelines

---

#### CCPA / CPRA: Supply Chain Data
**Authority:** California Privacy Protection Agency (CPPA)
**Status:** Audit and risk assessment obligations rolling out 2025–2028
**Applies to:** Organizations processing California consumer data through supply chain services, vendors, or contractors

| Requirement | Detail |
|---|---|
| **Data Inventory** | Comprehensive mapping of personal data collected, processed, shared across all vendors |
| **Vendor Contracts** | Written contracts with all sub-processors; must include audit rights and opt-out mechanisms |
| **AI Cybersecurity Audit** | Contractors must cooperate on cybersecurity audits (Article 9, effective Jan 1, 2026) |
| **Risk Assessments** | AI-related risk assessments required (Article 10); annual reports to CPPA beginning April 1, 2028 |
| **Opt-Out Rights** | Consumer right to opt out of automated decision-making that produces significant effects |

**Agent Factory Actions**:
- Build data flow maps for all supply chain agents handling California consumer data
- Include CCPA audit cooperation clauses in AI vendor agreements
- Implement opt-out mechanisms for consumer-facing supply chain automation

---

#### CISA / NIST Cybersecurity Framework (CSF 2.0)
**Authority:** CISA and NIST
**Status:** CSF 2.0 released Feb 2024; continuously updated
**Applies to:** All critical infrastructure sectors including healthcare, finance, and supply chain

> Supply chain attacks doubled in 2025, averaging approximately 26 incidents per month, making this framework operationally critical, not just a compliance checkbox.

| Control | Purpose |
|---|---|
| **SBOM (Software Bill of Materials)** | Full inventory of software components in AI systems; validate no vulnerable or prohibited dependencies |
| **Third-Party Risk Scoring** | Continuous vendor risk monitoring; supply chain attacks doubled in 2025 |
| **Zero Trust Architecture** | Assume breach; verify every access request including agent-to-agent calls |
| **Incident Response Plan** | Defined playbooks for supply chain-specific attack vectors (ransomware, data exfiltration) |

**Agent Factory Actions**:
- Generate SBOMs for all agent frameworks and dependencies
- Implement zero trust principles in multi-agent orchestration (no implicit trust between agents)
- Run vendor risk scoring as an automated agent function for supply chain clients

---

### 10.4 🗂️ Cross-Sector Regulatory Quick Reference

| Regulation | Sector | Jurisdiction | Effective | Core AI Obligation |
|---|---|---|---|---|
| **HIPAA Security Rule 2025** | Healthcare | U.S. | 2025 (proposed) | MFA, encryption, PHI minimization, BAAs |
| **FDA TPLC AI Guidance** | Healthcare | U.S. | Jan 2025 (draft) | Data lineage, bias analysis, PCCP, post-market monitoring |
| **State AI Laws (CA, PA, TX…)** | Healthcare | U.S. States | 2025–2026 | Disclosure, anti-bias, human verification |
| **EU AI Act (High-Risk)** | Finance, Supply Chain | EU/Global | **Aug 2, 2026** | Risk tiers, explainability, human-in-loop, technical docs |
| **OSFI E-23** | Finance | Canada | **May 1, 2027** | Model inventory, drift monitoring, independent validation |
| **NIST AI RMF** | All sectors | U.S./Global | Voluntary | Govern, Map, Measure, Manage lifecycle |
| **U.S. Treasury AI Guidance** | Finance | U.S. | **Feb 18, 2026** | Responsible AI deployment, consumer protection |
| **2026 NDAA AI Supply Chain** | Supply Chain (Defense) | U.S. | 2026 | Vendor restrictions, CMMC-aligned cybersecurity |
| **CCPA / CPRA** | Supply Chain, Finance | California/U.S. | 2025–2028 | Data mapping, vendor contracts, risk assessments |
| **CISA / NIST CSF 2.0** | All sectors | U.S. | Active | SBOM, zero trust, third-party risk, incident response |

> **Compliance is not a one-time checklist.** Regulations listed here with "proposed" or "draft" status will finalize. Regulations with future effective dates are already shaping what enterprise buyers require of AI vendors today. Build your Agent Factory to these standards now, retrofitting compliance into production systems is significantly more expensive than designing for it from the start.

---

## 🗺️ Agent Factory Architecture Quick Reference

```
┌─────────────────────────────────────────────────────┐
│                   ORCHESTRATION LAYER                │
│         LangGraph / AutoGen / CrewAI                 │
├──────────────┬──────────────┬────────────────────────┤
│   MEMORY     │    TOOLS     │   KNOWLEDGE            │
│   mem0       │  MCP Servers │   Ontologies + KGs     │
│   LangGraph  │  SEC EDGAR   │   FIBO / SNOMED        │
│   State      │  FHIR        │   UMLS / ICD-10        │
│              │  Logistics   │   GS1 / SCOR           │
├──────────────┴──────────────┴────────────────────────┤
│                   MODEL LAYER                        │
│   Domain LLMs (FinGPT, BioGPT, etc.)                 │
│   General LLMs (Claude, GPT-4o, Llama 3.x)           │
├─────────────────────────────────────────────────────┤
│                   DATA LAYER                         │
│   Healthcare: FHIR, MIMIC, PhysioNet, FAERS          │
│   Finance: EDGAR, FRED, Market Data APIs             │
│   Supply Chain: WMS, ERP, IoT Sensors, M5            │
├─────────────────────────────────────────────────────┤
│              COMPLIANCE & GOVERNANCE                 │
│   Audit Logs │ Explainability │ Human-in-Loop        │
│   HIPAA │ SOC 2 │ SR 11-7 │ FDA SaMD │ SEC/FINRA    │
│   EU AI Act │ NIST AI RMF │ ISO 42001               │
└─────────────────────────────────────────────────────┘
```

---

## 📋 Deployment Checklists

### Healthcare Agent
- [ ] PHI de-identification strategy documented
- [ ] HIPAA minimum necessary standard review completed
- [ ] Human-in-the-loop mechanism defined for clinical recommendations
- [ ] FHIR OAuth2 scope limited to minimum required resources
- [ ] Model evaluated on AgentClinic or equivalent clinical benchmark
- [ ] FDA SaMD classification determined
- [ ] Audit trail enabled for all agent decisions
- [ ] BAA signed with all cloud vendors

### Finance Agent
- [ ] Model risk management documentation complete (per SR 11-7)
- [ ] Independent model validation completed
- [ ] Explainability mechanism in place for agent recommendations
- [ ] Fair lending / disparate impact analysis completed (if credit-related)
- [ ] Supervisory controls defined for trading or execution
- [ ] Legal review of client-facing AI communications
- [ ] Data licensing verified for all market data sources
- [ ] Out-of-sample backtesting with documented methodology

### Supply Chain Agent
- [ ] Data access controls for ERP/WMS systems documented
- [ ] Human override mechanisms defined for autonomous ordering/routing
- [ ] Fallback to rule-based systems defined for agent failure
- [ ] Supplier data sharing agreements reviewed for AI use compliance
- [ ] Change management plan for operations teams prepared
- [ ] Audit trail for any agent-initiated transactions

---

## 🔄 Update Log

| Date | What Changed | Contributor |
|------|-------------|-------------|
| Feb 2026 | Initial release, Finance, Healthcare, Supply Chain, MCP servers, Ontologies, Papers, Associations | Mario Lazo |
| Feb 2026 | Added Section 10: Full regulatory reference guide, HIPAA 2025, FDA TPLC, State AI Laws, EU AI Act, OSFI E-23, NIST AI RMF, U.S. Treasury, 2026 NDAA, CCPA/CPRA, CISA CSF 2.0 | Mario Lazo |
| Feb 2026 | Reorganized structure for searchability; added Companion References section; expanded disclaimer and community contribution guidelines | Mario Lazo |

_Next scheduled review: **April 2026**_

---

## 📬 Contact & Collaboration

**How to reach out:**

| Channel | Use For |
|---------|---------|
| **GitHub Issues** | Corrections, broken links, outdated resources, removal requests |
| **GitHub Pull Requests** | Add new resources, improve descriptions, fix errors |
| **GitHub Discussions** | Architecture questions, share production experiences, coordinate |
| **LinkedIn** | Connect with Mario Lazo |

---

## 🎯 Quality Over Quantity

This reference intentionally excludes:

- **Vaporware**: Tools that exist only in press releases
- **Abandoned projects**: Repos with no commits in 18+ months (unless historically significant)
- **Demo-only tools**: Things that work in notebooks but break in production
- **Paywall-only resources**: Unless the value is exceptional and clearly stated
- **Generic AI tools**: Covered by companion references above

What stays in this document:

- **Used in production**: By the curator or verified by trusted practitioners
- **Strong research backing**: Published, peer-reviewed, cited
- **Actively maintained**: Recent commits, responsive maintainers
- **Relevant to regulated industries**: Addresses compliance, auditability, or domain-specific challenges

**If something doesn't meet these standards, it doesn't belong here.**

---

## 📈 Recommendations for Maximum Community Adoption

<!-- 
💡 PLAIN ENGLISH: This section is about how to help this guide spread and improve.
The more people use it, contribute to it, and share their experiences, 
the more valuable it becomes for everyone.
-->

### For Organizations Using This Guide

| Action | Why It Helps |
|--------|--------------|
| **Star the repo** | Signals value to others evaluating the resource |
| **Share internally** | Gets more eyes on it, more feedback, more contributions |
| **File issues when things are outdated** | Keeps the guide accurate, your 5-minute issue saves others hours |
| **Contribute what you learn** | If you found a great tool or pattern, share it, that's how this grows |

### For Community Contributors

**High-impact contributions we need:**

1. **Real-world case studies**: "We used X for Y, here's what worked and what didn't"
2. **Vendor comparisons**: Objective side-by-side evaluations (not marketing)
3. **Compliance mappings**: "Here's how Tool X addresses HIPAA requirement Y"
4. **Integration guides**: "Here's how to connect Framework A to System B"
5. **Failure stories**: What *didn't* work is often more valuable than what did

**Contribution quality bar:**

- Must be based on actual use (not just reading the README)
- Should include limitations, not just features
- Needs to be relevant to regulated environments specifically

### For Educators and Consultants

- **Fork freely**: Customize for your specific audience or client base
- **Attribute openly**: CC BY 4.0 means you can use this commercially with attribution
- **Contribute back**: If you improve it, share those improvements upstream
- **Teach from it**: Use sections as teaching materials for AI governance courses

### Making This Guide Better: Priority Areas

| Priority | What We Need | Who Can Help |
|----------|--------------|--------------|
| 🔴 **High** | Healthcare MCP server reviews | Clinical informatics practitioners |
| 🔴 **High** | Finance compliance mapping updates | GRC professionals, compliance officers |
| 🟡 **Medium** | Supply chain automation case studies | Operations and logistics leaders |
| 🟡 **Medium** | International regulation coverage | Practitioners outside North America |
| 🟢 **Low** | Additional ontology references | Knowledge graph specialists |
| 🟢 **Low** | Academic paper reviews | Researchers and academics |

---

## 🙏 Final Note

This guide exists because too many AI projects fail for preventable reasons:

- Teams build what already exists
- Organizations pick the wrong tool for their compliance environment
- Pilots succeed, productions fail
- Nobody maps the regulatory landscape until it's too late

If this reference helps one team avoid those mistakes, it was worth building.

**Help make it better.** File issues. Open PRs. Share what works. Share what doesn't. The AI landscape moves too fast for any one person to track alone.

---

## 🔗 How to Cite This Reference

If you find this useful in your work, please cite it:

```
Lazo, M. (2026). Agent Factory Reference: Regulated Industries Edition. 
GitHub. https://github.com/MarioLazo/agent-factory-reference
```

For academic papers:
```bibtex
@misc{agentfactoryref2026,
  author = {Lazo, Mario},
  title = {Agent Factory Reference: Regulated Industries Edition},
  year = {2026},
  publisher = {GitHub},
  url = {https://github.com/MarioLazo/agent-factory-reference}
}
```

---

_Last updated: February 2026_
_Maintained by: Mario Lazo_
_License: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/), Share with attribution_

> _"83% of enterprise AI pilots fail. Most of them fail for the same reasons. This guide is an attempt to make that number smaller."_
