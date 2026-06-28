---
layout: page
title: 气象科学内容自动识别模型
permalink: /projects/climate-claim-verification/
description: Climate-science claim verification with retrieval and stance detection
importance: 2
category: 研究与工程
role: 项目开发
period: 2023 年 2 月—2023 年 6 月
highlights:
  - 基于 BERT、RoBERTa 与 DPR 完成科学陈述检索和立场识别。
  - 内部验证集 F1 提升约 9.3%，AUC 提升约 7.8%。
---

## 项目概述

针对气象数据与科学陈述文本，构建“支持 / 反对 / 不相关”三分类模型，为科学文本理解与证据检索提供基础能力。

## 主要工作

- 基于 BERT 与 RoBERTa 构建双通道 stance detection 模型，分别编码科学陈述与候选气象文本。
- 使用 Dense Passage Retrieval（DPR）从大规模气象文本库中检索语义相关候选段落。
- 将锋面、等压线、台风等级等领域特征融入表示空间，提高模型对气象领域文本的敏感度。
- 通过数据清洗与权重初始化缓解噪声导致的过拟合问题。

## 简历记录结果

- 在内部气象验证集上，F1 相对基线提升约 **9.3%**。
- AUC 相对基线提升约 **7.8%**。

**技术栈：** Python, BERT, RoBERTa, DPR, PyTorch
