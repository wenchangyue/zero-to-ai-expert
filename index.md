---
layout: default
title: AI lessons from first principles to working systems
description: >-
  Source-linked lessons for people who want to understand artificial intelligence,
  use current AI tools, and build reliable systems.
---

# Understand AI. Use AI. Build with AI.

Zero to AI Expert is a structured learning path for adults who use AI and want to understand what happens underneath the interface. Early lessons assume no technical background. Later courses add mathematics, algorithms, code, system design, and evaluation.

[Watch Zero to AI Expert on YouTube](https://www.youtube.com/@ZeroToAIExpert){:.primary-link}

## Lesson companions

{% assign sorted_lessons = site.lessons | sort: "date" | reverse %}
{% for lesson in sorted_lessons %}
<article class="lesson-card">
  <p class="eyebrow">{{ lesson.course }} · {{ lesson.level }}</p>
  <h2><a href="{{ lesson.url | relative_url }}">{{ lesson.title }}</a></h2>
  <p>{{ lesson.description }}</p>
</article>
{% endfor %}

## Learning path

<div class="path-grid">
  <div><strong>AI Foundations</strong><br>Core concepts and plain-language mechanisms.</div>
  <div><strong>Algorithms</strong><br>How learning methods solve different tasks.</div>
  <div><strong>Large Language Models</strong><br>Tokens, transformers, training, prompting, and tools.</div>
  <div><strong>AI Mathematics</strong><br>Vectors, probability, optimization, and linear algebra.</div>
  <div><strong>Practical AI Workflows</strong><br>Repeatable ways to use current AI products.</div>
  <div><strong>Build AI Systems</strong><br>APIs, retrieval, agents, evaluation, and deployment.</div>
  <div><strong>Reliability and Safety</strong><br>Failure modes, verification, risk, and human oversight.</div>
</div>

## What these pages add

Each companion page gives the short answer first, explains the mechanism, lists key terms, answers common follow-up questions, and links to the sources used for the lesson. The pages use stable URLs so viewers, search engines, and answer systems can return to the same material after the video description is published.
