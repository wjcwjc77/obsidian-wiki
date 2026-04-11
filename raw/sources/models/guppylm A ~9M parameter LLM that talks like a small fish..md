---
title: "arman-bd/guppylm: A ~9M parameter LLM that talks like a small fish."
source: https://github.com/arman-bd/guppylm
author:
published:
created: 2026-04-11
description: A ~9M parameter LLM that talks like a small fish. Contribute to arman-bd/guppylm development by creating an account on GitHub.
tags:
  - models
---
[![GuppyLM](https://github.com/arman-bd/guppylm/raw/main/assets/guppy.png)](https://github.com/arman-bd/guppylm/blob/main/assets/guppy.png)

## GuppyLM

*A ~9M parameter LLM that talks like a small fish.*

---

> **This project exists to show that training your own language model is not magic.** No PhD required. No massive GPU cluster. One Colab notebook, 5 minutes, and you have a working LLM that you built from scratch — data generation, tokenizer, model architecture, training loop, and inference. If you can run a notebook, you can train a language model.
> 
> It won't produce a billion-parameter model that writes essays. But it will show you exactly how every piece works — from raw text to trained weights to generated output — so the big models stop feeling like black boxes.

## What is GuppyLM?

GuppyLM is a tiny language model that pretends to be a fish named Guppy. It speaks in short, lowercase sentences about water, food, light, and tank life. It doesn't understand human abstractions like money, phones, or politics — and it's not trying to.

It's trained from scratch on 60K synthetic conversations across 60 topics, runs on a single GPU in ~5 minutes, and produces a model small enough to run in a browser.

---

## Architecture

|  |  |
| --- | --- |
| **Parameters** | 8.7M |
| **Layers** | 6 |
| **Hidden dim** | 384 |
| **Heads** | 6 |
| **FFN** | 768 (ReLU) |
| **Vocab** | 4,096 (BPE) |
| **Max sequence** | 128 tokens |
| **Norm** | LayerNorm |
| **Position** | Learned embeddings |
| **LM head** | Weight-tied with embeddings |

Vanilla transformer. No GQA, no RoPE, no SwiGLU, no early exit. As simple as it gets.

---

## Personality

Guppy:

- Speaks in short, lowercase sentences
- Experiences the world through water, temperature, light, vibrations, and food
- Doesn't understand human abstractions
- Is friendly, curious, and a little dumb
- Thinks about food a lot

**60 topics:** greetings, feelings, temperature, food, light, water, tank, noise, night, loneliness, bubbles, glass, reflection, breathing, swimming, colors, taste, plants, filter, algae, snails, scared, excited, bored, curious, happy, tired, outside, cats, rain, seasons, music, visitors, children, meaning of life, time, memory, dreams, size, future, past, name, weather, sleep, friends, jokes, fear, love, age, intelligence, health, singing, TV, and more.
