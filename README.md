# RAG Teacher – Teaching Retrieval-Augmented Generation  
_An INFO 7390: Advanced Data Science and Architecture – Take-Home Final Project_  

**Author:** Manish Kumar Kondoju  
**Course:** INFO 7390 – Advanced Data Science and Architecture  
**Instructor:** Prof. Nik Bear Brown  

---

## 🌟 Project Overview

This project is a **mini-course on Retrieval-Augmented Generation (RAG)** designed for graduate students in data science and AI. It doesn’t just show code – it **teaches** the concept through:

- A **theory + practice tutorial webpage**  
- A **fully working RAG notebook implementation**  
- A **pedagogical report** explaining the teaching design  
- **Hands-on exercises, a quiz, and a debugging guide**  

The goal is to help learners go from:

> _“I’ve heard of RAG”_ → to → _“I can build, debug, and explain a RAG system.”_

---

## 🎯 Learning Objectives

By the end of this mini-course, learners should be able to:

1. **Explain** what Retrieval-Augmented Generation (RAG) is and why it is useful.  
2. **Describe** the core components of a RAG pipeline:
   - Document preprocessing and chunking  
   - Embedding generation  
   - Vector stores and similarity search  
   - Retrieval and prompt construction  
   - LLM-based generation  
3. **Implement** a minimal RAG system from scratch in Python using open-source tools.  
4. **Visualize** embeddings and interpret basic similarity structure.  
5. **Diagnose** common failure modes in RAG (bad retrieval, hallucinations, poor prompts).  
6. **Extend** the baseline implementation with different models, chunking strategies, or retrieval settings.

---

## 📁 Repository Structure

Adjust file names if your repo differs, but this is the intended structure:

```text
.
├── RAG_Scratch.ipynb          # Main teaching notebook: theory + implementation + visualizations + Gradio
├── rag_tutorial.html          # Web-based tutorial (PDF/Web deliverable) with theory, exercises, quiz, debugging guide
├── report_pedagogical.tex     # LaTeX source for pedagogical report (Teaching Philosophy, Concept Deep Dive, etc.)
├── arch.png                   # RAG architecture diagram used in the report and/or tutorial
├── data/
│   └── sample_corpus.txt      # Example corpus or synthetic documents (if used)
├── requirements.txt           # Python dependencies for running the notebook and RAG demo
└── README.md                  # You are here
```

If you have a different notebook name (e.g. `RAG_Sratch.ipynb`), just update this README accordingly.

---

## 🧠 Concept Summary: What is RAG?

**Retrieval-Augmented Generation (RAG)** combines:

- A **retriever** – finds relevant text chunks from an external knowledge base; and  
- A **generator** – usually a Large Language Model (LLM) that uses those chunks to answer questions.

The pipeline has two main phases:

1. **Indexing (offline)**
   - Collect documents  
   - Clean and chunk them  
   - Encode each chunk into an embedding vector  
   - Store embeddings in a vector store (FAISS / nearest neighbors)

2. **Querying (online)**
   - Encode the user’s question into an embedding  
   - Retrieve top-k similar chunks  
   - Build a prompt: **context + question + instructions**  
   - Ask the LLM to generate a grounded answer  

This project walks students through this entire pipeline step by step.

---

## ⚙️ Setup & Installation

### 1. Prerequisites

- Python **3.9+**
- `pip` (or `conda`, if you prefer)
- Jupyter Lab / Jupyter Notebook

Optional but recommended:

- A virtual environment (`venv` or `conda env`)

### 2. Clone the Repository

```bash
git clone <YOUR_REPO_URL>.git
cd <YOUR_REPO_NAME>
```

### 3. Create and Activate a Virtual Environment (recommended)

```bash
python -m venv .venv
source .venv/bin/activate    # macOS / Linux
# or
.\.venv\Scriptsctivate     # Windows
```

### 4. Install Dependencies

Make sure `requirements.txt` matches your notebook imports.

```bash
pip install -r requirements.txt
```

If you don’t have a `requirements.txt` yet, you can generate one from your current environment with:

```bash
pip freeze > requirements.txt
```

---

## 🧪 How to Run the Notebook

1. Activate your environment (if using one).
2. Start Jupyter:

```bash
jupyter notebook
# or
jupyter lab
```

3. Open **`RAG_Scratch.ipynb`** (or your notebook file).
4. From the menu, choose **Kernel → Restart & Run All** to execute all cells in order.

The notebook includes:

- **Concept recap** – abstract, introduction, and RAG theory  
- **Code cells** building:
  - `DocumentChunker`  
  - `EmbeddingGenerator`  
  - `VectorStore`  
- **End-to-end query demo** – question → retrieval → prompt → answer  
- **Embedding visualizations** (e.g., PCA plots)  
- A **Gradio-based interface** so learners can interact with the system like an app  

At the end of the notebook, you should see a Gradio link or inline UI. Use it to test questions and see the RAG pipeline in action.

---

## 🌐 Tutorial Webpage (rag_tutorial.html)

The **`rag_tutorial.html`** file is the student-facing **teaching document**.  

It includes:

- High-level explanations of:
  - Why RAG is needed  
  - RAG vs fine-tuning vs prompt engineering  
  - The indexing and query-time pipelines  
- A clean narrative that pairs with the notebook  
- **Hands-on exercises** labeled:
  - Beginner  
  - Intermediate  
  - Advanced  
- A **concept check quiz**  
- A **RAG debugging guide** mapping:
  - “Symptom → Likely cause → Suggested fix”

### How to View It

You can open it directly in a browser:

```bash
open rag_tutorial.html         # macOS
# or just double-click the file in a file explorer
```

You can also host it via GitHub Pages or any static hosting if you want students to access it via URL.

---


---

## 🎥 Show-and-Tell Video (Explain → Show → Try)

The project includes or assumes a **5–10 minute screen recording** that:

- **Explain**  
  - Introduces RAG and its motivation  
  - Compares it with fine-tuning and plain prompting  

- **Show**  
  - Walks through the Jupyter notebook  
  - Demonstrates the RAG pipeline end-to-end  
  - Shows embedding visualizations and the Gradio interface  

- **Try**  
  - Points learners to the exercises and quiz  
  - Explains how to run and modify the notebook themselves  

> **Video link placeholder:**  
> `📺 Video: [https://drive.google.com/file/d/1610Ki9TCE2IJvqelVIiJhYi2uLDA6eyy/view?usp=sharing]`

---

## 🧩 Assessment Materials

This project includes assessment-friendly components:

- **Hands-on exercises** (Beginner → Advanced)  
- **Concept check quiz** on the tutorial page  
- **Debugging guide** for common RAG problems  
- Well-commented notebook cells that can be turned into:
  - Lab assignments  
  - In-class demos  
  - Homework extensions  

Instructors can easily:

- Hide solution cells in the notebook, or  
- Provide a “starter” version and keep the full version as the answer key.

---

## 🤖 Use of AI Assistance

As required by INFO 7390 guidelines:

- AI tools (such as GPT-based assistants) were used to help with:
  - Drafting explanatory text and documentation structure  
  - Refining code comments and pedagogical wording  
  - Brainstorming exercises and quiz questions  

All technical implementation and final design decisions were reviewed, understood, and integrated by the author. The video, notebook execution, and reasoning about RAG are based on the author’s understanding, not an AI-generated black box.

---

## 📜 License

You can choose whichever license you prefer. A common choice for educational projects is **MIT**:

```text
MIT License

Copyright (c) 2025 Manish Kumar Kondoju

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

[...full MIT text here...]
```

---

## 🙋 Questions / Extensions

Ideas for extending this project:

- Plug in a **real-world corpus** (e.g., documentation, policies, or an academic domain).  
- Add a **reranking layer** or simple scoring function on top of the retrieved chunks.  
- Compare different embedding models and measure retrieval quality.  
- Turn the Gradio demo into a small **Streamlit app** or deploy it to a cloud platform.

If you’re reviewing this as part of INFO 7390, I recommend starting with:

1. `rag_tutorial.html` → for conceptual grounding  
2. `RAG_Scratch.ipynb` → for the implementation  
3. `report_pedagogical.pdf` → for the teaching analysis  

Happy learning and hacking with RAG! 🚀
