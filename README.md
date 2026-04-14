# RAGCHECKER: A Fine-grained Framework for Diagnosing Retrieval-Augmented Generation

> DS8008 Final Project — NLP / Text Mining

---

## 📌 Overview

This project implements and evaluates Retrieval-Augmented Generation (RAG) systems using the **RAGChecker** framework. The goal is to analyze how different retrieval and generation strategies affect the accuracy, reliability, and quality of generated responses.

RAG systems combine:
- a **retriever** (to fetch relevant documents)
- a **generator** (to produce answers)

Evaluating such systems is challenging because errors may originate from either component. To address this, this project uses **claim-level evaluation**, enabling fine-grained diagnosis of system behavior.

---

## ⚙️ Methodology

We implement a full RAG pipeline consisting of dataset preparation, retrieval, generation, and evaluation.

### 🔹 Retrieval Methods
- **FAISS** — semantic similarity using embeddings  
- **BM25** — keyword-based lexical matching  

### 🔹 Generation Methods
- **Extractive baseline** — selects answers directly from retrieved documents  
- **GPT-based generation** — synthesizes answers using retrieved context  

### 🔹 RAG Systems Evaluated
- FAISS + Extractive  
- BM25 + Extractive  
- FAISS + GPT  
- BM25 + GPT  

---

## 🖼️ Methodology Pipeline

<p align="center">
  <img src="images/pipeline.png" width="700"/>
</p>

---

## 📊 Evaluation Framework

We use **RAGChecker**, which evaluates responses at the **claim level** instead of treating answers as a whole.

### 🔹 Metrics Used

**Overall Metrics**
- Precision  
- Recall  

**Retriever Metrics**
- Claim Recall  
- Context Precision  

**Generator Metrics**
- Faithfulness  
- Hallucination  

---

## 🖼️ Evaluation Metrics

<p align="center">
  <img src="images/metrics.png" width="600"/>
</p>

---

## 📈 Results & Analysis

Our experiments highlight key differences between retrieval and generation strategies:

- **GPT-based generation improves precision** by producing more complete answers  
- **FAISS improves recall** through semantic retrieval  
- **BM25 reduces hallucination** due to precise keyword matching  

### 🔁 Trade-off
- FAISS → better coverage (higher recall)  
- BM25 → better reliability (lower hallucination)  

---

## 🖼️ System Comparison

<p align="center">
  <img src="images/analysis.png" width="700"/>
</p>

---

## 📁 Project Structure
ragchecker-project/
│
├── README.md
├── ragchecker.ipynb
│
├── data/
│ └── sample_data.json
│
├── src/
│ ├── retrieval.py
│ ├── generation.py
│ └── evaluation.py
│
├── images/
│ ├── pipeline.png
│ ├── metrics.png
│ └── analysis.png


---

## 📚 Datasets

This project uses the following datasets:

- **NovelQA**
- **CLAPNQ**
- **LoTTE (Science Corpus)**

Due to size limitations, only a small subset is included in the `data/` folder.

### 🔗 Full Dataset Access
- https://huggingface.co/datasets  
- https://ir-datasets.com/  

---

## 🚀 How to Run

1. Open the notebook:
ragchecker.ipynb

2. Install required dependencies:
pip install datasets sentence-transformers faiss-cpu


3. Run all cells sequentially

---

## 🧠 Key Insights

- RAG performance depends on both retrieval and generation  
- Semantic retrieval improves coverage but may introduce noise  
- Fine-grained evaluation provides deeper insights than traditional metrics  

---

## 👥 Authors

- Amadike Chidera Lilian
- Ogakwu Jeff
- David Philemon 

---

## 📌 Notes

- Only a subset of data is included due to size constraints  
- Full datasets should be downloaded separately  
- Ensure all dependencies are installed before running  
