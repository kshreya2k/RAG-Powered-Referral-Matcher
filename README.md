# Wekare360 Specialist Search Agent (SSA) – RAG Pipeline

This project implements an **Agentic RAG-Powered Referral Matcher** for WeKare360's One-Click Referral system. It takes a patient's symptoms and recommends the top 3 most relevant specialists with justifications based on proximity, availability, and insurance.

## Features
- Rule-based and semantic query interpretation (V1 to V3).
- Vector-based retrieval using FAISS and Chroma + LlamaIndex.
- Ranking by proximity, availability, insurance match.
- Reflection loop for low-confidence re-query.
- Multi-agent pipeline: Referral Matcher → Supervisor → Insurance Agent.
- Modular and scalable Python implementation.

## Structure

- `notebooks/` – 3 versions of the pipeline (V1–V3)
- `agents/` – Modular agent implementations
- `data/` – Mock specialist metadata
- `output/` – Sample structured output
