---
title: Application of class-balancing algorithms to diverse plasma metabolomics datasets using brain tumor as an example
title_zh: 类平衡算法在脑肿瘤等多样化血浆代谢组学数据集中的应用
authors: "Godlewski, A., Solowiej, K., Mojsak, P., Godzien, J., Zelkowska, J., Kretowski, A., Lyson, T., Burdukiewicz, M., Kaminski, K., Ciborowski, M."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.02.735756v1.full.pdf"
tags: ["query:fundus-mc"]
score: 6.0
evidence: 类别平衡算法处理医疗数据中的类别不平衡
tldr: 代谢组学中类别不平衡影响机器学习性能。本研究以脑肿瘤（胶质母细胞瘤、脑膜瘤）与对照血浆代谢组学数据为例，比较SMOTE过采样和RUS欠采样算法。RUS保留原始分布但牺牲代表性，SMOTE引入合成样本改变协方差结构，小样本（n=10）时过拟合风险高，大样本（n=30）时部分恢复。随机森林受益于两类平衡方法，支持向量机性能下降。结果强调选择平衡策略需考虑数据集大小、分析平台和机器学习算法。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735756-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1682, \"height\": 1770, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735756-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1706, \"height\": 1172, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735756-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1615, \"height\": 2057, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735756-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1692, \"height\": 1113, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735756-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1685, \"height\": 841, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-02-735756-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1310, \"height\": 1235, \"label\": \"Figure\"}]"
tables_json: "[{\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-735756-v1/table-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1534, \"height\": 1285, \"label\": \"Table\"}, {\"url\": \"assets/tables/biorxiv/biorxiv-10-64898-2026-07-02-735756-v1/table-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1708, \"height\": 1669, \"label\": \"Table\"}]"
motivation: 代谢组学研究中类别不平衡问题影响统计推断和机器学习性能，需要评估不同平衡算法的适用性。
method: 比较SMOTE过采样和RUS欠采样在LC-MS和GC-MS分析的胶质母细胞瘤、脑膜瘤与对照血浆代谢组学数据集上的效果。
result: RUS保留分布但减少代表性；SMOTE改变协方差结构，小样本过拟合风险增大，大样本部分恢复；随机森林F1分数提升，支持向量机分类性能下降。
conclusion: 选择类别平衡策略应基于数据集大小、分析平台和机器学习算法。
---

## 摘要
类别不平衡仍然是代谢组学研究中的一个挑战，其中生物学和技术变异可能影响统计推断和机器学习性能。类平衡算法通过增加少数类样本或减少多数类样本数量来解决这一问题。本研究评估了过采样和欠采样算法对来自胶质母细胞瘤、脑膜瘤患者及对照组的血浆样本的LC-MS和GC-MS分析所得靶向和非靶向代谢组学数据集的影响。应用合成少数类过采样技术（SMOTE）和随机欠采样（RUS）来平衡数据集，并比较了它们对数据分布、特征间相关性以及机器学习模型性能的影响。RUS保留了原始特征分布，但通过移除多数类样本降低了代表性。相比之下，SMOTE引入了合成样本，改变了协方差结构，增加了过拟合风险，尤其是在小数据集（n=10）中。这些效应在较大组（n=30）中减弱，部分恢复了代谢物之间的相关性。不同类平衡算法下的模型性能存在差异。随机森林分类器受益于两种平衡方法，欠采样通常获得更高的F1分数，而支持向量机模型的分类性能下降。这些发现强调了在代谢组学研究中根据数据集大小、分析平台和机器学习算法选择类平衡策略的重要性。

## Abstract
Class imbalance remains a challenge in metabolomics research, where biological and technical variability can affect statistical inference and machine learning (ML) performance. Class-balancing algorithms address this issue by either increasing minority-class observations or reducing the number of majority-class samples. This study evaluated the impact of oversampling and undersampling algorithms on targeted and untargeted metabolomics datasets derived from LC-MS and GC-MS analyses of plasma samples from patients with glioblastoma, meningioma, and controls. Synthetic Minority Oversampling Technique (SMOTE) and Random Undersampling (RUS) were applied to balance the datasets, and their effects on data distribution, inter-feature correlations, and machine learning model performance were compared. RUS preserved the original feature distributions but reduced representativeness by removing the majority-class samples. In contrast, SMOTE introduced synthetic samples that altered covariance structures, increasing the risk of overfitting, particularly in small datasets (n=10). These effects diminished with larger groups (n=30), partially restoring correlations between metabolites. Model performance varied across the class-balancing algorithms. Random Forest classifiers benefited from both balancing methods, with undersampling often yielding higher F1 scores, whereas Support Vector Machine models showed reduced classification performance. These findings highlight the importance of selecting class-balancing strategies based on dataset size, analytical platform, and ML algorithm in metabolomics studies.