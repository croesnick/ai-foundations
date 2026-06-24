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

*(Carsten's reflections, insights, and connections — added after reading)*

-

## 🔗 Cross-Links

- **Prerequisites:** None — this is the foundation
- **Next up:** [02-tokenization.md](02-tokenization.md) — Tokenization & Tokenizers
- **Related concepts:** [attention](../concepts/attention.md), [embeddings](../concepts/embeddings.md), [tokens](../concepts/tokens.md)
