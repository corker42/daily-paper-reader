---
title: Few-Shot Classification of C. elegans Developmental Stages via Explainable Hierarchical Hyperbolic Graph Embeddings
title_zh: 通过可解释分层双曲图嵌入实现秀丽隐杆线虫发育阶段的少样本分类
authors: "Khalid, N., Elliott, L., Obafemi-Ajayi, T., Wunsch, D., Scharf, A."
date: 2026-06-22
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.21.733631v1.full.pdf"
tags: ["query:fundus-mc"]
score: 6.0
evidence: 少样本分类方法，使用双曲嵌入和图结构，可迁移至医学图像分类
tldr: "线虫发育阶段的自动分类对衰老研究和药物筛选至关重要，但面临阶段间形态相似和标注数据稀缺的挑战。本文提出HyperDev框架，利用庞加莱球几何显式编码发育层级结构，结合生物先验，在少样本条件下实现可解释分类。在自建七阶段线虫数据集上，HyperDev达到76.9%-88.3%准确率，嵌入的生物对齐性显著优于ProtoNet等方法。该工作表明双曲几何为生物成像中的可解释少样本学习提供了有效途径。"
source: biorxiv
selection_source: fresh_fetch
motivation: 传统欧几里得方法将发育阶段视为独立类，无法建模层级关系，且标注数据稀缺；需可解释的少样本分类方法。
method: HyperDev采用庞加莱球双曲几何嵌入，结合生物发育先验，通过层级约束在少样本设置下学习阶段关系。
result: "在九种7-way少样本评估中准确率76.9%-88.3%，嵌入生物对齐皮尔逊相关系数0.669（p<0.001），显著优于ProtoNet等。"
conclusion: 双曲几何为生物成像可解释少样本学习提供了原则性方法，可支持高效发育阶段量化。
---

## 摘要
基于显微形态图像的秀丽隐杆线虫发育阶段自动化、准确且快速分类对于衰老研究、药物筛选和疾病建模至关重要。然而，由于阶段间形态相似性以及标注数据有限，该任务仍具有挑战性。在本工作中，我们提出HyperDev，一种双曲少样本学习框架，通过直接在嵌入空间中编码发育层次来解决这些限制，不同于将阶段视为独立类别的传统欧几里得方法。HyperDev采用庞加莱球几何，结合生物学启发的发育先验，自然表示阶段间关系。我们引入了自建的秀丽隐杆线虫数据集，涵盖七个发育阶段（卵、L1-L4、成虫、滞育幼虫），并存在极端类别不平衡（少数类每类6-8个样本）。HyperDev在九个7路少样本评估设置中达到有竞争力的分类准确率（76.9-88.3%），同时提供内在可解释性。学习到的嵌入表现出强生物学对齐（Pearson r = 0.669，p < 0.001），显著优于ProtoNet（r = 0.187）、MatchingNet（r = 0.235）和RelationNet（r = 0.464）。这些结果确立了双曲几何作为生物成像中可解释少样本学习的一种原理性方法，其中理解学习到的表征与预测性能同等重要。

临床相关性：通过从稀疏样本实现可解释、数据高效的发育分期，HyperDev支持改进衰老研究、疾病建模和药物筛选中的表型量化。

## Abstract
Automated, accurate, and fast developmental-stage classification of C. elegans from microscopy-based morphological images is essential for aging research, drug screening, and disease modeling. However, it remains challenging due to morphological similarities between stages and the limited annotated data. In this work, we propose HyperDev, a hyperbolic few-shot learning framework that addresses these limitations by directly encoding developmental hierarchies in the embedding space, unlike conventional Euclidean approaches that treat stages as independent classes. HyperDev uses Poincare ball geometry, combined with a biologically informed developmental prior, to naturally represent stage relationships. We introduce our self-curated C. elegans dataset spanning seven developmental stages (Egg, L1-L4, Adult, Dauer) with extreme class imbalance (6-8 samples per minority class). HyperDev achieves competitive classification accuracy (76.9-88.3%) while providing intrinsic explainability across nine 7-way few-shot evaluation settings. The learned embeddings exhibited strong biological alignment (Pearson r = 0.669, p < 0.001), while significantly outperforming ProtoNet (r = 0.187), MatchingNet (r = 0.235), and RelationNet (r = 0.464). These results establish hyperbolic geometry as a principled approach to explainable few-shot learning in biological imaging, where understanding learned representations is as critical as predictive performance.

Clinical RelevanceBy enabling explainable, data-efficient developmental staging from scarce samples, HyperDev supports improved phenotype quantification for aging research, disease modeling, and drug screening.