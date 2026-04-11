---
title: "VectifyAI/PageIndex: 📑 PageIndex: Document Index for Vectorless, Reasoning-based RAG"
source: https://github.com/VectifyAI/PageIndex
author:
published:
created: 2026-04-11
description: "📑 PageIndex: Document Index for Vectorless, Reasoning-based RAG - VectifyAI/PageIndex"
tags:
  - rag
---

## 📑 Introduction to PageIndex

Are you frustrated with vector database retrieval accuracy for long professional documents? Traditional vector-based RAG relies on semantic *similarity* rather than true *relevance*. But **similarity ≠ relevance** — what we truly need in retrieval is **relevance**, and that requires **reasoning**. When working with professional documents that demand domain expertise and multi-step reasoning, similarity search often falls short.

Inspired by AlphaGo, we propose **[PageIndex](https://vectify.ai/pageindex)** — a **vectorless**, **reasoning-based RAG** system that builds a **hierarchical tree index** from long documents and uses LLMs to **reason** *over that index* for **agentic, context-aware retrieval**. It simulates how *human experts* navigate and extract knowledge from complex documents through *tree search*, enabling LLMs to *think* and *reason* their way to the most relevant document sections. PageIndex performs retrieval in two steps:

1. Generate a “Table-of-Contents” **tree structure index** of documents
2. Perform reasoning-based retrieval through **tree search**

[![](https://camo.githubusercontent.com/e9c3f93a4039fa4743b0655dc7a08eddd0eeb24ed1bfddfb03b6a0bf3c87cbdc/68747470733a2f2f646f63732e70616765696e6465782e61692f696d616765732f636f6f6b626f6f6b2f766563746f726c6573732d7261672e706e67)](https://pageindex.ai/blog/pageindex-intro "The PageIndex Framework")

### 🎯 Core Features

Compared to traditional vector-based RAG, **PageIndex** features:

- **No Vector DB**: Uses document structure and LLM reasoning for retrieval, instead of vector similarity search.
- **No Chunking**: Documents are organized into natural sections, not artificial chunks.
- **Human-like Retrieval**: Simulates how human experts navigate and extract knowledge from complex documents.
- **Better Explainability and Traceability**: Retrieval is based on reasoning — traceable and interpretable, with page and section references. No more opaque, approximate vector search (“vibe retrieval”).

PageIndex powers a reasoning-based RAG system that achieved **state-of-the-art** [98.7% accuracy](https://github.com/VectifyAI/Mafin2.5-FinanceBench) on FinanceBench, demonstrating superior performance over vector-based RAG solutions in professional document analysis. See our [blog post](https://vectify.ai/blog/Mafin2.5) for details.
