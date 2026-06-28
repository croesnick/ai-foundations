# 🧠 AI Foundations

A personal knowledge base mapping the foundations of modern AI — built one topic at a time, one paper at a time.

## 📚 Curriculum

Each topic has a dedicated note file. Notes contain the assigned reading, key concepts, focus questions, personal reflections, and cross-links to related topics.

### Core Topics

| # | Topic | Notes | Status |
|---|-------|-------|--------|
| 1 | [Transformer Architecture & Self-Attention](notes/01-transformer.md) | 📝 | ✅ Done |
| 2 | [Tokenization & Tokenizers](notes/02-tokenization.md) | 📝 | ✅ Done |
| 3 | [Pre-training → SFT → RLHF / DPO / GRPO](notes/03-pre-training.md) | 📝 | 📖 Reading |
| 4 | [Mixture of Experts (MoE)](notes/04-moe.md) | 📝 | ⬜ |
| 5 | [Quantization (GGUF, GPTQ, AWQ, EXL2)](notes/05-quantization.md) | 📝 | ⬜ |
| 6 | [Model Families & Ecosystem](notes/06-model-families.md) | 📝 | ⬜ |
| 7 | [LoRA / QLoRA / PEFT](notes/07-lora.md) | 📝 | ⬜ |
| 8 | [Inference Optimization](notes/08-inference.md) | 📝 | ⬜ |
| 9 | [Context Windows & Long-Context](notes/09-context-windows.md) | 📝 | ⬜ |
| 10 | [Embeddings & Vector Databases](notes/10-embeddings.md) | 📝 | ⬜ |
| 11 | [RAG (Retrieval-Augmented Generation)](notes/11-rag.md) | 📝 | ⬜ |
| 12 | [Diffusion Models](notes/12-diffusion.md) | 📝 | ⬜ |
| 13 | [Multimodal Models](notes/13-multimodal.md) | 📝 | ⬜ |
| 14 | [Distillation & Model Merging](notes/14-distillation-merging.md) | 📝 | ⬜ |
| 15 | [Alignment, Guardrails & Safety](notes/15-alignment.md) | 📝 | ⬜ |

### Extended Topics (Cycle 2+)

| Topic | Notes | Status |
|-------|-------|--------|
| [Agents & Tool Use](notes/ext-agents.md) | 📝 | ⬜ |
| [Reasoning Models (o1/o3, DeepSeek-R1)](notes/ext-reasoning.md) | 📝 | ⬜ |
| [Training Infrastructure (GPU, FSDP, DeepSpeed)](notes/ext-training-infra.md) | 📝 | ⬜ |
| [Evaluation & Benchmarks](notes/ext-evaluation.md) | 📝 | ⬜ |
| [Sparse Attention & Efficient Transformers](notes/ext-sparse-attention.md) | 📝 | ⬜ |

## 🔗 Cross-Referenced Concepts

Recurring concepts that appear across multiple topics, collected in [`_concepts/`](concepts/):

- [Attention](concepts/attention.md) — the mechanism at the heart of everything
- [Embeddings](concepts/embeddings.md) — how text becomes numbers
- [Tokens](concepts/tokens.md) — the atomic unit of LLMs
- [Backpropagation](concepts/backprop.md) — how models learn
- [Loss Functions](concepts/loss-functions.md) — measuring how wrong we are
- [Quantization](concepts/quantization.md) — making models smaller and faster

## 📖 How This Works

1. **Daily homework**: Each day, a reading (paper/blog/tutorial) is assigned.
2. **Notes**: After reading, add personal notes, insights, and questions to the topic file.
3. **Cross-links**: Link related concepts between topics — everything connects.

## 🗓️ Progress

- **Started**: 2026-06-24
- **Current Cycle**: 1
- **Topics Covered**: 2/15

---

*This wiki is maintained alongside the [AI Daily Homework](https://hermes-agent.nousresearch.com) curriculum.*
