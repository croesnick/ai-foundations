# Mixture of Experts (MoE)

## 📖 Assigned Reading

- **Paper/Article:** A Visual Guide to Mixture of Experts (MoE)
- **Link:** https://newsletter.maartengrootendorst.com/p/a-visual-guide-to-mixture-of-experts
- **Type:** Blogpost (lecture-style, with visual diagrams)
- **Author/Source:** Maarten Grootendorst (Blogger, author of "Hands-On Graph Neural Networks")
- **Published:** January 2024
- **Read time:** ~25 min

### Bonus Reading

- **Paper:** Mixtral of Experts (arXiv:2401.04088)
- **Link:** https://arxiv.org/abs/2401.04088
- **Type:** arxiv Paper (Mistral AI, January 2024)
- **Note:** The canonical open-weights SMoE model. Short and readable. Skim sections 2 (Architecture) and 3 (Results) in particular.

## 🔑 Key Concepts

- Sparse vs. dense models: MoE increases parameter count without proportionally increasing compute
- The Feedforward Network (FFN) as the "expert" — MoE swaps the single FFN in a Transformer block for N parallel FFNs
- Router / gating network: a small linear layer + softmax that decides which experts handle a given token
- Top-k routing: typically k=1 or k=2 experts activated per token (Mixtral uses top-2)
- Sparse parameter count vs. active parameter count (e.g. Mixtral 8x7B: ~47B total, ~13B active per token)
- Load balancing & the "routing collapse" problem — why you need auxiliary losses to keep experts specialized
- Conditional computation: the core idea enabling sub-linear compute scaling with parameters

## 🤔 Focus Questions

- Why does MoE replace the FFN (and not the attention layer) with experts? What is it about the FFN that makes it a natural "expert"?
- What exactly does the router see as input, and what does its output mean? Trace a single token's path through an MoE block.
- How can a model with 47B parameters use only ~13B worth of compute per token? What does "active parameters" mean precisely?
- What is the load-balancing / routing-collapse problem, and why does training an MoE naively tend to "starve" some experts?
- Mixtral 8x7B beats Llama 2 70B on most benchmarks with far less active compute. What does that tell you about the relationship between model size and capability?

## ✍️ Personal Notes

*(Carsten's reflections, insights, and connections — added after reading)*

-

## 🔗 Cross-Links

- **Prerequisites:** [01-transformer.md](01-transformer.md), [03-pre-training.md](03-pre-training.md)
- **Next up:** [05-quantization.md](05-quantization.md) — Quantization
- **Related concepts:** [attention](../concepts/attention.md)
