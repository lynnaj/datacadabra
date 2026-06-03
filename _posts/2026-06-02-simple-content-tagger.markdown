---
layout: post
title:  "Simple Content Tagger with a Huggingface Transformer Model"
date:   2026-06-02 12:00:00 -0700
categories: Machine Learning
---

I built a zero-shot content tagger as a quick proof of concept using `facebook/bart-large-mnli`. Try it here: [Content Tagger on Hugging Face Spaces](https://huggingface.co/spaces/lynnaj/content_tagger)

**How it works:** paste any text, define your own label set (e.g., "tech, sports, politics"), and the model classifies it — no fine-tuning required.

### The Model

BART (Bidirectional and Auto-Regressive Transformers) is a sequence-to-sequence transformer architecture developed by Meta/Facebook. The `-mnli` suffix means it was fine-tuned on the Multi-Genre Natural Language Inference (MNLI) dataset, which is what enables zero-shot classification.

The idea: zero-shot classification reframes the labeling task as a natural language inference problem. For each candidate label, the model asks "does this text entail the topic: [label]?" and scores the probability. No labeled examples needed — just a model that understands semantic relationships well enough to reason about novel categories.

BART shares the same transformer foundations as BERT and GPT — encoder-decoder attention, self-attention layers, positional embeddings — with a different pretraining objective. It corrupts input text in various ways (masking, shuffling, deletion) and trains the model to reconstruct the original, giving it strong bidirectional understanding on the encoder side and generative capability on the decoder side.
