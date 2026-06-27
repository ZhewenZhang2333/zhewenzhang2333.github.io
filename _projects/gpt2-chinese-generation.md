---
layout: page
title: 中文 GPT-2 文本生成与中英互译
description: Chinese GPT-2 for text generation and bilingual translation
importance: 1
category: 研究与工程
---

## 项目概述

在之江实验室跨媒体智能研究中心研发实习期间，面向中文语料优化 GPT-2 模型，用于科研文本生成与中英互译。

## 主要工作

- 基于 Wenzhong-GPT2 重新设计中文 tokenizer 与词表结构，以降低序列长度并提高建模效率。
- 将摘要、问答和翻译任务统一为“指令 + 输入 → 输出”格式，开展多任务指令微调。
- 使用梯度裁剪等训练稳定性策略缓解梯度爆炸问题。
- 基于约 10 万条中文样本完成训练与对比评估，并通过 REST API 和命令行工具部署到实验室内部服务器。

## 简历记录结果

- 内部文本生成测试集 BLEU 提升约 **12.5%**。
- Perplexity 下降约 **15.7%**。
- 模型供实验室研究人员用于科研文本生成与中英互译。

**技术栈：** Python, PyTorch, Hugging Face Transformers, GPT-2, REST API
