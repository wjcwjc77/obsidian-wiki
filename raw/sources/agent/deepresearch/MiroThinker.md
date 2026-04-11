---
title: "MiroMindAI/MiroThinker: MiroThinker is a deep research agent optimized for complex research and prediction tasks. Our latest models, MiroThinker-1.7 and MiroThinker-H1, achieve 74.0 and 88.2 on the BrowseComp, respectively."
source: "https://github.com/MiroMindAI/MiroThinker"
author:
published:
created: 2026-04-11
description: "MiroThinker is a deep research agent optimized for complex research and prediction tasks. Our latest models, MiroThinker-1.7 and MiroThinker-H1, achieve 74.0 and 88.2 on the BrowseComp, respectively. - MiroMindAI/MiroThinker"
tags:
  - "deep-research"
---
[![MiroThinker](https://github.com/MiroMindAI/MiroThinker/raw/main/assets/mirothinker_logo.png)](https://github.com/MiroMindAI/MiroThinker/blob/main/assets/mirothinker_logo.png)

  

### 🚀 Try MiroThinker!

**MiroThinker**: A deep research agent optimized for research and prediction. It achieves a 88.2 on the challenging BrowseComp benchmark. See [Quick Start](#-quick-start).

## 📋 Table of Contents

- 📰 [News & Updates](#-news--updates)
- 📝 [Introduction](#-introduction)
- ✨ [Key Features](#-key-features)
- 📈 [Performance on Benchmarks](#-performance-on-benchmarks)
- 🚀 [Quick Start](#-quick-start)
- 📊 [Benchmark Evaluation](#-benchmark-evaluation)
- 🔬 [Trace Collection](#-trace-collection)
- ❓ [FAQ & Troubleshooting](#-faq--troubleshooting)
- 📄 [License](#-license)
- 🙏 [Acknowledgments](#-acknowledgments)

## 📰 News & Updates

- **\[2026-03-11\]** 🎉🎉🎉 Introducing [MiroThinker-1.7](https://huggingface.co/collections/miromind-ai/mirothinker-17), including [MiroThinker-1.7-mini](https://huggingface.co/miromind-ai/MiroThinker-1.7-mini) and [MiroThinker-1.7](https://huggingface.co/miromind-ai/MiroThinker-1.7). MiroThinker-1.7-mini achieves 72.3 on BrowseComp-ZH, setting a new SOTA among open-source models while using only 30B parameters. Our proprietary agent MiroThinker-H1 achieves leading performance on BrowseComp and BrowseComp-ZH among open-source and commercial models.
- **\[2026-01-23\]** 🎉 We have brought two important updates to [MiroThinker online](http://dr.miromind.ai/): (a) Core Research Report Generation: Deep Research online reports now support generation, preview, and sharing. (b) Extended Document Upload Types: Now supports the upload of various file formats, such as `.pdf`, `.doc`, `.ppt`, `.xls`, `.jpg`. Welcome to try it out! MiroThinker will continue to be maintained and iteratively upgraded, with the goal of becoming the best Research Agent you'll ever use!
- **\[2026-01-05\]** 🎉🎉 We release [MiroThinker-v1.5](https://huggingface.co/collections/miromind-ai/mirothinker-v15), a series of open-source deep research agents optimized for financial prediction. [MiroThinker-v1.5-30B](https://huggingface.co/miromind-ai/MiroThinker-v1.5-30B) surpasses Kimi-K2-Thinking on BrowseComp-ZH at much lower cost, using only 1/30 of the parameters. [MiroThinker-v1.5-235B](https://huggingface.co/miromind-ai/MiroThinker-v1.5-235B) scores 39.2% on HLE-Text, 69.8% on BrowseComp, 71.5% on BrowseComp-ZH, and 80.8% on GAIA-Val-165, setting a new state-of-the-art among search agents.
📜 Click to expand older updates
- **\[2025-11-13\]** 🎉 [MiroThinker-v1.0](https://huggingface.co/collections/miromind-ai/mirothinker-v10) is now released! Introducing **interactive scaling** as a third dimension of performance improvement, MiroThinker v1.0 supports 256K context window and up to 600 tool calls per task. Available in 8B, 30B, and 72B parameter scales, achieving 37.7%, 47.1%, 55.6%, and 81.9% on HLE-Text, BrowseComp, BrowseComp-ZH, and GAIA-Text-103, respectively. See [Technical Report](https://arxiv.org/abs/2511.11793) for more details.
- **\[2025-09-11\]** MiroThinker-72B-Preview ranked 4th in this week's FutureX benchmark. See [FutureX](https://futurex-ai.github.io/).
- **\[2025-09-08\]** [MiroThinker-v0.2](https://huggingface.co/collections/miromind-ai/mirothinker-v02) is now released, achieving open-source SOTA performance across multiple benchmarks, including HLE (17.8%), HLE-Text-Only (19.1%), BrowseComp-EN (17.2%), BrowseComp-ZH (29.4%), XBench-DeepSearch (56.0%), and Frames (74.8%).
- **\[2025-09-07\]** We supported more benchmarks, including [BrowseComp-ZH](https://arxiv.org/abs/2504.19314), [XBench-DeepSearch](https://xbench.org/agi/aisearch), and [FutureX](https://futurex-ai.github.io/). We plan to add more benchmarks in the future.
- **\[2025-08-22\]** Introducing streamlined deployment options for MiroThinker with optimized resource usage and faster startup times. Experience the interactive demo: [🚀 Try Gradio Demo](https://github.com/MiroMindAI/MiroThinker/blob/main/apps/gradio-demo)
- **\[2025-08-08\]** [MiroThinker-v0.1](https://huggingface.co/collections/miromind-ai/mirothinker-v01-689301b6d0563321862d44a1) released.