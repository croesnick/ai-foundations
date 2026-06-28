# Tokenization & Tokenizers (BPE, SentencePiece, tiktoken)

## 📖 Assigned Reading

- **Paper/Article:** Let's build the GPT Tokenizer
- **Link:** https://www.youtube.com/watch?v=zduSFxRajkE
- **Type:** Video-Lecture (Code-Along)
- **Author/Source:** Andrej Karpathy
- **Published:** February 2024
- **Read time:** ~2h 15min

## 🔑 Key Concepts

- Tokenizer als eigenständige Pipeline-Stage (separates Training, eigene encode()/decode()-Funktionen)
- Byte Pair Encoding (BPE) — Merge-Rules lernen durch iteratives Zusammenfügen des häufigsten Paares
- Byte-level BPE & warum es Unicode/OOV-Probleme löst
- Vokabular-Größen vs. Sequence Length vs. Compute Trade-offs
- SentencePiece & Unigram LM-Tokenizer (Alternative zu BPE; tiktoken vs. HuggingFace tokenizers)
- Tokenization-Glitches: Warum "SolidGoldMagikarp" etc. existieren und wie sie Modelverhalten beeinflussen
- Special Tokens (`<|endoftext|>`, Chat-Templates etc.)

## 🤔 Focus Questions

- Was genau wird beim Tokenizer-Training gelernt, und was *nicht* (im Gegensatz zum LLM-Pretraining)?
- Warum kann ein und dasselbe Wort in verschiedenen Sprachen sehr unterschiedliche Token-Anzahlen haben, und welche praktische Konsequenzen hat das für Cost, Context-Window und Fairness?

## ✍️ Personal Notes

### Carsten's Reading Notes (2026-06-24)

- Tokens are the "atoms" of large language models.
- There's a freedom to choose the mapping `tokenize : text -> token[]`. One possibility: `embed_char : text -> char[]`. Another is `embed := byte_pair_encoding`.
- Vocabulary size is a **hyperparameter** we can tune. GPT-4 has around 100k tokens in their vocab. The tokenizer (model) is one we train and optimize for the task and model usage we have.
- `tiktoken` library is just inference, not training.
- **Special tokens:** OpenAI inserted the `<|endoftext|>` token between documents to make the model learn that what comes after this special token is unrelated to the context before.
- **Random knowledge:** The `im` in `<|im_start|>` stands for "imaginary monologue". Related: "fim" stands for "fill in the middle".
- **Super interesting bit:** In the cl100k tokenizer, `.DefaultCellStyle` is a single token. LLMs like GPT only see this as a single token and can't do operations like "count the 'l's" or "reverse this string" on it — because it's a single token, not individual letters!
- **Reading list additions:**
  - "Language Models are Unsupervised Multitask Learners" (GPT-2 paper, 2019) — Karpathy mentioned it as "fairly readable"
  - "Efficient training for large language models to fill in the middle" (FIM paper)
  - "Beren's Blog — Integer Tokenization is insane"

## 🔗 Cross-Links

- **Prerequisites:** [01-transformer.md](01-transformer.md)
- **Next up:** [03-pre-training.md](03-pre-training.md) — Pre-training → SFT → RLHF
- **Related concepts:** [tokens](../concepts/tokens.md), [embeddings](../concepts/embeddings.md)
