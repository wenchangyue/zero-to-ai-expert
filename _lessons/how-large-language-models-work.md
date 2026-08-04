---
published: true
layout: lesson
title: "How Large Language Models Work: A Step-by-Step Visual Guide"
description: >-
  A source-linked explanation of tokenization, embeddings, Transformer blocks,
  attention, logits, autoregressive decoding, the KV cache, and LLM training.
date: '2026-08-03'
modified: '2026-08-03'
course: Large Language Models
level: Beginner
duration_label: 57 minutes
duration: PT57M08S
youtube_url: "https://youtu.be/yD3PQM_K2uk"
video_id: "yD3PQM_K2uk"
video_status: private
upload_date: "2026-08-04T01:20:57+00:00"
keywords:
  - how large language models work
  - LLM explained
  - Transformer
  - self-attention
  - tokenization
  - embeddings
  - logits and softmax
  - KV cache
  - autoregressive generation
  - LLM training
quick_answer: >-
  A large language model converts text into token IDs, looks up a learned vector
  for each ID, and passes the resulting matrix through many Transformer blocks.
  Causal self-attention mixes information from allowed earlier positions, while
  an MLP transforms each position. The final hidden vector is projected into one
  logit per vocabulary token. A decoder turns those logits into one selected
  token, appends it to the context, and repeats. Training uses next-token errors
  and backpropagation to adjust the model's parameters; ordinary chat inference
  keeps those base parameters fixed.
learning_outcomes:
  - Trace a user request from serialized text to token IDs and embedding vectors.
  - Calculate the sequence of operations in scaled dot-product attention.
  - Explain the separate roles of queries, keys, values, residual paths, and the MLP.
  - Distinguish logits, probabilities, temperature, top-k, and top-p decoding.
  - Explain why prefill, decode, and the KV cache have different computational roles.
  - Separate training-time parameter updates from inference-time activations and cache.
  - Distinguish tokenizer vocabulary, model parameters, activations, cache, and external sources.
faq:
  - q: Does a language model read words directly?
    a: No. A tokenizer converts text into token IDs. A token can be a word, part of a word, punctuation, bytes, or another text unit, depending on the tokenizer.
  - q: What do query, key, and value mean in self-attention?
    a: They are three learned projections of the same sequence representation. Query-key dot products produce comparison scores. After scaling, masking, and softmax, those scores become weights used to mix the value vectors.
  - q: Why is attention divided by the square root of the key dimension?
    a: Dot products tend to grow in magnitude as the dimension grows. Dividing by the square root of the key width keeps the scores in a range where softmax is less likely to saturate.
  - q: Does an attention weight explain why the complete model chose a token?
    a: No. It is a mixing weight inside one head at one layer. The final output also depends on value vectors, output projections, residual paths, MLPs, later layers, and decoding.
  - q: What is the difference between a logit and a probability?
    a: A logit is an unnormalized score for a vocabulary token. Softmax transforms the full logit vector into nonnegative probabilities that sum to one.
  - q: What does a KV cache store?
    a: It stores previously computed key and value rows for each layer during autoregressive generation. It avoids recomputing them for the prefix, but it does not make future token choices parallel.
  - q: Does chatting with an LLM retrain it?
    a: Ordinary inference changes the context, activations, and often the KV cache. It does not normally run backpropagation or update the base model parameters.
  - q: Where does an LLM store facts?
    a: There is no single readable fact table. Learned behavior is distributed across many parameters. A product can also supply current information through retrieval, databases, or tools, which are separate from the model weights.
sources:
  - '[Vaswani et al., Attention Is All You Need](https://arxiv.org/abs/1706.03762).'
  - '[Sennrich, Haddow, and Birch, Neural Machine Translation of Rare Words with Subword Units](https://aclanthology.org/P16-1162/).'
  - '[Kudo and Richardson, SentencePiece](https://aclanthology.org/D18-2012/).'
  - '[Bengio et al., A Neural Probabilistic Language Model](https://www.jmlr.org/papers/v3/bengio03a.html).'
  - '[Su et al., RoFormer: Enhanced Transformer with Rotary Position Embedding](https://arxiv.org/abs/2104.09864).'
  - '[Zhang and Sennrich, Root Mean Square Layer Normalization](https://arxiv.org/abs/1910.07467).'
  - '[Shazeer, GLU Variants Improve Transformer](https://arxiv.org/abs/2002.05202).'
  - '[Ainslie et al., GQA: Training Generalized Multi-Query Transformer Models](https://arxiv.org/abs/2305.13245).'
  - '[Holtzman et al., The Curious Case of Neural Text Degeneration](https://arxiv.org/abs/1904.09751).'
  - '[Kwon et al., Efficient Memory Management for Large Language Model Serving with PagedAttention](https://arxiv.org/abs/2309.06180).'
  - '[Grattafiori et al., The Llama 3 Herd of Models](https://arxiv.org/abs/2407.21783).'
---

## From text to model input

A chat interface does not usually send one isolated sentence straight into a neural network. The product assembles an ordered sequence that can include a system instruction, earlier turns, the current user message, tool results, retrieved passages, and a marker that tells the model where assistant generation begins. The tokenizer then converts that serialized text into token IDs.

The tokenizer vocabulary is a finite table that maps token pieces to integers. It does not contain dictionary definitions or one row for every fact the model can discuss. Different tokenizers can divide the same text differently. Byte-pair encoding, byte-level methods, WordPiece, and unigram tokenization are related approaches, not one universal algorithm.

## From IDs to vectors

Each token ID selects one row from a learned embedding matrix. If a prompt contains *n* tokens and the model width is *d*, stacking those rows produces a matrix with shape *n × d*. Rows correspond to sequence positions. Columns are learned coordinates; they should not be treated as a spreadsheet of permanently named concepts.

Order must enter the computation because embedding lookup alone does not say which token came first. The original Transformer added position encodings to token embeddings. Many later decoder models use rotary position embeddings, or RoPE, which rotate pairs of query and key coordinates by position-dependent angles. These are architecture choices rather than universal LLM features.

## One Transformer block

A common modern pre-norm block can be summarized as two learned updates to a residual stream:

`H = X + Attention(Norm(X))`

`X_next = H + MLP(Norm(H))`

The residual path preserves the current representation while attention or the MLP computes an update. RMSNorm controls vector scale without LayerNorm's re-centering step. Other model families use different normalization placement, activation functions, bias terms, dense or mixture-of-experts MLPs, and different attention layouts.

## Scaled dot-product attention

Self-attention forms three learned projections from the same sequence matrix:

`Q = XW_Q`  
`K = XW_K`  
`V = XW_V`

For one query position, dot products compare its query with the keys at allowed positions. The model divides those scores by the square root of the key width, applies a causal mask to future positions, and runs softmax across the remaining scores:

`A = softmax((QKᵀ / √d_k) + M_causal)`

The attention output is `O = AV`. Queries and keys determine the weights; value vectors supply the content being mixed. An attention weight is therefore a computational quantity inside one head. It is not a complete explanation of the final model decision.

Multiple heads use different learned projections. Their outputs are concatenated and projected back to model width. Grouped-query attention can use more query heads than key-value heads, reducing the amount of key-value data stored during generation without changing the basic compare-and-mix sequence.

## Residual update and MLP

After attention, the output projection writes an update back to the residual stream. The MLP then acts on each token row independently. A SwiGLU-style example projects a row into a wider space, applies a SiLU gate, multiplies the gate and content projections element by element, and projects the result back to model width.

Attention moves information across sequence positions. The MLP applies a learned nonlinear transformation within each position. Repeating these operations across many blocks turns a fixed token embedding into a context-dependent hidden vector.

## From the final hidden vector to one token

For next-token generation, the model uses the hidden vector at the last available sequence position. A final normalization and output projection produce one logit for each vocabulary token. Logits are raw scores; they do not need to be positive or sum to one. Softmax converts them into a probability distribution.

The decoder then applies a selection rule. Greedy decoding chooses the largest probability. Temperature rescales all logits before softmax. Top-k retains a fixed number of candidates. Top-p retains the smallest high-probability set whose cumulative probability reaches a threshold. Sampling draws from the retained distribution. These rules change token selection without changing the learned weights.

## Prefill, decode, and the KV cache

During prefill, the model processes all prompt positions together under the causal mask. During decode, it adds one new token position per iteration. A KV cache stores the keys and values already computed at every layer. The new query can read those cached rows, and the new key and value are appended.

This avoids recomputing the full prefix at every step. It does not remove the sequential dependency between generated tokens: token 20 cannot be chosen until token 19 has joined the context.

## Training and inference

Training shifts a known token sequence by one position. Inputs contain tokens 1 through *n − 1*; targets contain tokens 2 through *n*. A causal forward pass produces a next-token prediction at every position. Cross-entropy measures the probability assigned to each correct target. Backpropagation applies the chain rule through the output projection, Transformer blocks, and embeddings. An optimizer then updates the parameters.

Ordinary inference does not perform this update. It changes the prompt context, intermediate activations, and often the KV cache while keeping the base model parameters fixed. Pretraining is also not the complete assistant: instruction tuning, preference-based methods, system instructions, retrieval, tools, and product rules can all change the behavior a user sees.

## Five objects often called memory

The tokenizer vocabulary stores token pieces and IDs. Model parameters store learned numerical weights. Activations are temporary vectors in one forward pass. The KV cache stores current-sequence keys and values. External retrieval supplies documents, databases, or tool results through the product.

These objects contain different information and have different lifetimes. Treating all five as one kind of memory hides the mechanism and leads to errors such as looking for facts in the tokenizer vocabulary or assuming that a longer chat has retrained the base model.

## Boundary

This lesson follows a representative dense decoder-only Transformer and uses invented numerical examples. Real systems can use other tokenizers, normalization schemes, position methods, attention variants, mixture-of-experts layers, weight tying, quantization, speculative decoding, safety filters, and serving optimizations. The general causal path remains useful, but an exact implementation must be checked against that model's architecture and runtime.

Fluent continuation is not automatic fact verification. A model can produce a locally plausible sequence without comparing it with a current primary source, calculator, execution trace, experiment, or test. Verification is a separate operation chosen for the task.

## Page status

This is a reviewed lesson companion based on the final narration, captions, and cited sources. It reorganizes the spoken explanation for reading and is not labeled as a verbatim transcript. Last reviewed: 2026-08-03.
