---
title: Untrained Convolutional Neural Networks as Feature Extractors for Structural MRI
title_zh: 未训练卷积神经网络作为结构MRI特征提取器
authors: "Encin, A., Pepe, I. G., Chatelain, Y., Dickie, E., Glatard, T."
date: 2026-06-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730652v1.full.pdf"
tags: ["query:fundus-class"]
score: 6.0
evidence: 未训练CNN作为特征提取器，可用于眼底图像分类
tldr: 从结构MRI中提取特征通常依赖预训练模型，但存在计算成本高、数据泄露等局限。本文提出未训练的卷积神经网络un-CNN，采用多通道输入、多尺度特征聚合和协方差池化。在三个数据集和三个下游任务中，un-CNN特征提取性能与最先进预训练模型相当或更优。未训练CNN规避了训练模型的高资源需求，提升了可重复性和安全性。
source: biorxiv
selection_source: fresh_fetch
motivation: 预训练模型用于结构MRI特征提取存在计算成本高、内存需求大、数据泄露风险和可重复性差等局限。
method: 提出未训练的CNN架构un-CNN，扩展经典3D CNN，包含多通道输入、层次化编码器及协方差池化。
result: 在三个结构MRI数据集和三个下游任务中，un-CNN特征提取性能达到或超过最先进的预训练模型。
conclusion: 未训练的CNN可作为结构MRI特征提取的有效替代方案，降低资源需求并提高可重复性。
---

## 摘要
我们证明，使用未训练的卷积神经网络（un-CNN）从结构MRI中提取的特征，在三个结构MRI数据集和三个下游任务中，其预测性能可与最先进的预训练基础模型相媲美或更优。Un-CNN扩展了经典的3D CNN架构，包含多通道输入、具有多尺度特征聚合的分层编码器以及协方差池化。未训练的CNN规避了训练模型的几个关键限制，包括高计算成本和内存需求、需要分发大型模型权重、数据泄露风险以及可重复性挑战。

## Abstract
We demonstrate that features extracted from structural MRI using un-CNN, an untrained convolutional neural network, achieve predictive performance comparable to or exceeding that of state-of-the-art pretrained foundation models across three structural MRI datasets and three downstream tasks. Un-CNN extends a classical 3D CNN architecture with multi-channel inputs, a hierarchical encoder with multi-scale feature aggregation, and covariance pooling. Untrained CNNs circumvent several key limitations of trained models, including high computational cost and memory requirements, the need to distribute large model weights, risks of data leakage, and challenges in reproducibility.