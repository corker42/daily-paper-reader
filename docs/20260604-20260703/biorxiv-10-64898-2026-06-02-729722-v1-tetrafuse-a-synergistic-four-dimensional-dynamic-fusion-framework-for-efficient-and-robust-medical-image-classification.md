---
title: "TetraFuse: A Synergistic Four-Dimensional Dynamic Fusion Framework for Efficient and Robust Medical Image Classification"
title_zh: "TetraFuse: 一种协同四维动态融合框架用于高效鲁棒的医学图像分类"
authors: "Gao, Y., Li, J., Xu, J., Li, Q., Li, Z., Shi, Y., ZHao, G., Wu, X., Zhang, Y."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729722v1.full.pdf"
tags: ["query:fundus-mc"]
score: 6.0
evidence: 适用于眼底的高效医学图像分类框架
tldr: "现有轻量医学图像分类模型因分组卷积导致跨通道信息隔离，精度与效率难以兼顾。TetraFuse融合空间、通道、统计和频率四域特征，通过跨通道动态聚合（CCDA）重构全局通道拓扑，并设计阶段感知机制（LVGE+HFBI）提升特征质量。在三个数据集上表现优异，TetraFuse-Tiny仅用0.345G FLOPs即在Kvasir上达0.926准确率与0.994 AUC，FLOPs较ResNet50降低91.53%。该框架实现了高表示能力与低计算需求的结合，为大规模资源受限场景下的医学图像分析提供了可扩展方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有轻量模型因分组卷积导致跨通道信息隔离，难以兼顾精度与效率，亟需高效融合多域特征的框架。
method: 提出TetraFuse，融合空间、通道、统计和频率四域，通过CCDA重构通道拓扑，利用LVGE滤除浅层噪声，HFBI增强深层轮廓。
result: "在三个数据集上超越SOTA，TetraFuse-Tiny FLOPs较ResNet50降低91.53%，Kvasir上准确率0.926，AUC 0.994。"
conclusion: TetraFuse在保持高精度的同时大幅降低计算量，为资源受限临床环境提供可扩展的医学图像分类方案。
---

## 摘要
医学病理图像的准确与鲁棒分类对于计算机辅助诊断至关重要。然而，深度学习模型在高通量临床筛查中的应用面临一个根本性挑战：诊断准确性与计算效率之间的权衡。当前的轻量级架构通过分组卷积降低参数复杂度，但往往导致跨通道信息隔离和表征能力下降。本文提出TetraFuse，一种新颖的框架，系统性地整合了来自四个互补域的特征：空间、通道、统计和频率。TetraFuse引入了一种新的跨通道动态聚合（CCDA）范式，以可忽略的计算开销重建全局通道拓扑，解决了组间隔离问题。为了平衡感知保真度和效率，我们设计了一种阶段感知的局部增强机制：采用局部方差引导增强器（LVGE）滤除浅层背景噪声，同时通过高频边界注入（HFBI）强化深层病理轮廓，防止空间过度平滑。在COVID-19、ISIC 2018和Kvasir数据集上的实验结果表明，TetraFuse优于现有最先进（SOTA）方法。值得注意的是，与ResNet50相比，TetraFuse-Tiny的FLOPs减少了91.53%；在Kvasir数据集上，它仅以0.345G FLOPs达到了0.926的准确率和0.994的AUC。通过将高表征能力与极低计算需求相结合，TetraFuse为大规模医学图像分析提供了一种可扩展的解决方案，尤其是在资源受限的临床环境中。

## Abstract
Accurate and robust classification of medical pathology images is pivotal for computer-aided diagnosis. However, the deployment of deep learning models in high-throughput clinical screening faces a fundamental challenge: the trade-off between diagnostic accuracy and computational efficiency. Current lightweight architectures, while reducing parameter complexity through grouped convolutions, often lead to cross-channel information isolation and diminished representational capacity. In this paper, we propose TetraFuse, a novel framework that systematically integrates features from four complementary domains: space, channel, statistics, and frequency. TetraFuse introduces a novel Cross-Channel Dynamic Aggregation (CCDA) paradigm that reconstructs global channel topology with negligible computational overhead, resolving the inter-group isolation issue. To balance perceptual fidelity and efficiency, we design a stage-aware local enhancement mechanism: Local Variance-Guided Enhancer (LVGE) is employed to filter out shallow-stage background noise, while High-Frequency Boundary Injection (HFBI) reinforces deep-stage pathological contours, preventing spatial over-smoothing. Experimental results on the COVID-19, ISIC 2018, and Kvasir datasets confirm that TetraFuse outperforms state-of-the-art (SOTA) methods. Notably, TetraFuse-Tiny achieves a transformative 91.53% reduction in FLOPs compared to ResNet50; on the Kvasir dataset, it achieved an accuracy of 0.926 and an AUC of 0.994 with only 0.345G FLOPs. By combining high representational power with minimal computational demand, TetraFuse offers a scalable solution for large-scale medical image analysis, especially in resource-constrained clinical environments.