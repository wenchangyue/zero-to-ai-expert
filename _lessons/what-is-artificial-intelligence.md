---
layout: lesson
title: "What Is Artificial Intelligence? A Beginner's Guide to Modern AI"
description: >-
  A source-linked introduction to AI systems, machine learning, training and
  inference, deep learning, large language models, and verification.
date: '2026-08-03'
modified: '2026-08-03'
course: AI Foundations
level: Beginner
duration_label: 19 minutes
duration: PT19M34S
youtube_url: https://youtu.be/4ir_uHC7bnk
video_id: 4ir_uHC7bnk
video_status: private
upload_date: '2026-08-03'
keywords:
  - artificial intelligence
  - AI for beginners
  - machine learning
  - deep learning
  - large language models
  - training and inference
  - AI verification
quick_answer: >-
  Artificial intelligence is a broad category of machine-based systems. An AI
  system takes an input, transforms it with human-written rules or patterns
  learned from data, and produces an output for a human-defined task. Modern AI
  often uses machine learning. Training adjusts model parameters from examples;
  inference uses the trained parameters on new input. A fluent output still needs
  verification when accuracy matters.
learning_outcomes:
  - Identify the input, transformation, output, and verification step in an AI system.
  - Separate explicit rules from patterns learned through machine learning.
  - Explain how training differs from inference.
  - Place deep learning and large language models inside the larger AI category.
  - Explain why generated text can sound confident without being verified.
faq:
  - q: Is artificial intelligence one specific technology?
    a: No. AI is a category that includes rule-based systems, machine-learning models, and products that combine models with databases, tools, interfaces, and human review.
  - q: Are AI and machine learning the same thing?
    a: Machine learning is one approach within AI. Some AI systems follow explicit rules written by people. Many current systems use both learned models and explicit rules.
  - q: What is the difference between training and inference?
    a: Training uses data and an objective to adjust a model's parameters. Inference keeps those trained parameters fixed and uses them to produce an output for new input.
  - q: What makes deep learning deep?
    a: The word deep refers to multiple computational layers between input and output. Training adjusts parameters across those layers so the network can build useful intermediate representations.
  - q: How does a large language model generate text?
    a: Many generative language models process tokens and estimate a probability distribution for the next token. A decoding rule selects a token, adds it to the context, and repeats the process.
  - q: Is a chatbot the same thing as a language model?
    a: No. A chatbot product may add system instructions, retrieval, tools, safety rules, memory, logging, and a user interface around a language model.
  - q: Why can an AI answer be fluent and wrong?
    a: Token generation and factual verification are different operations. The model can produce a likely sequence without checking it against a trusted source, calculation, experiment, or test.
sources:
  - '[NIST, Artificial Intelligence glossary entry](https://csrc.nist.gov/glossary/term/artificial_intelligence).'
  - '[OECD, Explanatory memorandum on the updated definition of an AI system](https://oecd.ai/en/ai-publications/explanatory-memorandum-on-the-updated-oecd-definition-of-an-ai-system).'
  - '[Google for Developers, Machine Learning Glossary](https://developers.google.com/machine-learning/glossary/).'
  - '[LeCun, Bengio, and Hinton, Deep learning, Nature 2015](https://doi.org/10.1038/nature14539).'
  - '[Vaswani et al., Attention Is All You Need](https://arxiv.org/abs/1706.03762).'
  - '[Brown et al., Language Models are Few-Shot Learners](https://arxiv.org/abs/2005.14165).'
  - '[Ouyang et al., Training language models to follow instructions with human feedback](https://arxiv.org/abs/2203.02155).'
  - '[NIST AI 600-1, Generative Artificial Intelligence Profile](https://doi.org/10.6028/NIST.AI.600-1).'
---

## The practical frame: input, transformation, output, verification

A spam filter reads an email and returns a label. A recommendation system uses information about a viewer and a collection of videos to return a ranking. A language model processes tokens and returns probabilities for what may come next.

These products do different jobs, so the label *AI* alone tells us very little. Start with the input and output. Then inspect the process that connects them. The final question is how the result is checked and what happens when it is wrong.

This frame also prevents a common mistake: treating AI as one machine with one level of intelligence. A narrow classifier, a recommendation model, and a tool-using assistant can all belong to the category without sharing the same abilities or risks.

## Rules and learning

A rule-based spam filter might add points when a subject contains selected phrases or when an address appears on a block list. A programmer chooses the clues, their weights, and the threshold.

Machine learning changes how the internal mapping is set. People still choose the task, collect examples, define the target, and select a learning method. The training procedure adjusts model parameters to reduce error on those examples.

Real products often combine both approaches. A bank can use a learned model to estimate fraud risk and an explicit rule to block transactions above a chosen threshold. The model supplies a score; the rule determines the action.

## Model, training, and inference

A model contains a structure and parameter values that map input to output. During training, an objective measures error and an optimization method updates those parameters. The process repeats over many examples.

Inference begins after training. The parameters normally stay fixed while a new input produces a new output. One training run may support many later inference requests.

Performance on training examples does not establish performance on new data. Developers use validation and test data to estimate generalization. They also test important subgroups and failure cases because an average score can hide a serious problem.

## Deep learning

Deep learning is a family within machine learning. A deep neural network passes numerical representations through multiple layers. Early layers can capture local patterns; later layers combine those patterns into representations that help with the task.

Backpropagation calculates how changes in each parameter would affect the loss. An optimizer uses that information to update the network. The word *neural* reflects a loose historical inspiration. A modern neural network remains a system of numerical transformations rather than a reproduction of a human brain.

## Large language models

A tokenizer divides text into tokens. A token may be a whole word, part of a word, punctuation, or another text unit. Many generative language models process the current token sequence and estimate probabilities for the next token.

Generation selects one token according to a decoding rule, adds it to the context, and runs the model again. Repetition produces a sentence, a paragraph, or code.

Pretraining adjusts the model's parameters across large text collections. Instruction tuning and preference-based methods can make the base model more useful in conversation. The surrounding application may add retrieval, external tools, safety checks, and system instructions. Those additions help explain why a chat assistant is more than an isolated next-token model.

## Fluent output and verified output

A likely token sequence can be accurate, false, inconsistent, or unsupported by the input. NIST uses *confabulation* for confidently presented false content or content that conflicts with the prompt or earlier output. *Hallucination* is the more common informal term.

Verification must come from another operation. A retrieval system can supply documents. A calculator can check arithmetic. Code can run against tests. A person can compare a claim with a primary source. The appropriate check depends on the task and the cost of being wrong.

## Page status

This is a reviewed lesson companion based on the final narration and sources. It reorganizes the spoken explanation for reading and is not labeled as a verbatim transcript. Last reviewed: 2026-08-03.
