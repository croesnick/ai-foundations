# Pre-training → SFT → RLHF / DPO / GRPO

## 📖 Assigned Reading

- **Paper/Article:** Language Models are Unsupervised Multitask Learners (GPT-2)
- **Link:** https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf
- **Type:** arxiv-style Technical Report / Original Paper (PDF)
- **Author/Source:** Alec Radford, Jeffrey Wu, Rewon Child, David Luan, Dario Amodei, Ilya Sutskever (OpenAI)
- **Published:** Februar 2019
- **Read time:** ~30 min

## 🔑 Key Concepts

- **Unsupervised Multitask Learning:** Ein einzelnes Sprachmodell, das ohne task-spezifisches Training viele Aufgaben (Übersetzung, QA, Summarization) gleichzeitig lernt — ausschließlich durch Next-Token-Prediction.
- **Zero-Shot Generalization:** Das Modell wird auf Aufgaben getestet, für die es nie explizit trainiert wurde; es folgt Instruktionen bzw. Mustern, die in der natürlichen Sprachverteilung im Pre-training-Datensatz (WebText) enthalten sind.
- **WebText-Datensatz:** ~40 GB Text aus outbound Reddit-Links mit Karma ≥ 3; bewusste Filterung für Qualität.
- **Byte-Pair-Encoding (BPE) auf Byte-Level:** GPT-2 nutzt Byte-level BPE statt Word-level, um OOV-Probleme zu vermeiden — verbindet dies mit Topic 2 (Tokenisierung).
- **Scale-Hypothese:** Die zentrale These — mehr Parameter + mehr Daten → bessere Zero-Shot-Performance; 1.5B-Parameter-Modell zeigt messbare Verbesserungen auf vielen Benchmarks.
- **Pre-training als universelle Basis:** Das Paper argumentiert, dass das traditionelle "finetune pro Task"-Paradigma durch ein "großes generisches Modell, das alles im Pre-training lernt"-Paradigma abgelöst werden kann.
- **Emergent Capabilities:** (frühe Beobachtung) Mit wachsender Modellgröße erscheinen Fähigkeiten, die bei kleinen Modellen nicht beobachtbar waren — ein Vorläufer späterer "Emergence"-Diskussionen.

## 🤔 Focus Questions

- Wie argumentiert das Paper, dass ein reines Language Model (nur Next-Token-Prediction) Aufgaben wie Übersetzung oder QA "ohne" direkte Supervision lernen kann? Woher kommt die Supervision eigentlich?
- Was ist der Unterschied zwischen "unsupervised" (in diesem Kontext) und dem, was später als Instruction-Tuning / SFT bekannt wird?
- Warum hat OpenAI das Modell zunächst nicht voll veröffentlicht (Release-Staging)? Was waren die Sicherheitsbedenken?
- Inwiefern war GPT-2 ein Brückenpfeiler von "finetune ein Modell pro Task" (wie BERT) hin zum modernen "Pre-train once, prompt/align afterwards" Paradigma (GPT-3, InstructGPT)?
- Wie hängt die Byte-level-BPE-Tokenisierung von GPT-2 mit dem zusammen, was du in Topic 2 über Tokenizer gelernt hast?

## ✍️ Personal Notes

*(Carsten's reflections, insights, and connections — added after reading)*

-

## 🔗 Cross-Links

- **Prerequisites:** [01-transformer.md](01-transformer.md), [02-tokenization.md](02-tokenization.md)
- **Next up:** [04-moe.md](04-moe.md) — Mixture of Experts
- **Related concepts:** [backprop](../concepts/backprop.md), [loss-functions](../concepts/loss-functions.md), [attention](../concepts/attention.md)
