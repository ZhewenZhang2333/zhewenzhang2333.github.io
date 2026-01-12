---
title: "Image Similarity Model Enhancement (VGG + Attention)"
collection: portfolio
permalink: /portfolio/image-similarity/
excerpt: "Improved VGG with feature extraction + attention to enhance similarity discrimination; +6.8% accuracy gain."
---

## Overview
This project built an image similarity model closer to human visual judgment by comparing **ResNet vs. VGG** feature extraction and improving VGG with additional modules.

## Objective
- Improve similarity discrimination for image ranking/classification
- Increase robustness to minor shifts, noise, and background variation

## Approach
### Architecture Enhancements (before VGG output)
1) **Feature Extraction Layer**
- Extra conv + activation blocks to enrich edges/textures
- Compress redundant information

2) **Attention Layer**
- Channel/spatial attention to focus on similarity-relevant regions
- Reduce background/noise influence

3) **Max Pooling after Attention**
- Keep strongest local responses
- Improve robustness to small translations and scale changes

### Similarity Scoring
- Flatten → FC embedding
- Cosine similarity for pairwise scoring

## Results
- **+6.8% accuracy** on internal validation set
- **Top 20%** in internal Kaggle-style ranking evaluation

## My Role
Project lead: design, implementation, experiments, reporting

## Tech Stack
Python · PyTorch · CNN (VGG/ResNet) · Embedding + Cosine Similarity
