---
title: Zero-Shot Metabolite Prediction from Gene Expression via Physics-Informed Graph Neural Networks
title_zh: 基于物理信息图神经网络的基因表达零样本代谢物预测
authors: "Novella Rausell, C., Rabelink, T., Mahfouz, A."
date: 2026-07-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735073v1.full.pdf"
tags: ["query:fsrh"]
score: 6.0
evidence: 使用图神经网络进行零样本代谢物预测，类似于少样本学习范式
tldr: "从基因表达预测代谢物浓度对连接调控程序与代谢表型至关重要，但现有方法依赖静态映射且缺乏数据驱动与生化约束，泛化至新代谢物能力有限。本文提出GAZE，一种物理信息图神经网络，通过整合酶表达、EC功能嵌入和ChemBERTa代谢物描述符构建统一代谢图谱，并采用代谢物条件读取器实现零样本预测。在Cancer Atlas数据集上标准交叉验证R²达0.816；留一代谢物零样本测试中，物理信息变体将中位R²亏缺从-0.72降至-0.34，30%未见代谢物获得正R²；在独立肾癌数据集上无需微调即达中位Spearman ρ=0.330。GAZE首次实现无需代谢物特定参数的零样本预测，显著优于现有方法。"
source: biorxiv
selection_source: fresh_fetch
motivation: 现有方法依赖静态酶代谢物映射，缺乏数据驱动与生化约束，无法泛化至新代谢物，亟需结合物理信息的零样本预测模型。
method: 提出GAZE，基于物理信息图神经网络，整合酶表达、EC功能嵌入和ChemBERTa代谢物描述符，通过代谢物条件读取器实现零样本预测。
result: 在三个评估场景中：标准交叉验证R²=0.816；零样本留一代谢物测试中位R²亏缺-0.34；外部验证中位Spearman ρ=0.330，均优于基线。
conclusion: GAZE实现零样本代谢物预测，融合物理信息与图学习，为连接基因表达与代谢表型提供有效工具。
---

## 摘要
从基因表达预测代谢物浓度对于将调控程序与代谢表型联系起来至关重要。先前的方法依赖于静态的酶-代谢物映射，通常忽略数据驱动学习或生化约束，限制了它们泛化到新代谢物的能力。我们提出GAZE（零样本代谢物估计的图注意力网络），这是一种物理信息图神经网络，在统一的代谢图（5,414个节点，16,307条边）中整合了酶表达、酶委员会功能嵌入和ChemBERTa代谢物描述符。代谢物条件读取器利用每种代谢物的SMILES嵌入来查询学习的通路表示，从而实现无需代谢物特定参数的零样本预测。我们在三种场景下评估GAZE：（i）在癌症代谢谱图谱（18,044个基因，180种代谢物，867个细胞系）上进行标准交叉验证，R²=0.816；（ii）在50种留出代谢物上进行留一代谢物（LOMO）零样本评估，其中物理信息变体将中位R²赤字相对于标准GNN基线减半（-0.34 vs. -0.72），30%未见过的代谢物获得正R²；（iii）在独立的透明细胞肾细胞癌组织队列（220个样本）上进行外部验证，GAZE在214种代谢物上无需微调即实现中位斯皮尔曼ρ=0.330。在所有评估设置中，GAZE优于scCellFie、MEBOCOST和UnitedMet。

## Abstract
Predicting metabolite concentrations from gene expression is instrumental for linking regulatory programs to metabolic phenotypes. Prior approaches rely on static enzyme-metabolite mappings and often omit data-driven learning or biochemical constraints, limiting their ability to generalize to new metabolites. We present GAZE (Graph Attention for Zero-shot metabolite Estimation), a physics-informed graph neural network that integrates enzyme expression, Enzyme Commission functional embeddings, and ChemBERTa metabolite descriptors within a unified metabolic graph (5,414 nodes, 16,307 edges). A Metabolite-Conditioned Reader uses each metabolite's SMILES embedding to query learned pathway representations, enabling zero-shot prediction with no metabolite-specific parameters. We evaluate GAZE in three scenarios: (i) standard cross-validation on the Cancer Atlas of Metabolic Profiles (18,044 genes, 180 metabolites, 867 cell lines), achieving R2 = 0.816; (ii) leave-one-metabolite-out (LOMO) zero-shot evaluation across 50 held-out metabolites, where the physics-informed variant halves the median R2 deficit relative to a standard GNN baseline (-0.34 vs. -0.72), with 30% of unseen metabolites achieving positive R2; and (iii) external validation on an independent clear cell renal cell carcinoma tissue cohort (220 samples), where GAZE achieves median Spearman rho = 0.330 across 214 metabolites without fine-tuning. GAZE outperforms scCellFie, MEBOCOST, and UnitedMet across all evaluation settings.