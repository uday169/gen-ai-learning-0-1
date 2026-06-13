# Generative AI, RAG, and Agentic AI Roadmap

**Personalized for:** Python Full-Stack Developer moving toward **GenAI Developer + GenAI Architect**  
**Focus areas:** LLM applications, RAG, Agents, evaluation, observability, production architecture  
**Prepared date:** 2026-06-10

---

## 0. How to Use This Roadmap

This roadmap is designed to convert your existing Python full-stack background into advanced GenAI capability.

### Recommended learning ratio

- **30% Concepts**: LLMs, embeddings, RAG, agents, architecture patterns
- **50% Hands-on Building**: APIs, RAG apps, agent workflows, deployment
- **20% Optimization**: evaluation, observability, cost, latency, security

### Expected outcome

By the end of this roadmap, you should be able to:

- Build LLM-powered APIs using Python and FastAPI
- Design and implement Retrieval-Augmented Generation systems
- Build agentic workflows using tools, memory, and orchestration
- Evaluate RAG and agent systems using metrics and traces
- Deploy production-grade GenAI applications with monitoring, cost controls, and security
- Think like a GenAI architect: model selection, retrieval strategy, orchestration, deployment, governance

---

## 1. High-Level Roadmap Summary

```text
Stage 1: GenAI Foundations
Stage 2: LLM App Development
Stage 3: Prompt Engineering and Structured Output
Stage 4: Embeddings and Semantic Search
Stage 5: RAG Fundamentals
Stage 6: Advanced RAG
Stage 7: Agentic AI
Stage 8: Observability and Evaluation
Stage 9: Security, Governance, and PII Protection
Stage 10: Production Deployment and Architecture
Stage 11: Capstone Projects
```

---

## 2. Stage 1 — GenAI Foundations

### Goal
Understand what Generative AI is, how LLMs work, and why modern applications use LLMs differently from traditional software.

### Topics to learn

#### 2.1 AI vs ML vs Deep Learning vs GenAI

Learn the difference between:

- Artificial Intelligence
- Machine Learning
- Deep Learning
- Generative AI
- Large Language Models

#### 2.2 Large Language Models

Understand:

- What an LLM is
- Why LLMs generate text token by token
- Why LLMs are probabilistic, not deterministic
- Why LLMs can hallucinate
- Why context matters

#### 2.3 Transformers

Learn at a conceptual level:

- Encoder-decoder architecture
- Self-attention
- Positional encoding
- Why transformer architecture became the foundation of modern LLMs

You do **not** need to implement a transformer from scratch initially. As a developer/architect, focus first on understanding its behavior and limitations.

#### 2.4 Tokens and Tokenization

Understand:

- Text is split into tokens before being processed by an LLM
- Token count affects cost, latency, and context limits
- Different models may tokenize the same text differently

#### 2.5 Context Window

Understand:

- Context window = maximum tokens the model can process in one request
- Large context helps with long documents but does not replace good retrieval
- More context can increase cost and latency

### Hands-on practice

- Use a tokenizer tool and test how paragraphs are converted into tokens
- Compare short vs long prompts
- Ask the same question with different context sizes
- Observe how output changes when you add or remove relevant context

### Resources

- Microsoft Learn — Introduction to AI: https://learn.microsoft.com/en-us/training/paths/get-started-with-artificial-intelligence/
- Azure OpenAI overview: https://learn.microsoft.com/en-us/azure/ai-services/openai/
- OpenAI API docs: https://developers.openai.com/api/docs/
- Hugging Face NLP course: https://huggingface.co/learn/nlp-course/chapter1/1
- Illustrated Transformer: https://jalammar.github.io/illustrated-transformer/

---

## 3. Stage 2 — LLM Application Development

### Goal
Use your Python full-stack skills to build real LLM applications quickly.

### Core stack

- Python
- FastAPI
- Pydantic
- OpenAI SDK or Azure OpenAI SDK
- Environment variables
- Docker basics
- Postman or REST Client

### Topics to learn

#### 3.1 Calling LLM APIs

Understand:

- API keys
- Model names/deployments
- Request-response format
- Chat messages
- System, user, and assistant roles
- Streaming vs non-streaming responses

#### 3.2 FastAPI integration

Build endpoints such as:

```http
POST /chat
POST /summarize
POST /extract
POST /classify
```

#### 3.3 Structured output

Learn to force models to return:

- JSON
- Typed response objects
- Validated data using Pydantic

#### 3.4 Streaming responses

Learn streaming for:

- Chat UX
- Long responses
- Better perceived latency

### Mini project 1 — Basic LLM Chat API

Build a FastAPI service with:

- `/chat` endpoint
- request body with `user_message`
- model response
- error handling
- environment variable based API key
- simple logging

### Mini project 2 — Text Utility API

Create endpoints:

- `/summarize`
- `/rewrite`
- `/translate`
- `/extract-json`

### Resources

- OpenAI SDKs and CLI: https://developers.openai.com/api/docs/libraries
- Azure OpenAI docs: https://learn.microsoft.com/en-us/azure/ai-services/openai/
- FastAPI docs: https://fastapi.tiangolo.com/
- Pydantic docs: https://docs.pydantic.dev/
- Python dotenv: https://pypi.org/project/python-dotenv/

---

## 4. Stage 3 — Prompt Engineering and Model Parameters

### Goal
Learn how to reliably instruct LLMs for developer and enterprise use cases.

### Topics to learn

#### 4.1 Prompt types

- Zero-shot prompting
- Few-shot prompting
- Multi-shot prompting
- Role-based prompting
- Markdown prompting
- Instruction-based prompting
- Constraint-based prompting

#### 4.2 Prompt structure

Recommended structure:

```text
Role: Who should the model act as?
Task: What should the model do?
Context: What information should the model use?
Constraints: What should it avoid or follow?
Output Format: JSON, Markdown, bullet list, table, etc.
Examples: Optional few-shot examples.
```

#### 4.3 Model parameters

Learn:

- `temperature`: creativity/randomness
- `top_p`: sampling diversity
- `max_output_tokens`: output length control
- `stream`: token-by-token output
- `frequency_penalty` and `presence_penalty` where supported

#### 4.4 Prompt testing

For every important prompt, test:

- short input
- long input
- missing input
- malicious input
- ambiguous input
- irrelevant input

### Mini project 3 — Prompt Playground

Build a small web UI or API where you can change:

- system prompt
- user prompt
- temperature
- max tokens
- output format

Save prompt versions in a JSON file or database.

### Resources

- DeepLearning.AI Prompt Engineering for Developers: https://www.deeplearning.ai/short-courses/chatgpt-prompt-engineering-for-developers/
- OpenAI prompt engineering guide: https://platform.openai.com/docs/guides/prompt-engineering
- Microsoft prompt engineering concepts: https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/prompt-engineering
- LangSmith prompt management: https://docs.langchain.com/langsmith/home

---

## 5. Stage 4 — Embeddings and Semantic Search

### Goal
Understand how text becomes vectors and how semantic search powers RAG.

### Topics to learn

#### 5.1 Embeddings

Learn:

- Embeddings represent semantic meaning as vectors
- Similar text should have nearby vectors
- Embeddings are used for search, clustering, classification, recommendations, and RAG

#### 5.2 Similarity metrics

Understand:

- Cosine similarity
- Dot product
- Euclidean distance

#### 5.3 Vector indexes

Learn why indexes are needed:

- Brute-force vector search is expensive at scale
- Approximate nearest neighbor search improves speed
- HNSW is a common indexing method

#### 5.4 Vector databases

Learn core concepts:

- collection/index
- documents/chunks
- metadata
- filtering
- similarity search
- hybrid search

### Tools to explore

- FAISS
- Chroma
- Qdrant
- Pinecone
- Weaviate
- Azure AI Search
- PostgreSQL + pgvector

### Mini project 4 — Semantic Search API

Build an API that:

- accepts documents
- creates embeddings
- stores vectors
- searches by semantic similarity
- returns top matching chunks

### Resources

- Azure AI Search vector search: https://learn.microsoft.com/en-us/azure/search/vector-search-overview
- Pinecone learning center — RAG: https://www.pinecone.io/learn/retrieval-augmented-generation/
- FAISS GitHub: https://github.com/facebookresearch/faiss
- Chroma docs: https://docs.trychroma.com/
- Qdrant docs: https://qdrant.tech/documentation/
- pgvector GitHub: https://github.com/pgvector/pgvector

---

## 6. Stage 5 — RAG Fundamentals

### Goal
Build applications that answer using your data instead of only relying on model memory.

### 6.1 What is RAG?

Retrieval-Augmented Generation combines:

1. User question
2. Retrieval from external knowledge base
3. Relevant context injection into prompt
4. LLM-generated answer grounded in retrieved context

### 6.2 Why RAG is used

RAG helps with:

- answering from private enterprise data
- reducing hallucination
- keeping answers up to date
- avoiding expensive fine-tuning for many knowledge tasks
- citing sources

### 6.3 Core RAG pipeline

```text
Documents
  ↓
Load / Parse
  ↓
Clean / Normalize
  ↓
Chunk
  ↓
Embed
  ↓
Store in Vector DB
  ↓
Retrieve relevant chunks
  ↓
Inject context into prompt
  ↓
Generate answer
  ↓
Return answer with citations
```

### 6.4 Document ingestion

Learn:

- PDF loading
- DOCX loading
- HTML loading
- CSV/Excel loading
- database ingestion
- SharePoint/OneDrive ingestion where applicable

### 6.5 Chunking strategies

Learn:

- fixed-size chunking
- recursive chunking
- semantic chunking
- parent-child chunking
- overlap handling
- metadata enrichment

### 6.6 Retrieval methods

Learn:

- vector similarity search
- keyword search
- BM25
- hybrid search
- semantic ranking
- metadata filtering

### 6.7 Answer generation

Prompt should include:

- user question
- retrieved context
- answer instructions
- citation requirement
- fallback behavior when answer is not found

### Mini project 5 — PDF Q&A Bot

Build:

- PDF upload
- chunking
- embeddings
- vector database storage
- chat endpoint
- answer with citations

### Resources

- Azure Search + OpenAI demo: https://github.com/Azure-Samples/azure-search-openai-demo
- Microsoft sample — RAG chat app with your data: https://learn.microsoft.com/en-us/samples/azure-samples/azure-search-openai-demo/azure-search-openai-demo/
- LangChain docs: https://python.langchain.com/docs/
- LlamaIndex docs: https://developers.llamaindex.ai/python/framework/
- LlamaIndex GitHub: https://github.com/run-llama/llama_index

---

## 7. Stage 6 — Advanced RAG

### Goal
Improve RAG quality, speed, cost, and reliability.

### Topics to learn

#### 7.1 Retrieval optimization

- top-k tuning
- score thresholds
- reranking
- query rewriting
- multi-query retrieval
- contextual compression
- metadata filtering

#### 7.2 Hybrid search

Combine:

- keyword search for exact terms
- vector search for semantic meaning
- semantic reranking for relevance

#### 7.3 Reranking

Use rerankers to reorder retrieved documents before generation.

#### 7.4 Query transformation

Examples:

- rewrite vague query into precise query
- generate multiple search queries
- decompose complex question into subquestions

#### 7.5 Multimodal RAG

Learn how to handle:

- text
- tables
- images
- scanned PDFs
- diagrams
- screenshots

#### 7.6 RAG evaluation

Evaluate:

- retrieval precision
- retrieval recall
- faithfulness
- answer relevance
- context relevance
- hallucination rate

### Mini project 6 — Enterprise Knowledge Assistant

Build a more complete RAG app with:

- document upload
- metadata filters
- hybrid search
- citations
- feedback button
- admin ingestion pipeline
- evaluation dataset

### Resources

- RAGAS docs: https://docs.ragas.io/en/latest/getstarted/rag_eval/
- RAGAS GitHub: https://github.com/vibrantlabsai/ragas
- LlamaIndex evaluation docs: https://developers.llamaindex.ai/python/framework/
- LangSmith evaluation docs: https://docs.langchain.com/langsmith/home
- Azure AI Search hybrid search: https://learn.microsoft.com/en-us/azure/search/hybrid-search-overview

---

## 8. Stage 7 — LangChain, LlamaIndex, and Microsoft Semantic Kernel / Agent Framework

### Goal
Learn the major orchestration frameworks and know when to use each.

### 8.1 LangChain

Use LangChain for:

- LLM chains
- prompt templates
- tools
- retrievers
- quick prototypes
- integration ecosystem

Resources:

- LangChain docs: https://python.langchain.com/docs/
- LangChain GitHub: https://github.com/langchain-ai/langchain
- LangChain docs GitHub: https://github.com/langchain-ai/docs

### 8.2 LCEL — LangChain Expression Language

Learn:

- prompt → model → output parser
- composable chains
- streaming
- batching
- retries

Practice:

- build summarization chain
- build classification chain
- build extraction chain

### 8.3 LlamaIndex

Use LlamaIndex for:

- data ingestion
- indexing
- RAG over private data
- query engines
- document agents
- workflows

Resources:

- LlamaIndex docs: https://developers.llamaindex.ai/python/framework/
- LlamaIndex GitHub: https://github.com/run-llama/llama_index

### 8.4 Semantic Kernel / Microsoft Agent Framework

Use Microsoft ecosystem when:

- building enterprise Microsoft/Azure aligned solutions
- integrating with plugins/tools
- building agentic workflows
- working with Azure AI Foundry, Microsoft 365, or enterprise governance

Resources:

- Semantic Kernel docs: https://learn.microsoft.com/en-us/semantic-kernel/
- Semantic Kernel GitHub: https://github.com/microsoft/semantic-kernel
- Microsoft OpenAI Workshop: https://github.com/microsoft/OpenAIWorkshop

---

## 9. Stage 8 — Agentic AI

### Goal
Move beyond prompt-response apps into systems that can plan, call tools, remember, and execute workflows.

### 9.1 LLM vs Agent

LLM:

- responds to prompts
- does not inherently act unless connected to tools

Agent:

- has goals/instructions
- can decide steps
- can call tools
- can use memory
- can interact with external systems
- may involve human approval

### 9.2 Tool calling

Learn:

- function/tool schemas
- input validation
- tool execution
- error handling
- retries
- tool result summarization

Examples of tools:

- search documents
- query database
- call REST API
- send email
- create ticket
- run Python code in controlled environment

### 9.3 Human-in-the-loop

Use human approval for:

- sending emails
- deleting records
- financial actions
- production changes
- sensitive data workflows

### 9.4 Memory management

Learn:

- short-term memory
- long-term memory
- conversation memory
- user preferences
- vector memory
- memory privacy and expiry

### 9.5 Agent orchestration

Patterns:

- single agent with tools
- planner-executor
- supervisor-worker
- multi-agent collaboration
- deterministic workflow + agent decision points

### 9.6 Agent frameworks

Learn at least two:

- LangGraph
- CrewAI
- Microsoft Agent Framework / Semantic Kernel
- AutoGen for existing Microsoft examples, but check current maintenance direction before starting new projects

### Mini project 7 — Tool-Calling Agent

Build an agent that can:

- answer questions
- search your knowledge base
- call a calculator
- call a mock ticket API
- ask for human approval before final action

### Mini project 8 — Multi-Agent Research Workflow

Agents:

- Research Agent
- Summarizer Agent
- Critic Agent
- Final Writer Agent

Workflow:

```text
User topic → Research Agent → Summarizer → Critic → Final Answer
```

### Resources

- LangGraph GitHub: https://github.com/langchain-ai/langgraph
- LangGraph docs: https://langchain-ai.github.io/langgraph/
- CrewAI GitHub: https://github.com/crewAIInc/crewAI
- CrewAI docs: https://docs.crewai.com/
- CrewAI quickstarts: https://github.com/crewAIInc/crewAI-quickstarts
- AutoGen GitHub: https://github.com/microsoft/autogen
- AutoGen docs: https://microsoft.github.io/autogen/stable/index.html
- Microsoft OpenAI Workshop: https://github.com/microsoft/OpenAIWorkshop

---

## 10. Stage 9 — MCP, A2A, and Tool Ecosystem

### Goal
Understand emerging standards for connecting agents to tools and to other agents.

### 10.1 MCP — Model Context Protocol

MCP provides a standard way for AI applications to connect to tools, data sources, and workflows.

Learn:

- MCP server
- MCP client
- tools
- resources
- prompts
- transports
- local vs remote MCP servers

### 10.2 A2A — Agent-to-Agent communication

Understand conceptually:

- how agents can discover and communicate with other agents
- how responsibilities can be split across specialized agents
- how governance and access control become important

### Mini project 9 — Simple MCP-style Tool Server

Build a simple local tool server exposing:

- file search
- calculator
- ticket lookup
- document summary

### Resources

- MCP official docs: https://modelcontextprotocol.io/docs/getting-started/intro
- MCP GitHub: https://github.com/modelcontextprotocol/modelcontextprotocol
- OpenAI Agents SDK MCP docs: https://openai.github.io/openai-agents-python/mcp/

---

## 11. Stage 10 — Observability, Tracing, and Evaluation

### Goal
Make LLM and agent apps debuggable, measurable, and production-ready.

### Topics to learn

#### 11.1 Observability

Track:

- prompt
- model
- latency
- token usage
- cost
- retrieved chunks
- tool calls
- intermediate agent steps
- final output
- errors

#### 11.2 Tracing

Use traces to debug:

- why wrong context was retrieved
- why an agent called the wrong tool
- where latency increased
- which prompt version caused regression

#### 11.3 Evaluation

Evaluate:

- answer correctness
- faithfulness
- relevance
- retrieval quality
- tool-call success
- agent task completion

#### 11.4 Prompt and workflow versioning

Version:

- prompts
- chains
- agent instructions
- retrieval configs
- model settings
- evaluation datasets

### Mini project 10 — Add Tracing and Evaluation to RAG App

Add:

- LangSmith traces
- token/cost logging
- evaluation dataset
- RAGAS metrics
- feedback capture

### Resources

- LangSmith docs: https://docs.langchain.com/langsmith/home
- LangSmith reference: https://docs.langchain.com/langsmith/reference
- RAGAS docs: https://docs.ragas.io/en/latest/getstarted/rag_eval/
- Azure AI Foundry: https://ai.azure.com/
- Azure Monitor: https://learn.microsoft.com/en-us/azure/azure-monitor/

---

## 12. Stage 11 — Security, Privacy, and Governance

### Goal
Design GenAI applications safely for enterprise use.

### Topics to learn

#### 12.1 Common GenAI risks

- hallucination
- prompt injection
- data leakage
- insecure tool execution
- excessive permissions
- PII exposure
- unsafe autonomous actions

#### 12.2 PII detection and masking

Use PII tools before sending sensitive content to LLMs where required.

Learn:

- PII detection
- anonymization
- masking
- redaction
- allow lists
- custom recognizers

#### 12.3 Prompt injection defense

Apply:

- system prompt hardening
- instruction hierarchy
- retrieved-content isolation
- tool allowlists
- output validation
- human approval for sensitive actions

#### 12.4 Access control

For enterprise RAG:

- document-level permissions
- user identity propagation
- metadata filters
- Entra ID integration where applicable

### Mini project 11 — Secure RAG

Add to your RAG app:

- user authentication
- document-level metadata filtering
- PII masking
- prompt injection test cases
- tool allowlist

### Resources

- Microsoft Presidio GitHub: https://github.com/microsoft/presidio
- Microsoft Presidio docs: https://microsoft.github.io/presidio/
- OWASP Top 10 for LLM Applications: https://owasp.org/www-project-top-10-for-large-language-model-applications/
- Azure OpenAI Responsible AI: https://learn.microsoft.com/en-us/azure/ai-services/openai/concepts/content-filter

---

## 13. Stage 12 — Production Deployment and Architecture

### Goal
Deploy scalable GenAI systems with proper architecture.

### Topics to learn

#### 13.1 Backend architecture

Typical production architecture:

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

#### 13.2 Deployment

Learn:

- Docker
- Docker Compose
- Azure App Service
- Azure Container Apps
- Azure Functions for background tasks
- GitHub Actions CI/CD

#### 13.3 Scalability

Think about:

- async processing
- queue-based ingestion
- caching
- rate limits
- retries
- circuit breakers
- batch embeddings
- background indexing jobs

#### 13.4 Cost optimization

Track:

- input tokens
- output tokens
- embedding cost
- retrieval cost
- reranker cost
- evaluation cost

Optimize by:

- choosing smaller models for simple tasks
- using reasoning models only when needed
- caching common answers
- improving chunking to reduce unnecessary context
- using hybrid retrieval to reduce irrelevant chunks

#### 13.5 Model selection

Choose model based on:

- quality
- latency
- cost
- context window
- tool calling support
- structured output support
- multimodal support
- enterprise compliance needs

### Mini project 12 — Production GenAI Starter Kit

Build a reusable starter with:

- FastAPI backend
- Dockerfile
- environment config
- LLM provider abstraction
- vector DB abstraction
- logging
- tracing
- evaluation script
- deployment guide

### Resources

- Azure Container Apps: https://learn.microsoft.com/en-us/azure/container-apps/
- Azure App Service: https://learn.microsoft.com/en-us/azure/app-service/
- GitHub Actions: https://docs.github.com/en/actions
- Docker docs: https://docs.docker.com/
- Azure Search OpenAI demo: https://github.com/Azure-Samples/azure-search-openai-demo

---

## 14. Recommended 12-Week Learning Plan

### Week 1 — GenAI Basics

Learn:

- AI vs GenAI
- LLM basics
- tokens
- context window
- model parameters

Build:

- simple prompt experiments

Deliverable:

- notes explaining tokens, temperature, context, hallucination

---

### Week 2 — Python LLM API Development

Learn:

- OpenAI/Azure OpenAI API
- FastAPI integration
- environment variables

Build:

- basic chat API
- summarization API

Deliverable:

- GitHub repo: `llm-fastapi-basics`

---

### Week 3 — Prompt Engineering

Learn:

- role prompting
- few-shot prompting
- structured JSON output
- prompt testing

Build:

- prompt playground API/UI

Deliverable:

- reusable prompt templates

---

### Week 4 — Embeddings and Vector Search

Learn:

- embeddings
- cosine similarity
- vector DB basics

Build:

- semantic search API

Deliverable:

- GitHub repo: `semantic-search-python`

---

### Week 5 — Basic RAG

Learn:

- ingestion
- chunking
- retrieval
- answer generation

Build:

- PDF Q&A bot

Deliverable:

- GitHub repo: `pdf-rag-chatbot`

---

### Week 6 — Advanced RAG

Learn:

- hybrid search
- reranking
- metadata filters
- citations

Build:

- enterprise knowledge assistant v1

Deliverable:

- RAG app with source citations

---

### Week 7 — RAG Evaluation

Learn:

- RAGAS
- faithfulness
- answer relevance
- context precision
- context recall

Build:

- evaluation dataset
- automated evaluation script

Deliverable:

- RAG score report

---

### Week 8 — LangChain and LlamaIndex

Learn:

- LCEL
- retrievers
- query engines
- data connectors

Build:

- same RAG flow once in LangChain and once in LlamaIndex

Deliverable:

- comparison notes: LangChain vs LlamaIndex

---

### Week 9 — Agentic AI Basics

Learn:

- LLM vs agent
- tool calling
- memory
- human-in-loop

Build:

- tool-calling assistant

Deliverable:

- GitHub repo: `tool-calling-agent`

---

### Week 10 — Multi-Agent Workflows

Learn:

- LangGraph
- CrewAI
- supervisor-worker pattern
- agent state

Build:

- multi-agent research assistant

Deliverable:

- workflow diagram + code

---

### Week 11 — Observability and Security

Learn:

- tracing
- token/cost monitoring
- PII detection
- prompt injection mitigation

Build:

- add LangSmith traces and Presidio PII masking

Deliverable:

- secure + observable RAG/agent app

---

### Week 12 — Production Architecture

Learn:

- Docker
- deployment
- CI/CD
- cloud architecture
- cost optimization

Build:

- deploy final capstone app

Deliverable:

- architecture document + deployed demo

---

## 15. Capstone Project Options

### Capstone 1 — Enterprise Document Assistant

Features:

- upload documents
- background ingestion
- chunking and embeddings
- hybrid retrieval
- citations
- auth-ready design
- feedback capture
- RAGAS evaluation
- LangSmith tracing
- Docker deployment

Recommended stack:

- FastAPI
- React or simple frontend
- Azure OpenAI or OpenAI
- Azure AI Search / Qdrant / Chroma
- LangChain or LlamaIndex
- LangSmith
- Docker

---

### Capstone 2 — DMS Knowledge Assistant

This is suitable if your work involves document management systems.

Features:

- document metadata extraction
- document classification
- policy Q&A
- access-aware retrieval
- summarization
- ticket/action recommendation
- audit logs

Architecture:

```text
User
  ↓
Frontend
  ↓
FastAPI
  ↓
Auth + Permissions
  ↓
Document/RAG Service
  ↓
Vector DB + Metadata DB
  ↓
LLM Response with Citations
  ↓
Tracing + Evaluation + Logs
```

---

### Capstone 3 — Agentic Workflow Automation Assistant

Features:

- classify incoming request
- retrieve relevant knowledge
- decide next action
- call tools/APIs
- ask for approval
- create ticket or draft response
- trace all steps

Agent roles:

- Planner Agent
- Retrieval Agent
- Tool Agent
- Validation Agent
- Final Response Agent

---

## 16. Recommended GitHub Portfolio Structure

Create these repositories:

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

Each repo should include:

- README
- architecture diagram
- setup instructions
- `.env.example`
- sample data
- screenshots
- known limitations
- future improvements

---

## 17. Tools Checklist

### Programming

- Python
- FastAPI
- Pydantic
- AsyncIO
- pytest

### LLM providers

- Azure OpenAI
- OpenAI API
- Hugging Face models
- Ollama for local models

### Frameworks

- LangChain
- LlamaIndex
- LangGraph
- CrewAI
- Semantic Kernel / Microsoft Agent Framework

### Vector databases/search

- Chroma
- Qdrant
- FAISS
- Pinecone
- Weaviate
- Azure AI Search
- pgvector

### Evaluation and observability

- LangSmith
- RAGAS
- Azure AI Foundry traces
- Azure Monitor
- OpenTelemetry

### Security

- Microsoft Presidio
- OWASP LLM Top 10
- authentication/authorization
- secret management

### Deployment

- Docker
- Docker Compose
- Azure App Service
- Azure Container Apps
- GitHub Actions

---

## 18. Interview and Architect-Level Topics

Prepare to explain:

- What is RAG and when should it be used?
- RAG vs fine-tuning
- embeddings vs tokens
- vector search vs keyword search
- hybrid search
- chunking strategies
- reranking
- hallucination reduction
- prompt injection risk
- tool calling
- agents vs workflows
- human-in-the-loop patterns
- tracing and evaluation
- cost optimization
- model selection
- deployment architecture
- document-level security

---

## 19. Architecture Decision Guide

### When to use simple prompting

Use when:

- task does not need private data
- output is simple
- low risk
- no tool/action required

Examples:

- rewrite email
- summarize short text
- generate boilerplate code

### When to use RAG

Use when:

- answer depends on private or changing data
- citations are needed
- model should not rely only on training data

Examples:

- policy Q&A
- document assistant
- knowledge base chatbot

### When to use fine-tuning

Use when:

- you need style/format adaptation
- you have many high-quality examples
- behavior is repeated and narrow

Avoid fine-tuning only to add knowledge. Use RAG for knowledge.

### When to use agents

Use when:

- task requires multiple steps
- tools/APIs must be called
- decisions are needed during execution
- workflow may branch dynamically

### When to use deterministic workflows

Use when:

- process must be predictable
- compliance/audit requirements are strict
- steps are known in advance

Best production pattern:

```text
Deterministic workflow + LLM decision points + human approval for sensitive actions
```

---

## 20. Final Recommended Path for You

Because you are already a Python full-stack developer, do **not** spend too long only reading theory.

Follow this order:

1. LLM API basics with FastAPI
2. Prompt engineering and structured output
3. Embeddings and semantic search
4. Basic RAG
5. Advanced RAG with evaluation
6. Tool calling and agents
7. Observability and security
8. Production deployment
9. Architecture and cost optimization

Your biggest advantage is that you already understand application development. Use that strength and build GenAI systems end to end.

---

## 21. Master Resource List

### Official / Core

- Azure OpenAI: https://learn.microsoft.com/en-us/azure/ai-services/openai/
- Azure AI Foundry: https://ai.azure.com/
- OpenAI API docs: https://developers.openai.com/api/docs/
- OpenAI SDKs: https://developers.openai.com/api/docs/libraries
- Hugging Face: https://huggingface.co/

### Frameworks

- LangChain docs: https://python.langchain.com/docs/
- LangChain GitHub: https://github.com/langchain-ai/langchain
- LangGraph GitHub: https://github.com/langchain-ai/langgraph
- LangSmith docs: https://docs.langchain.com/langsmith/home
- LlamaIndex docs: https://developers.llamaindex.ai/python/framework/
- LlamaIndex GitHub: https://github.com/run-llama/llama_index
- Semantic Kernel docs: https://learn.microsoft.com/en-us/semantic-kernel/
- Semantic Kernel GitHub: https://github.com/microsoft/semantic-kernel

### Agents

- CrewAI docs: https://docs.crewai.com/
- CrewAI GitHub: https://github.com/crewAIInc/crewAI
- CrewAI quickstarts: https://github.com/crewAIInc/crewAI-quickstarts
- AutoGen docs: https://microsoft.github.io/autogen/stable/index.html
- AutoGen GitHub: https://github.com/microsoft/autogen
- Microsoft OpenAI Workshop: https://github.com/microsoft/OpenAIWorkshop

### RAG and Search

- Azure Search OpenAI demo: https://github.com/Azure-Samples/azure-search-openai-demo
- Microsoft RAG sample: https://learn.microsoft.com/en-us/samples/azure-samples/azure-search-openai-demo/azure-search-openai-demo/
- Azure AI Search vector search: https://learn.microsoft.com/en-us/azure/search/vector-search-overview
- Azure AI Search hybrid search: https://learn.microsoft.com/en-us/azure/search/hybrid-search-overview
- Pinecone RAG guide: https://www.pinecone.io/learn/retrieval-augmented-generation/

### Evaluation

- RAGAS docs: https://docs.ragas.io/en/latest/getstarted/rag_eval/
- RAGAS GitHub: https://github.com/vibrantlabsai/ragas
- LangSmith docs: https://docs.langchain.com/langsmith/home

### Security and Governance

- Microsoft Presidio docs: https://microsoft.github.io/presidio/
- Microsoft Presidio GitHub: https://github.com/microsoft/presidio
- OWASP LLM Top 10: https://owasp.org/www-project-top-10-for-large-language-model-applications/

### MCP and Standards

- MCP official docs: https://modelcontextprotocol.io/docs/getting-started/intro
- MCP GitHub: https://github.com/modelcontextprotocol/modelcontextprotocol
- OpenAI Agents SDK MCP docs: https://openai.github.io/openai-agents-python/mcp/

### Deployment

- Docker docs: https://docs.docker.com/
- Azure Container Apps: https://learn.microsoft.com/en-us/azure/container-apps/
- Azure App Service: https://learn.microsoft.com/en-us/azure/app-service/
- GitHub Actions: https://docs.github.com/en/actions

---

## 22. Completion Checklist

Mark each item as you complete it.

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

## 23. Final Notes

The roadmap from the senior developer is conceptually strong. The main improvement needed is execution: building real applications, adding production concerns, and creating a portfolio.

Your best path is:

```text
Build → Measure → Improve → Secure → Deploy → Document
```

If you follow this roadmap and complete the projects, you will move from beginner to advanced GenAI developer/architect with practical, interview-ready, and production-ready skills.
