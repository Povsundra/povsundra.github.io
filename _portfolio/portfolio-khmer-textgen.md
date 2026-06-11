---
title: "LSTM-based Khmer Text Style Transfer"
excerpt: "Sequence-to-sequence LSTM model with attention mechanism to transfer Khmer text between linguistic registers (normal to royal) while preserving semantic content."
collection: portfolio
date: 2026-01-02
header:
  teaser: /assets/images/portfolio-khmer-textgen-teaser.jpg
---

## Overview

Khmer is a linguistically rich language with distinct registers — everyday Khmer (សាមញ្ញ) 
and Royal Khmer (រាជស័ព្ទ), a formal register used exclusively when referring to the 
monarchy. These registers differ not just in vocabulary but in grammatical structure, 
where a single normal word may map to multiple royal terms. This project tackles the 
challenge of automatic text style transfer between these registers using deep learning, 
combining unsupervised representation learning with supervised fine-tuning on a 
small labeled dataset.

## The Challenge

Unlike English style transfer tasks, Khmer presents unique difficulties:
- **No word boundaries** — Khmer script is written without spaces, requiring character-level modeling
- **One-to-many mappings** — a single normal Khmer word often corresponds to multiple royal terms
- **Scarce labeled data** — only 793 manually labeled normal–royal sentence pairs available
- **Long-range dependencies** — royal register transformations depend on broader sentence context

## Approach

### Stage 1 — Unsupervised Pre-training
To overcome the labeled data scarcity problem, we first pre-trained a character-level 
LSTM autoencoder on a large unlabeled Khmer corpus collected via web scraping. Two 
models were trained in parallel — one on modern Khmer news text (Model A) and one on 
classical Khmer folktales (Model B) — to compare the effect of pre-training corpus on 
downstream style transfer performance. The encoder learned general Khmer character 
patterns, grammar, and linguistic structure without any labels.

### Stage 2 — Fine-tuning with Attention
The general-text pre-trained encoder was then adapted into a full Seq2Seq style transfer 
model. The encoder weights were initially frozen to preserve learned representations and 
prevent catastrophic forgetting, while a new attention-based LSTM decoder was trained 
on 793 labeled normal–royal sentence pairs. The attention mechanism allowed the decoder 
to dynamically focus on relevant parts of the input at each decoding step — critical for 
handling the complex one-to-many mappings unique to Khmer register transfer.

## My Contributions

This was a 6-person group project. My responsibilities covered the data and model pipeline:

- **Data Collection:** Web scraping of Khmer news and public text corpus for pre-training
- **Data Cleaning:** Zero-width space removal (`\u200b`, `\u200c`, `\u200d`), Latin 
  character filtering, Khmer-specific character normalization to reduce vocabulary noise
- **Vocabulary Engineering:** Built character-level vocabulary mapping (stoi dictionary) 
  with 85-character Khmer alphabet and special tokens (`<SOS>`, `<EOS>`, `<PAD>`, `<UNK>`)
- **Model Development:** Designed and implemented the LSTM encoder-decoder architecture 
  with bidirectional encoding and teacher forcing (ratio 0.5)

## Results

| Model | BLEU Score |
|---|---|
| Folktale pre-trained (baseline) | 9.4% |
| General-text pre-trained | 30.1% |
| Fine-tuned (normal → royal) | up to 0.87 |

The general-text pre-trained model significantly outperformed the folktale baseline 
(30.1% vs 9.4% BLEU), confirming that corpus diversity in pre-training directly 
impacts downstream style transfer quality. Fine-tuning with attention achieved 
sentence-level BLEU scores up to 0.87 on royal Khmer generation.

## Tech Stack

`Python` `PyTorch` `LSTM` `Seq2Seq` `Attention Mechanism` `NLP` `Character-level Tokenization`

## GitHub Repository

[View on GitHub](https://github.com/Povsundra/khmer-tst-web){: .btn .btn--info}

---
**Date:** May 2026 | **Course:** Natural Language Processing | **Type:** Group Project