---
title: "Scientific Stance Detection + DPR Retrieval (Meteorology Domain)"
collection: portfolio
permalink: /portfolio/stance-detection/
excerpt: "Dual-encoder BERT+RoBERTa stance detection with DPR retrieval and domain adaptation; F1 +9.3%, AUC +7.8%."
---

## Overview
Built an NLP system to classify whether meteorology evidence text **supports / opposes / is unrelated** to scientific claims, with retrieval support for evidence selection.

## Task
Given: **(scientific claim, meteorology paragraph)**  
Predict stance: **support / oppose / unrelated**

## Model
### Dual-Encoder Fusion
- Encoder 1: **BERT**
- Encoder 2: **RoBERTa**
- Concatenate representations → FC classifier

Motivation: capture complementary local/global semantics from different encoders.

### DPR Retrieval Integration
- Reproduced **Dense Passage Retrieval (DPR)**
- Retrieved candidate evidence paragraphs from a large corpus
- Built positive/negative samples for training/evaluation

### Domain Feature Adaptation
- Injected embeddings for meteorology terminology (fronts, isobars, typhoon levels, etc.)
- Improved sensitivity to domain-specific language

## Results
- **F1 +9.3%**
- **AUC +7.8%**
- Better robustness after data cleaning and improved initialization

## My Contributions
- Dual-encoder model design and training
- DPR reproduction and retrieval pipeline
- Domain adaptation features
- Evaluation + reporting

## Tech Stack
Python · PyTorch · Transformers (BERT/RoBERTa) · DPR · SQL/Corpus tooling
