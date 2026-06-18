---
title: "Integrative Transfer Network: Deep Transfer Learning Across Populations and Prediction Targets"
title_zh: 集成迁移网络：跨群体与预测目标的深度迁移学习
authors: "Gao, Y., Cui, Y."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.12.731936v1.full.pdf"
tags: ["query:fundus-class"]
score: 6.0
evidence: 跨人群和多个预测目标的深度迁移学习方法
tldr: 大型临床数据常含亚组差异和多目标预测，现有方法常单独处理。本文提出ITN深度神经网络，同时跨亚组和多个结果进行迁移学习。在时间事件和分类任务中，ITN通过借用其他亚组和结果信息，显著提升亚组特定预测性能。ITN为异质数据集提供统一学习框架，在需要亚组洞察的场景中具有重要价值。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法单独处理亚组差异或多目标预测，未联合利用两者信息，导致亚组特定预测能力受限。
method: 提出Integrative Transfer Network (ITN)，通过深度迁移学习同时跨亚组和多个预测目标共享与特定信息。
result: 在时间事件和分类任务中，ITN一致改善亚组特定预测性能，通过借用其他亚组和结果信息增强表现。
conclusion: ITN作为统一框架，有效从含亚组属性和多目标的异质数据中学习，提升亚组层面的预测洞察力。
---

## 摘要
大规模临床和生物医学数据集日益包含多样化的子群体属性（如人口统计学或临床子群体）和多个预测目标。尽管各种机器学习方法可以处理子群体差异或多目标预测，但它们通常独立而非联合地考虑这些方面。为了更有效地捕捉此类复杂数据集中的共享信息和子群体特有信息，我们提出了集成迁移网络（ITN），这是一种深度神经网络，旨在同时利用跨子群体和多个相关结果的数据。在广泛实验中，包括以人口统计学子群体和多种疾病终点为特征的时间事件预测和分类任务，ITN通过从其他子群体和结果中借用强度，展示了在子群体特定预测方面的一致改进。我们将ITN视为一个从异质数据集中学习的统一框架，其中子群体特定的见解至关重要。

## Abstract
Large-scale clinical and biomedical datasets increasingly contain both diverse subgroup attributes (e.g., demographic or clinical subgroups) and multiple prediction targets. Although various machine learning approaches can address subgroup differences or multi-target prediction, they often consider these aspects independently rather than jointly. To more effectively capture the shared and subgroup-specific information in such complex datasets, we propose the Integrative Transfer Network (ITN), a deep neural network designed to leverage data across subgroups and multiple related outcomes simultaneously. In extensive experiments, including time-to-event and classification tasks where demographic subgroups and multiple disease end-points are prevalent, ITN demonstrates consistent improvements in subgroup-specific prediction by borrowing strength from other subgroups and outcomes. We envision ITN as a unified frame-work for learning from heterogeneous datasets where subgroup-specific insights are critical.