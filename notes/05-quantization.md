# Quantization (GGUF, GPTQ, AWQ, EXL2, BitsAndBytes)

## 📖 Assigned Reading

**A Visual Guide to Quantization**

- **Paper/Article:** A Visual Guide to Quantization
- **Link:** https://newsletter.maartengrootendorst.com/p/a-visual-guide-to-quantization
- **Type:** Blogpost (visual guide / lecture-style newsletter)
- **Author/Source:** Maarten Grootendorst (Also Open-source AI Newsletter)
- **Published:** 2024-11 (November 2024)
- **Read time:** ~30 min

## 🔑 Key Concepts

- Quantization: FP32 → FP16/BF16 → INT8 → INT4 — reduziert Speicher und beschleunigt Inference auf Kosten von Genauigkeit
- Post-Training Quantization (PTQ) vs. Quantization-Aware Training (QAT): Der Unterschied zwischen "einfach abrunden" und einem Minimierungsproblem
- Absmax- & Zero-Point-Quantization: wie man fp32-Tensoren symmetrisch/asymmetrisch auf ein niedrigeres Bit-Format mapt
- Clipping vs. Outliers: Ausreißer legen den Quantization Range faktisch fest — Clipping erlaubt bewussten Präzisionsverlust
- Weight-Only- vs. Weight+Activation-Quantization (W8A16, W4A16) und warum das letztgenannte schwieriger ist
- Per-Tensor / Per-Channel / Per-Group Quantization: Skalierung auf verschiedenen Granularitäts-Ebenen
- GPTQ: 4-Bit-Quantisierung über ein iteratives Approximationsschema, GPU-beschleunigt
- AWQ: „Aktivierungsbewusste" Skalierung schützt nur die wichtigsten Gewichte gegen Quantisierungsfehler
- 1.58-Bit Quantisierung (BitNet): Extreme Quantisierung während des Trainings selbst (QAT)

## 🤔 Focus Questions

- Warum schadet ein einzelner großer Ausreißer (Outlier) beim Quantisieren eines ganzen Tensors so viel — und wofür lösen Clipping und Per-Channel-Quantization das Problem?
- Was ist der Unterschied zwischen Weight-Only-Quantisierung (z.B. GPTQ) und Weight+Activation-Quantisierung (W4A16) — und warum ist zweiteres schwieriger?
- Wie minimiert GPTQ den Quantisierungsfehler iterativ — warum funktioniert ein "einfaches Abrunden" (RTN) schlechter?
- Nach welcher Logik schützt AWQ genau die Gewichte, die mit wichtigen Aktivierungen verbunden sind?
- Warum kann BitNet 1.58-Bit nur mit QAT (Training mit Quantisierung) und nicht post-training funktionieren?

## ✍️ Personal Notes

*(Carsten's reflections, insights, and connections — added after reading)*

-

## 🔗 Cross-Links

- **Prerequisites:** [03-pre-training.md](03-pre-training.md)
- **Next up:** [06-model-families.md](06-model-families.md) — Model Families & Ecosystem
- **Related concepts:** [quantization](../concepts/quantization.md)
