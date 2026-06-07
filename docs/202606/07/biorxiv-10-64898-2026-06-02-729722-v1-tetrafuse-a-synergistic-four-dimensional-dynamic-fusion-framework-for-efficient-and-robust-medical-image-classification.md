---
title: "TetraFuse: A Synergistic Four-Dimensional Dynamic Fusion Framework for Efficient and Robust Medical Image Classification"
title_zh: TetraFuse：一种协同四维动态融合框架，用于高效且鲁棒的医学图像分类
authors: "Gao, Y., Li, J., Xu, J., Li, Q., Li, Z., Shi, Y., ZHao, G., Wu, X., Zhang, Y."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.02.729722v1.full.pdf"
tags: ["query:fundus-class"]
score: 7.0
evidence: 提出通用医学图像分类深度学习框架，可直接用于眼底病分类
tldr: 医学图像分类面临精度与效率的权衡，现有轻量模型因分组卷积导致跨通道信息隔离。提出TetraFuse框架，融合空间、通道、统计、频率四域特征，通过跨通道动态聚合CCDA解决信息隔离，局部方差引导LVGE滤除浅层噪声，高频边界注入HFBI增强深层轮廓。在COVID-19、ISIC 2018、Kvasir数据集上超越SOTA，Tiny模型FLOPs仅0.345G，Kvasir上准确率0.926、AUC 0.994。该框架以极低计算需求实现高精度，适用于资源受限的大规模临床场景。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有轻量模型因分组卷积导致跨通道信息隔离，亟需兼顾诊断精度与计算效率的新方法。
method: TetraFuse融合空间、通道、统计、频率四域，通过CCDA重建全局通道拓扑，LVGE滤除浅层噪声，HFBI注入高频轮廓。
result: "在三个数据集上超越SOTA，Tiny模型FLOPs降低91.53%，Kvasir上准确率0.926、AUC 0.994。"
conclusion: TetraFuse以高表达力与低计算需求，为大规模医学图像分析提供了可扩展的高效方案。
---

## 摘要
医学病理图像的准确鲁棒分类对于计算机辅助诊断至关重要。然而，深度学习模型在高通量临床筛查中的部署面临一个基本挑战：诊断准确性与计算效率之间的权衡。当前的轻量级架构通过分组卷积减少参数复杂度，但常导致跨通道信息隔离和表征能力下降。本文提出TetraFuse，一种新颖框架，系统性地整合了来自四个互补域的特征：空间、通道、统计和频率。TetraFuse引入了新的跨通道动态聚合（CCDA）范式，以可忽略的计算开销重建全局通道拓扑，解决了组间隔离问题。为了平衡感知保真度和效率，我们设计了一种阶段感知局部增强机制：采用局部方差引导增强器（LVGE）滤除浅层背景噪声，而高频边界注入（HFBI）则强化深层病理轮廓，防止空间过度平滑。在COVID-19、ISIC 2018和Kvasir数据集上的实验结果表明，TetraFuse优于最先进（SOTA）方法。值得注意的是，与ResNet50相比，TetraFuse-Tiny的FLOPs减少了91.53%；在Kvasir数据集上，它仅以0.345G FLOPs实现了0.926的准确率和0.994的AUC。通过结合高表征能力和最小计算需求，TetraFuse为大规模医学图像分析（尤其是在资源受限的临床环境中）提供了可扩展的解决方案。

## Abstract
Accurate and robust classification of medical pathology images is pivotal for computer-aided diagnosis. However, the deployment of deep learning models in high-throughput clinical screening faces a fundamental challenge: the trade-off between diagnostic accuracy and computational efficiency. Current lightweight architectures, while reducing parameter complexity through grouped convolutions, often lead to cross-channel information isolation and diminished representational capacity. In this paper, we propose TetraFuse, a novel framework that systematically integrates features from four complementary domains: space, channel, statistics, and frequency. TetraFuse introduces a novel Cross-Channel Dynamic Aggregation (CCDA) paradigm that reconstructs global channel topology with negligible computational overhead, resolving the inter-group isolation issue. To balance perceptual fidelity and efficiency, we design a stage-aware local enhancement mechanism: Local Variance-Guided Enhancer (LVGE) is employed to filter out shallow-stage background noise, while High-Frequency Boundary Injection (HFBI) reinforces deep-stage pathological contours, preventing spatial over-smoothing. Experimental results on the COVID-19, ISIC 2018, and Kvasir datasets confirm that TetraFuse outperforms state-of-the-art (SOTA) methods. Notably, TetraFuse-Tiny achieves a transformative 91.53% reduction in FLOPs compared to ResNet50; on the Kvasir dataset, it achieved an accuracy of 0.926 and an AUC of 0.994 with only 0.345G FLOPs. By combining high representational power with minimal computational demand, TetraFuse offers a scalable solution for large-scale medical image analysis, especially in resource-constrained clinical environments.