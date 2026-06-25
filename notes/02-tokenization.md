# Tokenization & Tokenizers (BPE, SentencePiece, tiktoken)

## 📖 Assigned Reading

- **Paper/Article:** "Let's build the GPT Tokenizer"
- **Link:** https://www.youtube.com/watch?v=zduSFxRajkE
- **Type:** Video / hands-on tutorial
- **Author/Source:** Andrej Karpathy
- **Published:** 2024-02-20
- **Read time:** ~120 min (full video) — kann in 2-3 Sessions geschaut werden

## 🔑 Key Concepts

- **Byte Pair Encoding (BPE)** — iterativer Aufbau eines Vokabulars durch wiederholtes Mergen des häufigsten Zeichenpaars
- **Byte-level vs. character-level BPE** — warum GPT-2 auf Byte-Ebene arbeitet (deckt beliebige Unicode-Strings ab, kein "unknown token"-Problem)
- **Vokabular-Größe & Merges** — Trade-off zwischen Vocab-Size, Sequence Length und Modellgröße
- **tiktoken** — OpenAI's schnelle Regex-basierte Byte-Level BPE Implementierung (GPT-4 / cl100k_base)
- **SentencePiece** — Google's Framework; implementiert BPE und Unigram Language Model; sprachunabhängig
- **Encoding / Decoding** — der Round-Trip String → Token-IDs → String; Determinismus & Edge Cases
- **Pre-tokenization (Regex-Splitting)** — wie Text vor dem BPE-Merge in "Wörter" aufgeteilt wird (z.B. GPT-4's Regex-Pattern)
- **Special Tokens** — BOS / EOS / PAD und ihre Rolle im Training
- **Tokenization-Gotchas** — warum LLMs bei Arithmetik, Code und Whitespace Fehler machen (Token-Grenzen ≠ logische Grenzen)
- **Multilingualität** — warum nicht-englische Texte mehr Tokens verbrauchen und warum das Kosten & Kontextfenster beeinflusst

## 🤔 Focus Questions

- Wie entscheidet der BPE-Algorithmus, welcher Merge als nächstes durchgeführt wird, und warum ist diese Reihenfolge wichtig für die Qualität des finalen Vokabulars?
- Was ist der entscheidende Vorteil von Byte-Level BPE gegenüber Character-Level BPE — und warum hat OpenAI diesen Weg gewählt?
- Wie unterscheiden sich SentencePiece (Unigram LM) und tiktoken (BPE) in ihrer Philosophie und Anwendung?
- Wie können Token-Grenzen das Modellverhalten beeinflussen — z.B. bei einfachen Rechenaufgaben (" 7+8") oder Code-Snippets?
- Warum kostet derselbe Satz in Deutsch mehr Tokens als in Englisch, und welche praktischen Konsequenzen hat das?

## ✍️ Personal Notes

*(Carsten's reflections, insights, and connections — added after reading)*

-

## 🔗 Cross-Links

- **Prerequisites:** [01-transformer.md](01-transformer.md)
- **Next up:** [03-pre-training.md](03-pre-training.md) — Pre-training → SFT → RLHF
- **Related concepts:** [tokens](../concepts/tokens.md), [embeddings](../concepts/embeddings.md)
