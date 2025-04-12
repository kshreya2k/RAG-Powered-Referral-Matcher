# Specialist Search Agent (SSA) – Agentic RAG-Powered Referral Matcher

This repository presents a multi-version implementation of a **Specialist Search Agent (SSA)** for the WeKare360 One-Click Referral system. The system uses Retrieval-Augmented Generation (RAG) and modular AI agents to recommend the top 3 specialists based on patient symptoms, ranked by proximity, availability, and insurance compatibility. 

Developed and tested in **Google Colab** for rapid prototyping and demonstration.

---

## Author
**Shreya Banik**

---

## Objective

To design and implement an explainable referral matching system that:
- Parses free-text patient input to identify key symptoms and intent
- Matches the input to appropriate medical specialists
- Ranks specialists using structured metadata
- Outputs structured JSON responses with clear justifications
- Enables integration with downstream agents (e.g., insurance authorization)

---

## Models and Tools Used

| Component                  | Details                                                                 |
|---------------------------|-------------------------------------------------------------------------|
| **LLM (for reasoning)**   | `GPT2` (via `transformers`) for generating summaries and reflections     |
| **Sentence Embeddings**   | `all-MiniLM-L6-v2` from `sentence-transformers` for vector search        |
| **Vector Store**          | `FAISS` (V2) and `Chroma` via `LlamaIndex` (V3) for fast similarity search|
| **RAG Framework**         | `LlamaIndex` (formerly GPT Index) for index construction and querying    |
| **Agentic Design**        | Custom Python agents (Referral, Supervisor, Insurance)                   |
| **Notebook Platform**     | Google Colab                                                              |
| **Metadata Format**       | Structured CSV for specialists' data (name, specialty, insurance, etc.)  |

---

## Pipeline Versions

### `SSA_V1.ipynb` – Rule-Based Matching
- Keyword-based specialty detection
- Ranking using metadata: availability, insurance, and proximity
- No semantic or vector-based retrieval

### `SSA_V2.ipynb` – Hybrid RAG with FAISS
- Uses HuggingFace embeddings (`all-MiniLM-L6-v2`) and FAISS for semantic retrieval
- Combines vector search with rule-based filtering
- Includes confidence scoring and composite ranking logic

### `SSA_V3.ipynb` – Agentic RAG with Multi-Agent Pipeline
- Modular agent design:
  - `ReferralMatcher`
  - `SupervisorAgent`
  - `InsuranceAgent`
- Uses `LlamaIndex` + `Chroma` for semantic search over profile corpus
- Reflection loop to re-query if relevance score is below 0.6
- Structured JSON output with patient-friendly justifications

---

## Directory Structure

- `notebooks/` – 3 versions of the pipeline (V1–V3)
- `agents/` – Modular agent implementations
- `data/` – Mock specialist metadata
- `output/` – Sample structured output
