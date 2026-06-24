# Transformer Architecture & Self-Attention

## 📖 Assigned Reading

- **Paper/Article:** The Illustrated Transformer
- **Link:** https://jalammar.github.io/illustrated-transformer/
- **Type:** Blogpost (visuelles Tutorial)
- **Author/Source:** Jay Alammar
- **Published:** June 27, 2018
- **Read time:** ~25 min

## 🔑 Key Concepts

- Self-Attention: Q/K/V-Tensoren und warum das Modell "auf alles gleichzeitig schauen" kann
- Multi-Head Attention: warum mehrere Attention-Heads parallel laufen statt einer einzigen
- Positional Encoding: wie Reihenfolge-Information in eine Architektur injiziert wird, die per se positions-agnostisch ist
- Encoder-Decoder-Struktur (originale Seq2Seq-Form) vs. decoder-only (GPT-Stil)
- Residual Connections & Layer Norm als Stabilisatoren

## 🤔 Focus Questions

- Warum braucht der Transformer überhaupt Positional Encoding, und warum reicht ein einfacher Index nicht aus?
- Was genau machen Query, Key und Value — und wie unterscheidet sich Attention von einer einfachen Gewichtungs-Summe?

## ✍️ Personal Notes

### Carsten's Reading Notes (2026-06-24)

- **Attention concept:** Only knew it by name before. Need to read the linked previous blog post about what Attention is.
- **⚠️ Attention in training vs. inference:** Initially thought Attention is only relevant for training, not for running a model. **(Correction: Attention runs on every single token at inference time too — see below)**
- **Parallelization:** The Transformer parallelizes well because "the word in each position flows through its own path in the encoder." Independent paths → can map to GPU parallelism. Makes sense, but details of GPU execution mapping still unclear.
- **"Attention Is All You Need" paper:** Would it make sense to read the original paper? **(→ Yes, absolutely. Added to feedback.)**
- **Feed Forward Network:** Don't know what this is yet. Is it relevant? **(→ Yes, see below)**
- **Self-attention intuition:** Self-attention = while inspecting a word, the model also looks at surrounding context and "bakes" the understanding into the word's representation. Classic example: "it" in a sentence — understanding what "it" refers to.
- **Self-attention calculation:** For each word, produce a series of scores for all words in the surrounding context. Score = query vector of current word × key vector of context word. For each word → N scores (N = number of words in context). Result: "attention score" per word, how much to pay attention to which surrounding word, down-leveling irrelevant ones.
- **Q/K/V matrices:** Don't yet understand what query, key, and value matrices/vectors are and how we get to them. 😄

*(notes will be continued)*

## 🔗 Cross-Links

- **Prerequisites:** None — this is the foundation
- **Next up:** [02-tokenization.md](02-tokenization.md) — Tokenization & Tokenizers
- **Related concepts:** [attention](../concepts/attention.md), [embeddings](../concepts/embeddings.md), [tokens](../concepts/tokens.md)
