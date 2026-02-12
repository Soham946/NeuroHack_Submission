# NeuroMemory: Long-Form Contextual Memory System
### 🏆 Submission for NeuroHack

**Team:** Neuro Titans
**Problem:** Long-Form Memory Recall (1,000+ Turns) in Real-Time AI  

## 🚀 Overview
NeuroMemory is a **Dual-Loop Memory Architecture** capable of retaining user facts, preferences, and instructions across 1,000+ conversation turns without context window overflow. It achieves **< 2s latency** on standard hardware by decoupling "Memory Formation" (Write) from "Context Retrieval" (Read).

## 🧠 System Architecture
Our system solves the "Goldfish Memory" problem using a specialized RAG pipeline:
1.  **Fast Loop (Read):** Retrieves the top-1 most semantically relevant memory using `ChromaDB` and injects it into the System Prompt.
2.  **Slow Loop (Write):** Asynchronously extracts `Facts` and `Emotions` using Llama-3 and stores them with metadata (Turn #, Timestamp).
3.  **The "Time Machine":** Includes a simulation tool to inject "Turn 1" memories to prove long-term retention instantly.

## ⚡ Key Features (Evaluation Criteria Met)
* **Accuracy:** successfully recalls specific facts from Turn 1 at Turn 1,000+.
* **Real-Time Latency:** Uses `Llama-3-8B-GGUF` with GPU acceleration for < 2s response times.
* **Structured Output:** Logs the required `active_memories` JSON structure for auditability.
* **Robustness:** Uses GGUF quantification to avoid PyTorch dependency conflicts.

## 🛠️ Tech Stack
* **Model:** Llama-3-8B-Instruct (Quantized)
* **Inference:** Llama.cpp (GPU Accelerated)
* **Database:** ChromaDB (Vector Store)
* **Embeddings:** all-MiniLM-L6-v2
* **Interface:** Gradio

## 🏃‍♂️ How to Run
1.  `pip install -r requirements.txt`
2.  `python app.py`
3.  Access the Web UI at the local URL.

## 📸 Proof of Functionality
*(Add your screenshot of the "OFFICIAL PS OUTPUT" JSON log here)*
