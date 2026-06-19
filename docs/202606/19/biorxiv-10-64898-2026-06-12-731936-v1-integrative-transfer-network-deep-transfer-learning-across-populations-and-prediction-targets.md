---
title: "Integrative Transfer Network: Deep Transfer Learning Across Populations and Prediction Targets"
title_zh: 集成迁移网络：跨群体与预测目标的深度迁移学习
authors: "Gao, Y., Cui, Y."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731936v1.full.pdf"
tags: ["query:fundus-class"]
score: 7.0
evidence: 深度迁移学习方法可用于眼底图像分类的多目标预测
tldr: 大规模临床数据常包含不同人口统计或临床子组以及多个预测目标，现有方法通常独立处理子组差异或多目标预测，缺乏联合利用。本文提出集成迁移网络ITN，一种深度神经网络，通过共享表示和子组特定分支同时跨子组和多个相关结果进行学习。在时间事件分析和分类任务中，ITN通过借用其他子组和结果的信息，一致改善了各子组的预测性能，尤其对数据稀疏的子组提升显著。ITN为异构医疗数据提供了统一学习框架，能够有效提取子组特异性见解，具有广泛适用性。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法独立处理子组差异或多目标预测，未能联合利用跨子组和跨任务信息，限制了子组特定预测性能。
method: 提出ITN深度网络，通过共享表示和子组特定分支，实现跨子组和跨结果的迁移学习，同时捕获共享和子组特异性信息。
result: 在时间事件和分类任务中，ITN相比基线方法在各子组上取得一致更优的预测性能，尤其受益于数据稀疏子组。
conclusion: ITN为异构数据集提供统一学习框架，能有效提升子组特异性预测，适用于子组和预测目标多样化的场景。
---

## 摘要
大规模临床和生物医学数据集日益包含多样化的亚组属性（例如，人口统计学或临床亚组）和多个预测目标。尽管各种机器学习方法可以处理亚组差异或多目标预测，但它们通常独立而非联合地考虑这些方面。为了更有效地捕捉此类复杂数据中的共享信息和亚组特有信息，我们提出了集成迁移网络（ITN），这是一种深度神经网络，旨在同时利用跨亚组和多个相关结果的数据。在广泛的实验中，包括时间-事件任务和分类任务（其中人口统计学亚组和多疾病终点普遍存在），ITN通过借用其他亚组和结果的强度，在亚组特定预测中展示了一致的改进。我们设想ITN作为一个统一的框架，用于从异构数据集中学习，其中亚组特定的洞察至关重要。

## Abstract
Large-scale clinical and biomedical datasets increasingly contain both diverse subgroup attributes (e.g., demographic or clinical subgroups) and multiple prediction targets. Although various machine learning approaches can address subgroup differences or multi-target prediction, they often consider these aspects independently rather than jointly. To more effectively capture the shared and subgroup-specific information in such complex datasets, we propose the Integrative Transfer Network (ITN), a deep neural network designed to leverage data across subgroups and multiple related outcomes simultaneously. In extensive experiments, including time-to-event and classification tasks where demographic subgroups and multiple disease end-points are prevalent, ITN demonstrates consistent improvements in subgroup-specific prediction by borrowing strength from other subgroups and outcomes. We envision ITN as a unified frame-work for learning from heterogeneous datasets where subgroup-specific insights are critical.