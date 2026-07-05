# Bonus Reading: Language Models are Unsupervised Multitask Learners (GPT-2 Paper)

## 📖 Assigned Reading

- **Paper/Article:** Language Models are Unsupervised Multitask Learners
- **Link:** https://cdn.openai.com/better-language-models/language_models_are_unsupervised_multitask_learners.pdf
- **Type:** arxiv Paper (Technical Report)
- **Author/Source:** Alec Radford, Jeffrey Wu, Rewon Child, David Luan, Dario Amodei, Ilya Sutskever (OpenAI)
- **Published:** 2019
- **Read time:** ~45 min

## 🔑 Key Concepts

- Language modeling as unsupervised distribution estimation
- Zero-shot task performance: LMs can perform downstream tasks without parameter/architecture modification
- WebText dataset: Reddit-based web scrape (≥3 karma) as quality filter
- BPE as "practical middle ground between character and word level" language modeling
- Generalization vs. Memorization: train/test overlap analysis with Bloom filters
- Zero-shot translation, summarization (TL;DR trick), Q&A (CoQA)

## ✍️ Personal Notes

### Carsten's Highlights & Annotations (extracted from PDF)

#### Page 1

**Highlight:** "Our suspicion is that the prevalence of single task training on single domain datasets is a major contributor to the lack of generalization observed in current systems."
- *Context:* Progress towards robust systems with current architectures is likely to require training and measuring performance on a wide range of domains and tasks.

#### Page 2

**Highlight:** "We demonstrate language models can perform down-stream tasks in a zero-shot setting"
- *Context:* ...without any parameter or architecture modification. We demonstrate this approach shows potential by highlighting the ability of language models to perform a wide range of tasks in a zero-shot setting.

**Highlight:** "language modeling"
- *Context:* At the core of our approach is language modeling. Language modeling is usually framed as unsupervised distribution estimation...

**Highlight:** "unsupervised distri- bution estimation"
- *Context:* ...from a set of examples (x1, x2, ..., xn) each composed of variable length sequences of symbols (s1, s2, ..., sn).

#### Page 3

**Highlight:** "Our approach motivates building as large and diverse a dataset as possible in order to collect natural lan- guage demonstrations of tasks in as varied of domains and contexts as possible."
- *Context:* Most prior work trained language models on a single domain of text, such as news articles, Wikipedia, or fiction books.

**Highlight:** "diverse and nearly unlimited text is web scrapes such as Common Crawl."
- *Context:* While these archives are many orders of magnitude larger than current language modeling datasets, they have significant data quality issues.

**Highlight:** "we want to avoid making assumptions about the tasks to be performed ahead of time"
- *Context:* While this is a pragmatic approach to improve performance on a specific task, we want to avoid making assumptions about the tasks to be performed ahead of time.

**Highlight:** "we created a new web scrape"
- *Context:* Instead, we created a new web scrape which emphasizes document quality.

**Highlight:** "starting point, we scraped all outbound links from Reddit,"
- *Context:* ...which received at least 3 karma. This can be thought of as a heuristic indicator for whether other users found the link interesting, educational, or just funny.

**Highlight:** "WebText"
- *Context:* The resulting dataset, WebText, contains the text subset of these 5 million links.

#### Page 4

**Highlight:** "current byte-level LMs are not competitive with word-level LMs on large scale datasets"
- *Context:* ...such as the One Billion Word Benchmark. We observed a similar performance gap in our own attempts to train standard byte-level LMs on WebText.

**Highlight:** "practical middle ground between character and word level"
- *Context:* Byte Pair Encoding (BPE) is a practical middle ground between character and word level language modeling...

**Highlight:** "interpolates between word level inputs for frequent symbol sequences and char- acter level inputs for infrequent symbol sequences"
- *Context:* ...which effectively interpolates between word level inputs for frequent symbol sequences and character level inputs for infrequent symbol sequences.

**Highlight:** "5% held-out sample of WebText"
- *Context:* The learning rate of each model was manually tuned for the best perplexity on a 5% held-out sample of WebText.

#### Page 5

**Highlight:** "gains of 2.5 to 5 perplexity for GPT-2"
- *Context:* We observe gains of 2.5 to 5 perplexity for GPT-2 with these de-tokenizers.
- *Annotation:* what does "perplexity" mean here?

**Highlight:** "predict the final word of sentences which require at least 50 tokens of context for a human"
- *Context:* The LAMBADA dataset tests the ability of systems to model long-range dependencies in text. The task is to predict the final word of sentences which require at least 50 tokens of context for a human to successfully predict.

#### Page 6

**Highlight:** "perform commonsense reasoning by measuring its ability to resolve ambiguities in text"
- *Context:* The Winograd Schema challenge was constructed to measure the capability of a system to perform commonsense reasoning by measuring its ability to resolve ambiguities in text.

**Highlight:** "CoQA tests reading comprehension capabilities and also the ability of models to answer questions that depend on conversation history (such as "Why?")."
- *Context:* The Conversation Question Answering dataset consists of documents from 7 different domains paired with natural language dialogues.

**Highlight:** "final token A: achieves 55 F1 on the development set"
- *Context:* Greedy decoding from GPT-2 when conditioned on a document, the history of the associated conversation, and a final token A: achieves 55 F1 on the development set.

**Highlight:** "some inspection of its answers and errors suggests GPT-2 often uses simple retrieval based heuristics such as answer with a name from the document in response to a who question."
- *Context:* While GPT-2's performance is exciting for a system without any supervised training, some inspection of its answers and errors suggests GPT-2 often uses simple retrieval based heuristics.

**Highlight:** "we add the text TL;DR: after the article and generate 100 tokens"
- *Context:* To induce summarization behavior we add the text TL;DR: after the article and generate 100 tokens with Top-k random sampling with k = 2.

**Highlight:** "we condition the language model on a context of example pairs of the format english sentence = french sentence"
- *Context:* We test whether GPT-2 has begun to learn how to translate from one language to another.

**Highlight:** "after a fi- nal prompt of english sentence ="
- *Context:* ...and then after a final prompt of english sentence = we sample from the model with greedy decoding.

**Highlight:** "GPT-2 gets 5 BLEU, which is slightly worse than a word-by-word substitution"
- *Annotation:* It's better in english because (a) the tokenizer was trained on an english corpus, I expect (b) the model itself was trained primarily on English text

#### Page 7

**Highlight:** "very strong English language model to perform significantly better, achieving 11.5 BLEU. This outperforms several unsupervised machine translation baselines"
- *Context:* On the WMT-14 French-English test set, GPT-2 is able to leverage its very strong English language model to perform significantly better.

**Highlight:** "still much worse than the 33.5 BLEU of the current best unsupervised machine translation approach"
- *Context:* ...but is still much worse than the 33.5 BLEU of the current best unsupervised machine translation approach.

**Highlight:** "Performance on this task was sur- prising to us, since we deliberately removed non-English webpages from WebText as a filtering step."
- *Context:* In order to confirm this, we ran a byte-level language detector on WebText which detected only 10MB of data in the French language.

#### Page 8

**Highlight:** "important to analyze how much test data also shows up in the training data"
- *Context:* As the size of datasets increases this issue becomes increasingly likely which suggests a similar phenomena could be happening with WebText.

**Highlight:** "CIFAR-10 has 3.3% overlap between train and test images"
- *Context:* Recent work in computer vision has shown that common image datasets contain a non-trivial amount of near-duplicate images.

**Highlight:** "Bloom filters"
- *Annotation:* What's a Bloom Filter? Shall I learn about them?

**Highlight:** "Understanding and quantifying how highly similar text im- pacts performance is an important research question."
- *Context:* Better de-duplication techniques such as scalable fuzzy matching could also help better answer these questions.

#### Page 9

**Highlight:** "More in- spirational to our work was the observation of Liu et al. (2018) that a model trained to generate Wikipedia articles also learned to translate names between languages."
- *Context:* Interesting learned functionality in generative models has been documented before.

**Highlight:** "the zero-shot performance of GPT-2 is still far from use-able."
- *Context:* While suggestive as a research result, in terms of practical applications, the zero-shot performance of GPT-2 is still far from use-able.

#### Page 10

**Highlight:** "able to perform well across many domains and datasets"
- *Context:* When a large language model is trained on a sufficiently large and diverse dataset it is able to perform well across many domains and datasets.

**Highlight:** "trained on a sufficiently large and diverse dataset"
- *Context:* The diversity of tasks the model is able to perform in a zero-shot setting suggests that high-capacity models trained to maximize the likelihood...

### Open Questions from Annotations

1. **"What does 'perplexity' mean here?"** (Page 5) — Perplexity is a standard LM metric measuring how "surprised" the model is by the next token. Lower = better. It's the exponentiated average negative log-likelihood: PPL = exp(-1/N * Σ log P(x_i | x_<i)). A perplexity of 2.5 means the model is as uncertain as if choosing uniformly among 2.5 tokens. (→ Will be covered in depth in Topic 3: Pre-training)

2. **"It's better in english because (a) the tokenizer was trained on an english corpus, I expect (b) the model itself was trained primarily on English text"** (Page 6) — Correct on both counts. The BPE tokenizer was trained on English-dominant WebText, so French text gets fragmented into more tokens. And the model itself saw almost no French (only ~10MB in WebText). Both factors compound.

3. **"What's a Bloom Filter? Shall I learn about them?"** (Page 8) — A Bloom Filter is a probabilistic data structure for fast set membership tests. You can ask "is X in the set?" and get either "definitely no" or "probably yes" (with a tunable false-positive rate). OpenAI used them to check how much test data leaked into training data. It's a CS classic — worth knowing, but not AI-specific. (→ Adding to reading list as a side topic.)

## 🔗 Cross-Links

- **Related topics:** [02-tokenization.md](02-tokenization.md) (BPE), [03-pre-training.md](03-pre-training.md) (training, zero-shot)
- **Related concepts:** [tokens](../concepts/tokens.md), [loss-functions](../concepts/loss-functions.md) (perplexity)
