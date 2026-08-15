---
published: true
layout: lesson
title: "Attention Is All You Need Explained: How the Original Transformer Works"
description: >-
  A source-linked, numerical walkthrough of the original Transformer, including
  token vectors, positional encoding, scaled dot-product attention, causal
  masking, cross-attention, training, inference, results, and limitations.
date: '2026-08-15'
modified: '2026-08-15'
course: AI Foundations
level: Beginner
duration_label: 54 minutes
duration: PT54M28S
youtube_url: "https://youtu.be/wisURfoIEYA"
video_id: "wisURfoIEYA"
video_status: private
upload_date: "2026-08-15"
keywords:
  - Attention Is All You Need explained
  - Transformer explained
  - how attention works
  - self-attention
  - scaled dot-product attention
  - multi-head attention
  - causal mask
  - cross-attention
  - positional encoding
  - Transformer architecture
quick_answer: >-
  The original Transformer converts token IDs into vectors, adds position
  information, and repeatedly uses attention and feed-forward layers to update
  those vectors. In one attention head, learned query-key dot products become
  normalized weights, and those weights mix value vectors. The decoder combines
  masked self-attention with encoder-decoder attention, projects its final vector
  into vocabulary logits, and selects the next token. Attention changes how
  information travels between positions, but embeddings, residual paths,
  normalization, feed-forward networks, and the output projection remain essential.
learning_outcomes:
  - Trace one translation through the encoder and decoder of the original Transformer.
  - Explain how token IDs, embeddings, and sinusoidal positional encodings form the model input.
  - Calculate one scaled dot-product attention head with explicit teaching numbers.
  - Distinguish encoder self-attention, masked decoder self-attention, and cross-attention.
  - Explain how causal masking prevents target positions from reading future answers.
  - Follow a decoder vector through vocabulary logits, softmax, and next-token generation.
  - Separate parallel training from sequential autoregressive inference.
  - State what the 2017 paper demonstrated and what it did not invent or prove.
faq:
  - q: Did Attention Is All You Need invent attention?
    a: No. Earlier sequence-to-sequence systems already used attention. The paper's central contribution was a complete sequence-transduction architecture built around attention without sequence-aligned recurrence or convolution.
  - q: What are queries, keys, and values?
    a: They are learned projections of sequence representations. Query-key dot products produce compatibility scores; normalized scores become weights that mix the value vectors.
  - q: Why divide attention scores by the square root of the key dimension?
    a: Under the paper's simplifying assumptions, dot-product variance grows with the key dimension. Dividing by its square root keeps scores closer to a scale where softmax is less likely to saturate.
  - q: What does the causal mask do?
    a: It replaces scores for future target positions with negative infinity before softmax, so those positions receive probability zero and cannot leak the answer during training.
  - q: What is cross-attention?
    a: The decoder supplies the queries, while the encoder's final output supplies keys and values. This lets the current target-side state mix relevant information from source positions.
  - q: Is the Transformer fully parallel?
    a: Training can compute many source and permitted target positions together. Autoregressive inference remains sequential across generated output tokens because each new token becomes input to the next step.
  - q: Do attention weights completely explain a prediction?
    a: No. They are intermediate mixing weights inside one head. The final prediction also depends on value vectors, projections, residual paths, feed-forward layers, normalization, later layers, and decoding.
sources:
  - '[Vaswani et al., Attention Is All You Need, arXiv version](https://arxiv.org/abs/1706.03762).'
  - '[Vaswani et al., Attention Is All You Need, NeurIPS 2017 proceedings](https://proceedings.neurips.cc/paper/7181-attention-is-all-you-need).'
  - '[Sennrich, Haddow, and Birch, Neural Machine Translation of Rare Words with Subword Units](https://aclanthology.org/P16-1162/).'
  - '[Tensor2Tensor reference implementation](https://github.com/tensorflow/tensor2tensor).'
---

## The complete route

The original Transformer is an encoder-decoder translation model. The encoder receives a source sentence and produces one contextual vector for every source position. The decoder receives the target prefix that is already known, reads the encoder output, and predicts the next target token. During training, the correct shifted target sequence is available under a causal mask. During inference, the decoder appends one selected token and runs again.

The model is attention-centered, not attention-only. Tokenization, embedding lookup, positional encoding, residual connections, Layer Normalization, position-wise feed-forward networks, and a vocabulary output projection are all required parts of the route.

## From text to position-aware vectors

Text is divided into tokens and mapped to integer IDs. An ID is an address into a learned embedding table; its numerical size does not measure meaning or importance. Looking up one row per token creates a matrix with one vector per sequence position. In the base model, the vector width is 512.

Embedding lookup alone does not encode order. The original model adds fixed sine and cosine position values to the scaled token embeddings. Different coordinate pairs oscillate at different frequencies. This makes otherwise identical token embeddings position-dependent before the first encoder layer.

## One attention head

For one sequence matrix `X`, learned projections produce queries, keys, and values:

`Q = XW_Q`  
`K = XW_K`  
`V = XW_V`

One scaled dot-product attention head computes:

`Attention(Q,K,V) = softmax(QKᵀ / √d_k)V`

Each query row is compared with every permitted key row. Dividing by `√d_k` controls the score scale. Softmax turns one row of scores into nonnegative weights that sum to one. Multiplying by `V` produces a weighted mixture of value rows. Queries and keys determine how much each source contributes; values provide the content being mixed.

The lesson calculates an invented two-dimensional example. Its displayed numbers are teaching values, not activations or parameters extracted from the trained 2017 system. The base model instead used eight heads with 64-dimensional queries, keys, and values per head. Concatenating eight head outputs restored the 512-dimensional model width before a learned output projection.

## Residual paths and feed-forward layers

Multi-head attention is one sublayer. The original encoder follows it with a residual connection and Layer Normalization, then applies a position-wise feed-forward network and another residual-plus-normalization step:

`LayerNorm(x + Sublayer(x))`

The residual path preserves the incoming representation while the sublayer proposes a change. The original feed-forward network expands each position from 512 to 2,048 values, applies ReLU, and projects back to 512. Attention moves information across positions; the feed-forward network transforms each position independently.

## Three uses of attention

Encoder self-attention obtains `Q`, `K`, and `V` from the encoder. Every source position can attend to every source position. Decoder masked self-attention obtains all three from the decoder but blocks future target positions. Encoder-decoder attention, often called cross-attention, obtains queries from the decoder and keys and values from the final encoder output.

The causal mask changes illegal future scores to negative infinity before softmax. Their normalized probabilities therefore become zero. This lets training compute all target positions together without allowing a position to read the target answer at that position or later positions.

## From the decoder vector to a token

At the decoder output, a learned linear transformation produces one logit per target-vocabulary token. A logit is an unnormalized score and can be positive or negative. Softmax converts the complete logit vector into probabilities. A decoding rule then chooses a token, appends it to the prefix, and begins the next inference step.

Training is different. A forward pass produces distributions for all permitted target positions. A loss compares them with the correct shifted targets. Backpropagation computes parameter gradients, and Adam updates embeddings, attention projections, feed-forward matrices, and other learned values. Ordinary inference uses the learned values without running this training update.

## Results and boundaries

The official NeurIPS 2017 paper reports 28.4 BLEU for the big English-to-German model and 41.0 BLEU for English-to-French. Later arXiv versions contain a different 41.8 English-to-French value in the abstract and Table 2 while retaining 41.0 in Section 6.1. Results must therefore be quoted with the paper version identified.

The paper did not invent attention, prove that attention weights fully explain a prediction, or make autoregressive output generation parallel. It demonstrated that a carefully constructed attention-centered architecture could replace sequence-aligned recurrence and convolution in the translation backbone while achieving strong quality and favorable training efficiency in the experiments reported.

## Page status

This is a reviewed lesson companion based on the final narration, mathematical audit, and cited primary sources. It reorganizes the spoken explanation for reading and is not a verbatim transcript. The YouTube video remains Private until the channel owner authorizes a public release.
