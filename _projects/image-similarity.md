---
layout: page
title: 图像相似度对比模型
description: Image similarity learning with VGG and attention mechanisms
importance: 3
category: 研究与工程
---

## 项目概述

构建接近人类视觉判断的图像相似度模型，对比 ResNet 与 VGG 的特征提取能力，并改进 VGG 输出层前的网络结构。

[查看代码仓库](https://github.com/ZhewenZhang2333/deep-learning-model)

## 主要工作

- 增加特征提取层，以压缩冗余信息并强化边缘、纹理等视觉模式。
- 引入通道或空间注意力，根据上下文为不同视觉特征分配权重。
- 通过最大池化增强模型对平移和尺度变化的鲁棒性。
- 将特征映射到 embedding 空间，并使用余弦相似度计算图像相似度。

## 简历记录结果

- 改进模型在内部验证集上的准确率较原始 VGG 提升约 **6.8%**。
- 内部 Kaggle-ranking 评测进入 **Top 20%**。

**技术栈：** Python, PyTorch, VGG, ResNet, Attention
