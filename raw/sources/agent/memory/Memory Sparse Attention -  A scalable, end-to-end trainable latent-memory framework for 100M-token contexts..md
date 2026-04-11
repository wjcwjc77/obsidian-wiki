---
title: "EverMind-AI/MSA: Memory Sparse Attention -  A scalable, end-to-end trainable latent-memory framework for 100M-token contexts."
source: https://github.com/EverMind-AI/MSA
author:
published:
created: 2026-04-11
description: Memory Sparse Attention -  A scalable, end-to-end trainable latent-memory framework for 100M-token contexts. - EverMind-AI/MSA
tags:
  - memory
  - attention
---
## MSA: Memory Sparse Attention

*A scalable, end-to-end trainable latent-memory framework for 100M-token contexts*

[**arXiv**](https://arxiv.org/abs/2603.23516) • [**Zenodo**](https://zenodo.org/records/19103670)

[中文](https://github.com/EverMind-AI/MSA/blob/main/README_ZH.md)

## 📝 Abstract

Long-term memory is essential for general intelligence, yet the **full attention** bottleneck constrains most LLMs' **effective context length** to **128K–1M**. Existing attempts，hybrid linear attention, fixed-size state memory (e.g., RNNs), and external storage like **RAG/agents** ，either suffer rapid precision decay and latency growth at extreme scales, lack end-to-end differentiability or dynamic memory maintenance, or require complex pipelines. We present **Memory Sparse Attention (MSA)**: an **end-to-end trainable, scalable sparse** **latent-state memory** framework. Core ideas include:

- **Scalable sparse attention** + **document-wise RoPE** (parallel/global) achieving **near-linear complexity** in both training and inference;
- **KV cache compression** with a **Memory Parallel** inference engine to deliver **100M token** throughput on **2×A800** GPUs;
- **Memory Interleave** for multi-round, multi-hop reasoning across scattered memory segments.

On long-context QA and NIAH (Needle-in-a-Haystack) benchmarks, **MSA** surpasses same-backbone RAG, best-of-breed RAG stacks, and leading long-context models. Across an unprecedented **16K→100M token** range, MSA shows **< 9%** degradation, suggesting a practical path to **decouple memory capacity from reasoning**.

> **Scaling from 16K→100M tokens**: MSA fuses top-k selection with sparse attention to remain end-to-end differentiable while allowing document decoupling at inference. On MS MARCO, MSA sustains **<9%** degradation and exhibits strong extrapolation. *Some baseline curves end early due to their context limits.*

[![Figure 1: Scaling curve 16K→100M tokens](https://github.com/EverMind-AI/MSA/raw/main/assets/fig1_scaling.png)](https://github.com/EverMind-AI/MSA/blob/main/assets/fig1_scaling.png)

*Figure 1: MSA scalability under extreme-long contexts*

---

## ✨ Key Contributions

- **Memory-Sparse Attention (MSA)**: an **end-to-end trainable**, **scalable sparse attention** layer with **document-wise RoPE**, realizing **O(L)** complexity and **<9%** degradation from **16K→100M tokens**.
- **KV cache compression + Memory Parallel**: tiered storage (GPU-resident routing keys, CPU content K/V), distributed scoring, and on-demand transfers to enable **100M-token** inference on **2×A800**.
- **Memory Interleave**: adaptive alternating "generative retrieval → context expansion → generation," significantly boosting **multi-hop** reasoning across documents.
- **Comprehensive evaluation**: MSA outperforms same-backbone RAG, best-of-breed RAG pipelines, and top long-context models on long-context QA and NIAH, showing superior **stability** and **accuracy** at scale.

---

## 🧩 Overall Design

### Architecture

MSA integrates **retrieval and generation** into a single differentiable loop. Document latent states (**K/V/Kᵣ**) are **chunk-mean pooled** for compression. A **router projector** computes relevance via cosine similarity (mean-pooled over heads, then token-wise max), selects **Top‑k documents**, then concatenates their **compressed K/V** with the query's local **K/V** for autoregressive decoding. Routing applies only to **upper layers**; lower layers keep **independent document processing** for hierarchical alignment.

- **Parallel (document-wise) RoPE**: Each document resets positions from 0, preventing position drift between **train-short** and **infer-long**, enabling 64k training to extrapolate to 100M.
- **Global RoPE (active context)**: The query's starting index is **offset by k** (Top‑k retrieved blocks), preserving causal ordering: *background → query → generation*.

**Figure 2: MSA layer (sparse attention + document-wise RoPE)**

[![Figure 2: MSA layer](https://github.com/EverMind-AI/MSA/raw/main/assets/fig2_msa_layer.png)](https://github.com/EverMind-AI/MSA/blob/main/assets/fig2_msa_layer.png)

*Figure 2: Memory-Sparse Attention layer and parallel/global RoPE*

---

### Inference Pipeline

MSA uses a **three-stage** pipeline (Fig. 3):

1. **Global Memory Encoding (offline)**: forward over the corpus to cache chunk-pooled **(K̄, V̄, K̄ᵣ)**.
2. **Online Routing & Context Assembly**: project query to **Qᵣ**, match with **K̄ᵣ** to pick **Top‑k**, then load only the selected **K̄/V̄** and concatenate with local context.
3. **Sparse Generation**: autoregress over the **sparse context**.

**Memory Parallel** shards **K̄ᵣ** across GPUs (query broadcast → local scoring → global reduce). Content **K̄/V̄** stays in host DRAM and is **asynchronously fetched** when selected—balancing **VRAM** and **throughput** for **100M-token** deployment.

**Figure 3: Three-stage inference & Memory Interleave**

[![Figure 3: Inference](https://github.com/EverMind-AI/MSA/raw/main/assets/fig3_inference.png)](https://github.com/EverMind-AI/MSA/blob/main/assets/fig3_inference.png)

