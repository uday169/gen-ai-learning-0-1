# gen-ai-learning-0-1

A structured learning path for Python full-stack developers moving toward **GenAI Developer** and **GenAI Architect** roles.

**Focus areas:** LLM applications · RAG · Agentic AI · Evaluation · Observability · Production Architecture

---

## 📖 Table of Contents

1. [About This Roadmap](#about-this-roadmap)
2. [High-Level Roadmap Overview](#high-level-roadmap-overview)
3. [Stage 1 — GenAI Foundations](#stage-1--genai-foundations)
4. [Stage 2 — LLM Application Development](#stage-2--llm-application-development)
5. [Stage 3 — Prompt Engineering](#stage-3--prompt-engineering)
6. [Stage 4 — Embeddings and Semantic Search](#stage-4--embeddings-and-semantic-search)
7. [Stage 5 — RAG Fundamentals](#stage-5--rag-fundamentals)
8. [Stage 6 — Advanced RAG](#stage-6--advanced-rag)
9. [Stage 7 — Orchestration Frameworks](#stage-7--orchestration-frameworks)
10. [Stage 8 — Agentic AI](#stage-8--agentic-ai)
11. [Stage 9 — MCP and A2A](#stage-9--mcp-and-a2a)
12. [Stage 10 — Observability and Evaluation](#stage-10--observability-and-evaluation)
13. [Stage 11 — Security, Privacy, and Governance](#stage-11--security-privacy-and-governance)
14. [Stage 12 — Production Deployment and Architecture](#stage-12--production-deployment-and-architecture)
15. [12-Week Learning Plan](#12-week-learning-plan)
16. [Capstone Projects](#capstone-projects)
17. [Tools Checklist](#tools-checklist)
18. [GitHub Portfolio Structure](#github-portfolio-structure)
19. [Architecture Decision Guide](#architecture-decision-guide)
20. [Master Resource List](#master-resource-list)
21. [Completion Checklist](#completion-checklist)

---

## About This Roadmap

This roadmap converts an existing Python full-stack background into advanced GenAI capability.

### Recommended learning ratio

| Category | Weight | Description |
|---|---|---|
| Concepts | 30% | LLMs, embeddings, RAG, agents, architecture patterns |
| Hands-on Building | 50% | APIs, RAG apps, agent workflows, deployment |
| Optimization | 20% | Evaluation, observability, cost, latency, security |

### Expected outcomes

By the end of this roadmap you will be able to:

- Build LLM-powered APIs using Python and FastAPI
- Design and implement Retrieval-Augmented Generation systems
- Build agentic workflows using tools, memory, and orchestration
- Evaluate RAG and agent systems using metrics and traces
- Deploy production-grade GenAI applications with monitoring, cost controls, and security
- Think like a GenAI architect: model selection, retrieval strategy, orchestration, deployment, governance

---

## High-Level Roadmap Overview

```text
Stage 1  → GenAI Foundations
Stage 2  → LLM App Development
Stage 3  → Prompt Engineering and Structured Output
Stage 4  → Embeddings and Semantic Search
Stage 5  → RAG Fundamentals
Stage 6  → Advanced RAG
Stage 7  → Orchestration Frameworks (LangChain, LlamaIndex, Semantic Kernel)
Stage 8  → Agentic AI
Stage 9  → MCP and A2A
Stage 10 → Observability, Tracing, and Evaluation
Stage 11 → Security, Privacy, and Governance
Stage 12 → Production Deployment and Architecture
```

---

## Stage 1 — GenAI Foundations

**Goal:** Understand what Generative AI is, how LLMs work, and why modern applications use LLMs differently from traditional software.

### Topics

| Topic | Key concepts |
|---|---|
| AI vs ML vs GenAI | Differences between AI, Machine Learning, Deep Learning, Generative AI, and LLMs |
| Large Language Models | Token-by-token generation, probabilistic output, hallucination, context importance |
| Transformers | Encoder-decoder architecture, self-attention, positional encoding |
| Tokenization | Text → tokens, token cost and limits, model-specific tokenizers |
| Context Window | Maximum tokens per request, cost/latency tradeoffs |

### Hands-on practice

- Use a tokenizer tool and compare short vs long prompts
- Observe how output changes when context is added or removed
- Ask the same question with different context sizes

### Resources

| Resource | Link |
|---|---|
| Microsoft Learn — Intro to AI | https://learn.microsoft.com/en-us/training/paths/get-started-with-artificial-intelligence/ |
| Azure OpenAI overview | https://learn.microsoft.com/en-us/azure/ai-services/openai/ |
| OpenAI API docs | https://developers.openai.com/api/docs/ |
| Hugging Face NLP course | https://huggingface.co/learn/nlp-course/chapter1/1 |
| The Illustrated Transformer | https://jalammar.github.io/illustrated-transformer/ |

---

## Stage 2 — LLM Application Development

**Goal:** Use Python full-stack skills to build real LLM applications quickly.

### Core stack

Python · FastAPI · Pydantic · OpenAI SDK / Azure OpenAI SDK · Docker basics · Postman

### Topics

- Calling LLM APIs: API keys, model names, request-response format, system/user/assistant roles, streaming
- FastAPI integration: `POST /chat`, `POST /summarize`, `POST /extract`, `POST /classify`
- Structured output: JSON responses, typed objects, Pydantic validation
- Streaming responses: chat UX, long responses, better perceived latency

### Mini projects

| Project | Description |
|---|---|
| Mini project 1 — Basic LLM Chat API | FastAPI service with `/chat` endpoint, error handling, env-based API key, logging |
| Mini project 2 — Text Utility API | Endpoints for `/summarize`, `/rewrite`, `/translate`, `/extract-json` |

### Resources

| Resource | Link |
|---|---|
| OpenAI SDKs | https://developers.openai.com/api/docs/libraries |
| Azure OpenAI | https://learn.microsoft.com/en-us/azure/ai-services/openai/ |
| FastAPI docs | https://fastapi.tiangolo.com/ |
| Pydantic docs | https://docs.pydantic.dev/ |

---

## Stage 3 — Prompt Engineering

**Goal:** Learn how to reliably instruct LLMs for developer and enterprise use cases.

### Topics

- Prompt types: zero-shot, few-shot, multi-shot, role-based, markdown, instruction-based, constraint-based
- Recommended prompt structure: Role → Task → Context → Constraints → Output Format → Examples
- Model parameters: `temperature`, `top_p`, `max_output_tokens`, `stream`, `frequency_penalty`
- Prompt testing: short input, long input, missing input, malicious input, ambiguous input

### Mini project

| Project | Description |
|---|---|
| Mini project 3 — Prompt Playground | Web UI or API to adjust system prompt, user prompt, temperature, max tokens, and output format |

### Resources

| Resource | Link |
|---|---|
| DeepLearning.AI Prompt Engineering | https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/ |
| OpenAI prompt engineering guide | https://platform.openai.com/docs/guides/prompt-engineering |
| Microsoft prompt engineering guide | https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/prompt-engineering |

---

## Stage 4 — Embeddings and Semantic Search

**Goal:** Understand how text becomes vectors and how semantic search powers RAG.

### Topics

- Embeddings: semantic meaning as vectors, similar text → nearby vectors, use cases
- Similarity metrics: cosine similarity, dot product, Euclidean distance
- Vector indexes: approximate nearest neighbor (ANN), HNSW
- Vector databases: collection, documents, metadata, filtering, hybrid search

### Vector database options

FAISS · Chroma · Qdrant · Pinecone · Weaviate · Azure AI Search · pgvector

### Mini project

| Project | Description |
|---|---|
| Mini project 4 — Semantic Search API | Accept documents, create embeddings, store vectors, search by semantic similarity, return top chunks |

### Resources

| Resource | Link |
|---|---|
| Azure AI Search vector search | https://learn.microsoft.com/en-us/azure/search/vector-search-overview |
| Pinecone RAG guide | https://www.pinecone.io/learn/retrieval-augmented-generation/ |
| FAISS GitHub | https://github.com/facebookresearch/faiss |
| Chroma docs | https://docs.trychroma.com/ |
| Qdrant docs | https://qdrant.tech/documentation/ |

---

## Stage 5 — RAG Fundamentals

**Goal:** Build applications that answer using your data instead of only relying on model memory.

### What is RAG?

Retrieval-Augmented Generation combines:

1. User question
2. Retrieval from external knowledge base
3. Relevant context injection into prompt
4. LLM-generated answer grounded in retrieved context

### Why RAG?

- Answer from private enterprise data
- Reduce hallucination
- Keep answers up to date
- Avoid expensive fine-tuning
- Cite sources

### Core RAG pipeline

```text
Documents → Load/Parse → Clean/Normalize → Chunk → Embed
  → Store in Vector DB → Retrieve relevant chunks
  → Inject context into prompt → Generate answer → Return with citations
```

### Topics

- **Document ingestion:** PDF, DOCX, HTML, CSV/Excel, database, SharePoint
- **Chunking strategies:** fixed-size, recursive, semantic, parent-child, overlap, metadata enrichment
- **Retrieval methods:** vector similarity, keyword search, BM25, hybrid search, metadata filtering
- **Answer generation:** user question + retrieved context + citation requirement + fallback behavior

### Mini project

| Project | Description |
|---|---|
| Mini project 5 — PDF Q&A Bot | PDF upload → chunking → embeddings → vector DB → chat endpoint → answer with citations |

### Resources

| Resource | Link |
|---|---|
| Azure Search + OpenAI demo | https://github.com/Azure-Samples/azure-search-openai-demo |
| LangChain docs | https://python.langchain.com/docs/ |
| LlamaIndex docs | https://developers.llamaindex.ai/python/framework/ |

---

## Stage 6 — Advanced RAG

**Goal:** Improve RAG quality, speed, cost, and reliability.

### Topics

| Topic | Details |
|---|---|
| Retrieval optimization | top-k tuning, score thresholds, reranking, query rewriting, multi-query retrieval, contextual compression |
| Hybrid search | keyword + vector + semantic reranking |
| Reranking | Reorder retrieved documents before generation |
| Query transformation | rewrite vague queries, generate multiple queries, decompose complex questions |
| Multimodal RAG | Handle text, tables, images, scanned PDFs, diagrams, screenshots |
| RAG evaluation | retrieval precision/recall, faithfulness, answer relevance, hallucination rate |

### Mini project

| Project | Description |
|---|---|
| Mini project 6 — Enterprise Knowledge Assistant | Document upload, metadata filters, hybrid search, citations, feedback button, admin ingestion pipeline, evaluation dataset |

### Resources

| Resource | Link |
|---|---|
| RAGAS docs | https://docs.ragas.io/en/latest/getstarted/rag_eval/ |
| Azure AI Search hybrid search | https://learn.microsoft.com/en-us/azure/search/hybrid-search-overview |
| LangSmith evaluation | https://docs.langchain.com/langsmith/home |

---

## Stage 7 — Orchestration Frameworks

**Goal:** Learn the major orchestration frameworks and know when to use each.

### LangChain

Use for: LLM chains, prompt templates, tools, retrievers, quick prototypes, integration ecosystem.

Key concept — LCEL (LangChain Expression Language): prompt → model → output parser, composable chains, streaming, batching, retries.

| Resource | Link |
|---|---|
| LangChain docs | https://python.langchain.com/docs/ |
| LangChain GitHub | https://github.com/langchain-ai/langchain |

### LlamaIndex

Use for: data ingestion, indexing, RAG over private data, query engines, document agents, workflows.

| Resource | Link |
|---|---|
| LlamaIndex docs | https://developers.llamaindex.ai/python/framework/ |
| LlamaIndex GitHub | https://github.com/run-llama/llama_index |

### Semantic Kernel / Microsoft Agent Framework

Use for: enterprise Microsoft/Azure solutions, plugins/tools, agentic workflows, Azure AI Foundry and Microsoft 365 integration.

| Resource | Link |
|---|---|
| Semantic Kernel docs | https://learn.microsoft.com/en-us/semantic-kernel/ |
| Semantic Kernel GitHub | https://github.com/microsoft/semantic-kernel |

---

## Stage 8 — Agentic AI

**Goal:** Move beyond prompt-response apps into systems that can plan, call tools, remember, and execute workflows.

### LLM vs Agent

| LLM | Agent |
|---|---|
| Responds to prompts | Has goals and instructions |
| Does not act without tools | Can decide steps |
| — | Can call tools |
| — | Can use memory |
| — | Can interact with external systems |
| — | May involve human approval |

### Topics

- **Tool calling:** function/tool schemas, input validation, tool execution, error handling, retries, result summarization
- **Human-in-the-loop:** approval for emails, deletes, financial actions, production changes, sensitive data
- **Memory management:** short-term, long-term, conversation memory, user preferences, vector memory, privacy/expiry
- **Agent orchestration patterns:** single agent with tools · planner-executor · supervisor-worker · multi-agent collaboration

### Agent frameworks (learn at least two)

- LangGraph
- CrewAI
- Microsoft Agent Framework / Semantic Kernel
- AutoGen

### Mini projects

| Project | Description |
|---|---|
| Mini project 7 — Tool-Calling Agent | Answer questions, search knowledge base, calculator, mock ticket API, human approval before final action |
| Mini project 8 — Multi-Agent Research Workflow | Research Agent → Summarizer → Critic → Final Writer |

### Resources

| Resource | Link |
|---|---|
| LangGraph docs | https://langchain-ai.github.io/langgraph/ |
| CrewAI docs | https://docs.crewai.com/ |
| AutoGen docs | https://microsoft.github.io/autogen/stable/index.html |
| Microsoft OpenAI Workshop | https://github.com/microsoft/OpenAIWorkshop |

---

## Stage 9 — MCP and A2A

**Goal:** Understand emerging standards for connecting agents to tools and to other agents.

### MCP — Model Context Protocol

MCP provides a standard way for AI applications to connect to tools, data sources, and workflows.

Learn: MCP server · MCP client · tools · resources · prompts · transports · local vs remote MCP servers

### A2A — Agent-to-Agent communication

Understand how agents discover and communicate with each other, how responsibilities are split across specialized agents, and how governance/access control apply.

### Mini project

| Project | Description |
|---|---|
| Mini project 9 — Simple MCP-style Tool Server | Local tool server exposing file search, calculator, ticket lookup, document summary |

### Resources

| Resource | Link |
|---|---|
| MCP official docs | https://modelcontextprotocol.io/docs/getting-started/intro |
| MCP GitHub | https://github.com/modelcontextprotocol/modelcontextprotocol |
| OpenAI Agents SDK MCP | https://openai.github.io/openai-agents-python/mcp/ |

---

## Stage 10 — Observability and Evaluation

**Goal:** Make LLM and agent apps debuggable, measurable, and production-ready.

### Topics

| Topic | Key items to track |
|---|---|
| Observability | prompt, model, latency, token usage, cost, retrieved chunks, tool calls, agent steps, errors |
| Tracing | wrong context retrieval, wrong tool calls, latency spikes, prompt version regressions |
| Evaluation | answer correctness, faithfulness, relevance, retrieval quality, tool-call success, task completion |
| Versioning | prompts, chains, agent instructions, retrieval configs, model settings, evaluation datasets |

### Mini project

| Project | Description |
|---|---|
| Mini project 10 — Add Tracing and Evaluation | Add LangSmith traces, token/cost logging, evaluation dataset, RAGAS metrics, feedback capture to existing RAG app |

### Resources

| Resource | Link |
|---|---|
| LangSmith docs | https://docs.langchain.com/langsmith/home |
| RAGAS docs | https://docs.ragas.io/en/latest/getstarted/rag_eval/ |
| Azure AI Foundry | https://ai.azure.com/ |
| Azure Monitor | https://learn.microsoft.com/en-us/azure/azure-monitor/ |

---

## Stage 11 — Security, Privacy, and Governance

**Goal:** Design GenAI applications safely for enterprise use.

### Common GenAI risks

hallucination · prompt injection · data leakage · insecure tool execution · excessive permissions · PII exposure · unsafe autonomous actions

### Topics

| Topic | Approach |
|---|---|
| PII detection and masking | PII detection, anonymization, masking, redaction, allow lists, custom recognizers |
| Prompt injection defense | system prompt hardening, instruction hierarchy, retrieved-content isolation, tool allowlists, output validation |
| Access control | document-level permissions, user identity propagation, metadata filters, Entra ID integration |

### Mini project

| Project | Description |
|---|---|
| Mini project 11 — Secure RAG | Add user authentication, document-level metadata filtering, PII masking, prompt injection test cases, tool allowlist |

### Resources

| Resource | Link |
|---|---|
| Microsoft Presidio docs | https://microsoft.github.io/presidio/ |
| Microsoft Presidio GitHub | https://github.com/microsoft/presidio |
| OWASP Top 10 for LLM Apps | https://owasp.org/www-project-top-10-for-large-language-model-applications/ |
| Azure OpenAI Content Filter | https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/content-filter |

---

## Stage 12 — Production Deployment and Architecture

**Goal:** Deploy scalable GenAI systems with proper architecture.

### Production architecture

```text
Frontend
  ↓
API Gateway / Auth
  ↓
FastAPI Backend
  ↓
Orchestration Layer
  ↓
LLM Provider / Model Router
  ↓
Retrieval Layer
  ↓
Vector DB / Search Engine
  ↓
Observability + Evaluation + Logs
```

### Topics

| Topic | Details |
|---|---|
| Deployment | Docker, Docker Compose, Azure App Service, Azure Container Apps, Azure Functions, GitHub Actions CI/CD |
| Scalability | async processing, queue-based ingestion, caching, rate limits, retries, circuit breakers, batch embeddings |
| Cost optimization | track input/output/embedding/retrieval/reranker tokens; use smaller models for simple tasks; cache common answers |
| Model selection | quality · latency · cost · context window · tool calling support · structured output · multimodal · compliance |

### Mini project

| Project | Description |
|---|---|
| Mini project 12 — Production GenAI Starter Kit | FastAPI backend, Dockerfile, env config, LLM/vector DB abstraction, logging, tracing, evaluation script, deployment guide |

### Resources

| Resource | Link |
|---|---|
| Azure Container Apps | https://learn.microsoft.com/en-us/azure/container-apps/ |
| Azure App Service | https://learn.microsoft.com/en-us/azure/app-service/ |
| GitHub Actions | https://docs.github.com/en/actions |
| Docker docs | https://docs.docker.com/ |
| Azure Search OpenAI demo | https://github.com/Azure-Samples/azure-search-openai-demo |

---

## 12-Week Learning Plan

| Week | Focus | Build | Deliverable |
|---|---|---|---|
| 1 | GenAI Basics — AI vs GenAI, LLM basics, tokens, context window, model parameters | Prompt experiments | Notes on tokens, temperature, context, hallucination |
| 2 | Python LLM API Development — OpenAI/Azure OpenAI, FastAPI, env variables | Basic chat API + summarization API | GitHub repo: `llm-fastapi-basics` |
| 3 | Prompt Engineering — role prompting, few-shot, structured JSON, prompt testing | Prompt playground | Reusable prompt templates |
| 4 | Embeddings and Vector Search — embeddings, cosine similarity, vector DB basics | Semantic search API | GitHub repo: `semantic-search-python` |
| 5 | Basic RAG — ingestion, chunking, retrieval, answer generation | PDF Q&A bot | GitHub repo: `pdf-rag-chatbot` |
| 6 | Advanced RAG — hybrid search, reranking, metadata filters, citations | Enterprise knowledge assistant v1 | RAG app with source citations |
| 7 | RAG Evaluation — RAGAS, faithfulness, answer relevance, context precision/recall | Evaluation dataset + automated evaluation script | RAG score report |
| 8 | LangChain and LlamaIndex — LCEL, retrievers, query engines, data connectors | Same RAG flow in both LangChain and LlamaIndex | Comparison notes: LangChain vs LlamaIndex |
| 9 | Agentic AI Basics — LLM vs agent, tool calling, memory, human-in-loop | Tool-calling assistant | GitHub repo: `tool-calling-agent` |
| 10 | Multi-Agent Workflows — LangGraph, CrewAI, supervisor-worker pattern, agent state | Multi-agent research assistant | Workflow diagram + code |
| 11 | Observability and Security — tracing, token/cost monitoring, PII detection, prompt injection mitigation | Add LangSmith traces and Presidio PII masking | Secure + observable RAG/agent app |
| 12 | Production Architecture — Docker, deployment, CI/CD, cloud architecture, cost optimization | Deploy final capstone app | Architecture document + deployed demo |

---

## Capstone Projects

### Capstone 1 — Enterprise Document Assistant

Features: document upload · background ingestion · chunking and embeddings · hybrid retrieval · citations · auth-ready design · feedback capture · RAGAS evaluation · LangSmith tracing · Docker deployment

**Recommended stack:** FastAPI · React · Azure OpenAI / OpenAI · Azure AI Search / Qdrant / Chroma · LangChain or LlamaIndex · LangSmith · Docker

---

### Capstone 2 — DMS Knowledge Assistant

Features: document metadata extraction · document classification · policy Q&A · access-aware retrieval · summarization · ticket/action recommendation · audit logs

```text
User → Frontend → FastAPI → Auth + Permissions
  → Document/RAG Service → Vector DB + Metadata DB
  → LLM Response with Citations → Tracing + Evaluation + Logs
```

---

### Capstone 3 — Agentic Workflow Automation Assistant

Features: classify incoming request · retrieve relevant knowledge · decide next action · call tools/APIs · ask for approval · create ticket or draft response · trace all steps

**Agent roles:** Planner Agent · Retrieval Agent · Tool Agent · Validation Agent · Final Response Agent

---

## Tools Checklist

### Programming
- Python · FastAPI · Pydantic · AsyncIO · pytest

### LLM providers
- Azure OpenAI · OpenAI API · Hugging Face models · Ollama (local models)

### Frameworks
- LangChain · LlamaIndex · LangGraph · CrewAI · Semantic Kernel / Microsoft Agent Framework

### Vector databases / Search
- Chroma · Qdrant · FAISS · Pinecone · Weaviate · Azure AI Search · pgvector

### Evaluation and observability
- LangSmith · RAGAS · Azure AI Foundry traces · Azure Monitor · OpenTelemetry

### Security
- Microsoft Presidio · OWASP LLM Top 10 · authentication/authorization · secret management

### Deployment
- Docker · Docker Compose · Azure App Service · Azure Container Apps · GitHub Actions

---

## GitHub Portfolio Structure

Create these repositories as you progress through the roadmap:

```text
genai-learning-notes
llm-fastapi-basics
prompt-playground
semantic-search-python
pdf-rag-chatbot
advanced-rag-evaluation
tool-calling-agent
multi-agent-research-assistant
secure-rag-presidio
production-genai-starter-kit
```

Each repository should include:
- README with setup instructions
- Architecture diagram
- `.env.example`
- Sample data
- Screenshots
- Known limitations
- Future improvements

---

## Architecture Decision Guide

| Pattern | Use when | Examples |
|---|---|---|
| Simple prompting | No private data needed, simple output, low risk, no tools | Rewrite email, summarize short text, generate boilerplate code |
| RAG | Answer depends on private/changing data, citations needed | Policy Q&A, document assistant, knowledge base chatbot |
| Fine-tuning | Style/format adaptation needed, many high-quality examples available, repeated narrow behavior | Custom tone, domain-specific format — not for adding knowledge |
| Agents | Multi-step task, tools/APIs must be called, dynamic branching | Workflow automation, research assistant, ticketing actions |
| Deterministic workflows | Predictable process, strict compliance/audit | Approval pipelines, financial flows, regulated processes |

> **Best production pattern:** Deterministic workflow + LLM decision points + human approval for sensitive actions

---

## Master Resource List

### Official / Core
| Resource | Link |
|---|---|
| Azure OpenAI | https://learn.microsoft.com/en-us/azure/ai-services/openai/ |
| Azure AI Foundry | https://ai.azure.com/ |
| OpenAI API docs | https://developers.openai.com/api/docs/ |
| Hugging Face | https://huggingface.co/ |

### Frameworks
| Resource | Link |
|---|---|
| LangChain docs | https://python.langchain.com/docs/ |
| LangGraph docs | https://langchain-ai.github.io/langgraph/ |
| LangSmith docs | https://docs.langchain.com/langsmith/home |
| LlamaIndex docs | https://developers.llamaindex.ai/python/framework/ |
| Semantic Kernel | https://learn.microsoft.com/en-us/semantic-kernel/ |

### Agents
| Resource | Link |
|---|---|
| CrewAI docs | https://docs.crewai.com/ |
| CrewAI quickstarts | https://github.com/crewAIInc/crewAI-quickstarts |
| AutoGen docs | https://microsoft.github.io/autogen/stable/index.html |
| Microsoft OpenAI Workshop | https://github.com/microsoft/OpenAIWorkshop |

### RAG and Search
| Resource | Link |
|---|---|
| Azure Search OpenAI demo | https://github.com/Azure-Samples/azure-search-openai-demo |
| Azure AI Search hybrid search | https://learn.microsoft.com/en-us/azure/search/hybrid-search-overview |
| Pinecone RAG guide | https://www.pinecone.io/learn/retrieval-augmented-generation/ |

### Evaluation
| Resource | Link |
|---|---|
| RAGAS docs | https://docs.ragas.io/en/latest/getstarted/rag_eval/ |
| LangSmith docs | https://docs.langchain.com/langsmith/home |

### Security and Governance
| Resource | Link |
|---|---|
| Microsoft Presidio | https://microsoft.github.io/presidio/ |
| OWASP LLM Top 10 | https://owasp.org/www-project-top-10-for-large-language-model-applications/ |

### MCP and Standards
| Resource | Link |
|---|---|
| MCP official docs | https://modelcontextprotocol.io/docs/getting-started/intro |
| OpenAI Agents SDK MCP | https://openai.github.io/openai-agents-python/mcp/ |

---

## Completion Checklist

Track your progress as you work through the roadmap:

```text
[ ] Understand LLM basics, tokens, context window
[ ] Build basic FastAPI LLM API
[ ] Build prompt playground
[ ] Build semantic search API
[ ] Build PDF RAG chatbot
[ ] Add citations to RAG answers
[ ] Add hybrid search or reranking
[ ] Add RAGAS evaluation
[ ] Learn LangChain LCEL basics
[ ] Learn LlamaIndex query engine basics
[ ] Build tool-calling agent
[ ] Build multi-agent workflow
[ ] Add LangSmith tracing
[ ] Add PII masking with Presidio
[ ] Add Docker deployment
[ ] Create architecture document
[ ] Publish portfolio repos on GitHub
```

---

> Build → Measure → Improve → Secure → Deploy → Document