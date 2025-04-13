# 🩺 WeKare360 Specialist Search Agent (SSA) – RAG Pipeline

This project explores a **multi-agent, Retrieval-Augmented Generation (RAG)-powered AI system** designed to intelligently match patients with medical specialists based on symptoms, location, insurance, and availability.

Developed as part of a technical assignment for the **WeKare360 One-Click Referral System**, this system parses natural language patient queries and returns a ranked list of specialists with clear, explainable justifications.

---

## 🚀 Features

- **Natural Language Understanding** using zero-shot classification (`facebook/bart-large-mnli`)
- **Semantic Search** over specialist profiles using vector embeddings (HuggingFace models)
- **RAG Pipelines** with FAISS, LangChain, and LlamaIndex + Chroma
- **Specialist Ranking** based on:
  - Symptom-specialty alignment
  - Insurance compatibility
  - Geographic proximity
  - Next-3-day availability
- **Patient-Friendly Justifications** via Falcon-7B (`tiiuae/falcon-7b-instruct`)
- **Multi-Agent Architecture**:  
  Specialist Search Agent → Supervisor Agent → Insurance Agent
- **Reflection Loop**: Auto re-query on low-confidence results
- **API-ready Placeholder**: Simulated logic for real-time availability updates

---

## 📂 Project Structure

```bash
notebooks/
├── Multiagent_RAG_pipeline_final.ipynb  # End-to-end pipeline
data/
├── Mock_Specialist_Dataset.csv          # Metadata for doctors
doc/
├── Shreya Banik-Interview with Sri.pdf         # Task document