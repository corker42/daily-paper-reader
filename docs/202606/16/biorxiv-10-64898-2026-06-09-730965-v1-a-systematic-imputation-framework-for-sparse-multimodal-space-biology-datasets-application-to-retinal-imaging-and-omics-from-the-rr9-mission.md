---
title: "A systematic imputation framework for sparse, multimodal space biology datasets: application to retinal imaging and omics from the RR9 mission"
title_zh: 稀疏、多模态空间生物学数据集的系统化插补框架：应用于RR9任务中的视网膜成像和组学数据
authors: "Nagesh, V., Sanders, L., Costes, S. V., Avci, P., Sigit, A., Agarwal, A., Haghighi, A., Batool, A., Karouia, F., Chander, A. M., Schmidt, C. M., Gong, J."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.09.730965v1.full.pdf"
tags: ["query:retina-agent"]
score: 6.0
evidence: 视网膜成像数据插补用于疾病管理
tldr: 针对空间生物学中高成本、低样本量导致的数据稀疏多模态缺失问题，提出一个四阶段系统插补框架。以NASA RR9任务视网膜成像及组学数据为例，通过逻辑回归诊断缺失机制为MAR，评估KNN、MICE-Elastic及混合策略。验证表明MICE-Elastic和混合策略能保留真实信号，但插补显著提升分类性能却恶化聚类结构。该框架为空间生物学家处理稀疏多模态数据提供实用指南，是空间医学数字孪生的基础步骤。
source: biorxiv
selection_source: fresh_fetch
motivation: 空间生物学数据因实验成本高、样本稀缺且多模态，缺失严重，现有插补方法缺乏系统指导。
method: 提出四阶段框架：诊断缺失机制（逻辑回归）、选择策略（KNN、MICE-Elastic、混合）、验证（七项指标）、权衡分析。
result: MICE-Elastic和混合策略保留RNA-seq和TUNEL真实信号；插补提升分类性能但降低聚类一致性，需权衡。
conclusion: 该框架为稀疏多模态数据插补提供系统决策指南，助力空间医学数字孪生发展。
---

## 摘要
缺失数据是空间生物学中的一个基本挑战，高昂的实验成本、有限的样本可用性和组织分配限制导致数据集稀疏、多模态且异质。我们提出了一个系统化的四阶段框架，用于针对这些特征诊断、实施和验证数据插补策略，并展示了其在NASA啮齿动物研究9（RR9）任务中视网膜成像和组学数据上的应用。使用基于逻辑回归的缺失诊断，我们识别出由实验设计约束驱动的随机缺失（MAR）机制，涵盖九种检测方式。我们实施并优化了三种插补策略：K近邻（KNN）、基于链式方程多重插补配合弱弹性网络正则化（MICE-Elastic）以及一种逐列混合策略，并以随机样本插补器作为基线进行评估。通过七个互补指标的验证，包括监督分类、无监督聚类、相关结构保持、掩码值恢复、跨数据集泛化性和置换检验，结果表明MICE-Elastic和混合策略在RNA-seq和TUNEL检测方式中保留了真实的生物信号，而KNN和随机样本插补器尽管达到了可比的交叉验证准确率，却未能做到。一个关键发现是，插补显著提高了监督分类性能，但持续降低了无监督聚类结构，研究人员在应用这些方法之前必须理解这一权衡。该框架为管理稀疏多模态数据集的空间生物学家和数据科学家提供了实用、可操作的指导，并为空间医学数字孪生开发奠定了基础。

## Abstract
Missing data is a fundamental challenge in space biology, where high experimental costs, limited sample availability, and tissue allocation constraints produce datasets that are sparse, multimodal, and heterogeneous. We present a systematic four-stage framework for diagnosing, implementing, and validating data imputation strategies tailored to these characteristics, and demonstrate its application to retinal imaging and omics data from the NASA Rodent Research 9 (RR9) mission. Using logistic regression-based missingness diagnosis, we identify a Missing At Random (MAR) mechanism driven by experimental design constraints across nine assay modalities. We implement and optimize three imputation strategies: K-Nearest Neighbors (KNN), Multiple Imputation by Chained Equations with weak ElasticNet regularization (MICE-Elastic), and a per-column hybrid strategy, evaluated against a random sample imputer baseline. Validation across seven complementary metrics including supervised classification, unsupervised clustering, correlation structure preservation, masked value recovery, cross-dataset generalization, and permutation testing reveals that MICE-Elastic and the Hybrid strategy preserve genuine biological signal in both RNA-seq and TUNEL modalities, while KNN and the random sample imputer do not despite achieving comparable cross-validation accuracy. A critical finding is that imputation substantially improves supervised classification performance while consistently degrading unsupervised clustering structure, a trade-off researchers must understand before applying these methods. This framework provides practical, actionable guidance for space biologists and data scientists managing sparse multimodal datasets, and represents a foundational step toward digital twin development for space medicine.