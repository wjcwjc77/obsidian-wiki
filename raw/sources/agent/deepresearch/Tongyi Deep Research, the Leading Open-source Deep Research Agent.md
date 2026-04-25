---
title: "Alibaba-NLP/DeepResearch: Tongyi Deep Research, the Leading Open-source Deep Research Agent"
source: "https://github.com/Alibaba-NLP/DeepResearch"
author:
published:
created: 2026-04-24
description: "Tongyi Deep Research, the Leading Open-source Deep Research Agent - Alibaba-NLP/DeepResearch"
tags:
  - "deepresearch"
---
![](https://github.com/Alibaba-NLP/DeepResearch/raw/main/assets/logo.png)

---

🤗 [HuggingFace](https://huggingface.co/Alibaba-NLP/Tongyi-DeepResearch-30B-A3B) ｜ [ModelScope](https://modelscope.cn/models/iic/Tongyi-DeepResearch-30B-A3B) | 💬 [WeChat(微信)](https://github.com/Alibaba-NLP/DeepResearch/blob/main/assets/wechat_new.jpg) | 📰 [Blog](https://tongyi-agent.github.io/blog/introducing-tongyi-deep-research/) | 📑 [Paper](https://arxiv.org/pdf/2510.24701)

[![Alibaba-NLP%2FDeepResearch | Trendshift](https://camo.githubusercontent.com/bce452910ecfced7cf3bd9bdfeae21d9cccf6ba10f7ebd0582b0a0a0d7bdb926/68747470733a2f2f7472656e6473686966742e696f2f6170692f62616467652f7265706f7369746f726965732f3134383935)](https://trendshift.io/repositories/14895)

👏 Welcome to try Tongyi DeepResearch via our **[Modelscope online demo](https://www.modelscope.cn/studios/jialongwu/Tongyi-DeepResearch)** or **[🤗 Huggingface online demo](https://huggingface.co/spaces/Alibaba-NLP/Tongyi-DeepResearch)** or **[bailian service](https://bailian.console.aliyun.com/?spm=a2ty02.31808181.d_app-market.1.6c4974a1tFmoFc&tab=app#/app/app-market/deep-search/)**!

> [!note] Note
> This demo is for quick exploration only. Response times may vary or fail intermittently due to model latency and tool QPS limits. For a stable experience we recommend local deployment; for a production-ready service, visit [bailian](https://bailian.console.aliyun.com/?spm=a2ty02.31808181.d_app-market.1.6c4974a1tFmoFc&tab=app#/app/app-market/deep-search/) and follow the guided setup.

## Introduction

We present **Tongyi DeepResearch**, an agentic large language model featuring 30.5 billion total parameters, with only 3.3 billion activated per token. Developed by Tongyi Lab, the model is specifically designed for **long-horizon, deep information-seeking** tasks. Tongyi DeepResearch demonstrates state-of-the-art performance across a range of agentic search benchmarks, including Humanity's Last Exam, BrowseComp, BrowseComp-ZH, WebWalkerQA,xbench-DeepSearch, FRAMES and SimpleQA.

> Tongyi DeepResearch builds upon our previous work on the [WebAgent](https://github.com/Alibaba-NLP/DeepResearch/blob/main/WebAgent) project.

More details can be found in our 📰 [Tech Blog](https://tongyi-agent.github.io/blog/introducing-tongyi-deep-research/).

[![](https://github.com/Alibaba-NLP/DeepResearch/raw/main/assets/performance.png)](https://github.com/Alibaba-NLP/DeepResearch/blob/main/assets/performance.png)

## Features

- ⚙️ **Fully automated synthetic data generation pipeline**: We design a highly scalable data synthesis pipeline, which is fully automatic and empowers agentic pre-training, supervised fine-tuning, and reinforcement learning.
- 🔄 **Large-scale continual pre-training on agentic data**: Leveraging diverse, high-quality agentic interaction data to extend model capabilities, maintain freshness, and strengthen reasoning performance.
- 🔁 **End-to-end reinforcement learning**: We employ a strictly on-policy RL approach based on a customized Group Relative Policy Optimization framework, with token-level policy gradients, leave-one-out advantage estimation, and selective filtering of negative samples to stabilize training in a non‑stationary environment.
- 🤖 **Agent Inference Paradigm Compatibility**: At inference, Tongyi DeepResearch is compatible with two inference paradigms: ReAct, for rigorously evaluating the model's core intrinsic abilities, and an IterResearch-based 'Heavy' mode, which uses a test-time scaling strategy to unlock the model's maximum performance ceiling.

## Model Download

You can directly download the model by following the links below.

| Model | Download Links | Model Size | Context Length |
| --- | --- | --- | --- |
| Tongyi-DeepResearch-30B-A3B | [🤗 HuggingFace](https://huggingface.co/Alibaba-NLP/Tongyi-DeepResearch-30B-A3B)   [🤖 ModelScope](https://modelscope.cn/models/iic/Tongyi-DeepResearch-30B-A3B) | 30B-A3B | 128K |

## News

\[2025/09/20\]🚀 Tongyi-DeepResearch-30B-A3B is now on [OpenRouter](https://openrouter.ai/alibaba/tongyi-deepresearch-30b-a3b)! Follow the [Quick-start](https://github.com/Alibaba-NLP/DeepResearch?tab=readme-ov-file#6-you-can-use-openrouters-api-to-call-our-model) guide.

\[2025/09/17\]🔥 We have released **Tongyi-DeepResearch-30B-A3B**.

## Deep Research Benchmark Results

[![](https://github.com/Alibaba-NLP/DeepResearch/raw/main/assets/benchmark.png)](https://github.com/Alibaba-NLP/DeepResearch/blob/main/assets/benchmark.png)

## Quick Start

This guide provides instructions for setting up the environment and running inference scripts located in the [inference](https://github.com/Alibaba-NLP/DeepResearch/blob/main/inference) folder.

### 1\. Environment Setup

- Recommended Python version: **3.10.0** (using other versions may cause dependency issues).
- It is strongly advised to create an isolated environment using `conda` or `virtualenv`.
```
# Example with Conda
conda create -n react_infer_env python=3.10.0
conda activate react_infer_env
```

### 2\. Installation

Install the required dependencies:

```
pip install -r requirements.txt
```

### 3\. Environment Configuration and Prepare Evaluation Data

#### Environment Configuration

Configure your API keys and settings by copying the example environment file:

```
# Copy the example environment file
cp .env.example .env
```

Edit the `.env` file and provide your actual API keys and configuration values:

- **SERPER\_KEY\_ID**: Get your key from [Serper.dev](https://serper.dev/) for web search and Google Scholar
- **JINA\_API\_KEYS**: Get your key from [Jina.ai](https://jina.ai/) for web page reading
- **API\_KEY/API\_BASE**: OpenAI-compatible API for page summarization from [OpenAI](https://platform.openai.com/)
- **DASHSCOPE\_API\_KEY**: Get your key from [Dashscope](https://dashscope.aliyun.com/) for file parsing
- **SANDBOX\_FUSION\_ENDPOINT**: Python interpreter sandbox endpoints (see [SandboxFusion](https://github.com/bytedance/SandboxFusion))
- **MODEL\_PATH**: Path to your model weights
- **DATASET**: Name of your evaluation dataset
- **OUTPUT\_PATH**: Directory for saving results

> **Note**: The `.env` file is gitignored, so your secrets will not be committed to the repository.

#### Prepare Evaluation Data

The system supports two input file formats: **JSON** and **JSONL**.

#### Supported File Formats:

**Option 1: JSONL Format (recommended)**

- Create your data file with `.jsonl` extension (e.g., `my_questions.jsonl`)
- Each line must be a valid JSON object with `question` and `answer` keys:
	```
	{"question": "What is the capital of France?", "answer": "Paris"}
	{"question": "Explain quantum computing", "answer": ""}
	```

**Option 2: JSON Format**

- Create your data file with `.json` extension (e.g., `my_questions.json`)
- File must contain a JSON array of objects, each with `question` and `answer` keys:
	```
	[
	  { "question": "What is the capital of France?", "answer": "Paris" },
	  { "question": "Explain quantum computing", "answer": "" }
	]
	```

**Important Note:** The `answer` field contains the **ground truth/reference answer** used for evaluation. The system generates its own responses to the questions, and these reference answers are used to automatically judge the quality of the generated responses during benchmark evaluation.

#### File References for Document Processing:

- If using the *file parser* tool, **prepend the filename to the `question` field**
- Place referenced files in `eval_data/file_corpus/` directory
- Example: `{"question": "(Uploaded 1 file: ['report.pdf'])\n\nWhat are the key findings?", "answer": "..."}`

#### File Organization:

```
project_root/
├── eval_data/
│   ├── my_questions.jsonl          # Your evaluation data
│   └── file_corpus/                # Referenced documents
│       ├── report.pdf
│       └── data.xlsx
```

### 4\. Configure the Inference Script

- Open `run_react_infer.sh` and modify the following variables as instructed in the comments:
	- `MODEL_PATH` - path to the local or remote model weights.
		- `DATASET` - full path to your evaluation file, e.g. `eval_data/my_questions.jsonl` or `/path/to/my_questions.json`.
		- `OUTPUT_PATH` - path for saving the prediction results, e.g. `./outputs`.
- Depending on the tools you enable (retrieval, calculator, web search, etc.), provide the required `API_KEY`, `BASE_URL`, or other credentials. Each key is explained inline in the bash script.

### 5\. Run the Inference Script

```
bash run_react_infer.sh
```

---

With these steps, you can fully prepare the environment, configure the dataset, and run the model. For more details, consult the inline comments in each script or open an issue.

### 6\. You can use OpenRouter's API to call our model

Tongyi-DeepResearch-30B-A3B is now available at [OpenRouter](https://openrouter.ai/alibaba/tongyi-deepresearch-30b-a3b). You can run the inference without any GPUs.

You need to modify the following in the file [inference/react\_agent.py](https://github.com/Alibaba-NLP/DeepResearch/blob/main/inference/react_agent.py):

- In the call\_server function: Set the API key and URL to your OpenRouter account’s API and URL.
- Change the model name to alibaba/tongyi-deepresearch-30b-a3b.
- Adjust the content concatenation way as described in the comments on lines **88–90.**

## Benchmark Evaluation

We provide benchmark evaluation scripts for various datasets. Please refer to the [evaluation scripts](https://github.com/Alibaba-NLP/DeepResearch/blob/main/evaluation) directory for more details.

## FAQ

Please refer to the [FAQ](https://github.com/Alibaba-NLP/DeepResearch/blob/main/FAQ.md) for more details.

## Deep Research Agent Family

[![](https://github.com/Alibaba-NLP/DeepResearch/raw/main/assets/family17.png)](https://github.com/Alibaba-NLP/DeepResearch/blob/main/assets/family17.png)

Tongyi DeepResearch also has an extensive deep research agent family. You can find more information in the following paper:

\[1\] [WebWalker: Benchmarking LLMs in Web Traversal](https://arxiv.org/pdf/2501.07572) (ACL 2025)  
\[2\] [WebDancer: Towards Autonomous Information Seeking Agency](https://arxiv.org/pdf/2505.22648) (NeurIPS 2025)  
\[3\] [WebSailor: Navigating Super-human Reasoning for Web Agent](https://arxiv.org/pdf/2507.02592)  
\[4\] [WebShaper: Agentically Data Synthesizing via Information-Seeking Formalization](https://arxiv.org/pdf/2507.15061)  
\[5\] [WebWatcher: Breaking New Frontier of Vision-Language Deep Research Agent](https://arxiv.org/pdf/2508.05748)  
\[6\] [WebResearcher: Unleashing unbounded reasoning capability in Long-Horizon Agents](https://arxiv.org/pdf/2509.13309)  
\[7\] [ReSum: Unlocking Long-Horizon Search Intelligence via Context Summarization](https://arxiv.org/pdf/2509.13313)  
\[8\] [WebWeaver: Structuring Web-Scale Evidence with Dynamic Outlines for Open-Ended Deep Research](https://arxiv.org/pdf/2509.13312)  
\[9\] [WebSailor-V2: Bridging the Chasm to Proprietary Agents via Synthetic Data and Scalable Reinforcement Learning](https://arxiv.org/pdf/2509.13305)  
\[10\] [Scaling Agents via Continual Pre-training](https://arxiv.org/pdf/2509.13310)  
\[11\] [Towards General Agentic Intelligence via Environment Scaling](https://arxiv.org/pdf/2509.13311)  
\[12\] [AgentFold: Long-Horizon Web Agents with Proactive Context Management](https://arxiv.org/pdf/2510.24699)  
\[13\] [WebLeaper: Empowering Efficient, Info-Rich Seeking for Web Agents](https://arxiv.org/pdf/2510.24697)  
\[14\] [BrowseConf: Confidence-Guided Test-Time Scaling for Web Agents](https://arxiv.org/pdf/2510.23458)  
\[15\] [Repurposing Synthetic Data for Fine-grained Search Agent Supervision](https://arxiv.org/pdf/2510.24694)  
\[16\] [ParallelMuse: Agentic Parallel Thinking for Deep Information Seeking](https://arxiv.org/pdf/2510.24698)  
\[17\] [AgentFrontier: Expanding the Capability Frontier of LLM Agents with ZPD-Guided Data Synthesis](https://arxiv.org/pdf/2510.24695)  
\[18\] [Nested Browser-Use Learning for Agentic Information Seeking](https://arxiv.org/pdf/2512.23647)

## 🌟 Misc

[![Star History Chart](https://camo.githubusercontent.com/2fe32f3292b9c287da39793cc5565930f1afe1b6a592f10c61139f93299b584d/68747470733a2f2f6170692e737461722d686973746f72792e636f6d2f7376673f7265706f733d416c69626162612d4e4c502f44656570526573656172636826747970653d44617465)](https://www.star-history.com/#Alibaba-NLP/DeepResearch&Date)

## 🚩 Talent Recruitment

🔥🔥🔥 We are hiring! Research intern positions are open (based in Hangzhou、Beijing、Shanghai)

📚 **Research Area** ：Web Agent, Search Agent, Agent RL, MultiAgent RL, Agentic RAG

☎️ **Contact** ： [yongjiang.jy@alibaba-inc.com](https://github.com/Alibaba-NLP/DeepResearch/blob/main)

## Contact Information

For communications, please contact Yong Jiang ([yongjiang.jy@alibaba-inc.com](mailto:yongjiang.jy@alibaba-inc.com)).

## Citation

```
@article{tongyidr,
  title={Tongyi DeepResearch Technical Report},
  ={Team, Tongyi DeepResearch and Li, Baixuan and Zhang, Bo and Zhang, Dingchu and Huang, Fei and Li, Guangyu and Chen, Guoxin and Yin, Huifeng and Wu, Jialong and Zhou, Jingren and others},
  journal={arXiv preprint arXiv:2510.24701},
  year={2025}
}
```