---
title: "Chinese GPT-2 Optimization & Instruction Tuning"
collection: portfolio
permalink: /portfolio/gpt2-zh/
excerpt: "Tokenizer redesign + instruction tuning for Chinese GPT-2; improved BLEU and perplexity; deployed via REST API."
---

## Overview
During my internship at **Zhejiang Lab (Cross-media Intelligence Center)**, I worked on optimizing a **Chinese GPT-2** model for high-quality generation and Chinese–English translation.

## Objectives
- Improve Chinese tokenization efficiency for large-scale corpora  
- Enhance controllability and quality via **instruction tuning**  
- Stabilize training and deliver a usable internal service

## Methods
### 1) Tokenizer & Vocabulary Redesign
- Re-designed the Chinese tokenizer and vocabulary to better match Chinese corpus statistics
- Reduced average sequence length and improved modeling efficiency

### 2) Instruction Tuning (Multi-task)
Unified multiple tasks into an **instruction → output** format:
- summarization
- Q&A
- translation

### 3) Training Stabilization
- Applied **gradient clipping** to mitigate gradient explosion
- Improved convergence smoothness and stability

## Data & Setup (Internal)
- ~100k Chinese samples (news, encyclopedia, internal text)
- ~117M parameter scale
- Baseline: original Wenzhong-GPT2 with default tokenizer

## Results
- **BLEU +12.5%**
- **Perplexity −15.7%**
- Better fluency and usability reported by internal users

## Deployment
- Deployed on internal server
- Provided access via **REST API / CLI**
- Used by **10+ researchers** for daily generation and translation tasks

## My Contributions
- Tokenizer/vocabulary redesign
- Instruction-tuning pipeline implementation
- Training stability improvements
- Deployment and internal user support

## Tech Stack
Python · PyTorch · HuggingFace · Docker · REST API · Git
