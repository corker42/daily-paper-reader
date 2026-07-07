---
title: "FAMUS: A Few-Shot Learning Framework for Large-Scale Protein Annotation"
title_zh: FAMUS：一种面向大规模蛋白质注释的少样本学习框架
authors: "Shur, G., Burstein, D."
date: 2026-07-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.03.08.710366v2.full.pdf"
tags: ["query:fsrh"]
score: 9.0
evidence: 用于蛋白质注释的少样本学习框架
tldr: 现有基因功能注释工具依赖单一序列比对，难以处理欠表示家族且阈值设置不稳健。为此提出FAMUS框架，基于监督对比学习，将查询序列与所有profile HMM的相似度向量映射到紧凑空间，并利用未标注序列作为负样本。实验表明，FAMUS在KEGG Orthology和PANTHER家族注释上优于KofamScan和InterProScan。该框架是首个基于对比学习的模块化注释工具，提供四个预训练模型，支持用户自定义数据库，可轻松集成到基因组分析流程中。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有自动注释工具依赖单个最相似序列且阈值设定困难，对稀疏家族标注不准确。
method: 采用监督对比学习，将查询序列与所有profile HMM的相似度向量映射至紧凑空间，并纳入未标注序列作为负样本。
result: 在KEGG Orthology和PANTHER家族注释中超越KofamScan和InterProScan，构建了四个高精度模型。
conclusion: FAMUS是首个基于对比学习的模块化注释框架，支持自定义数据库，可实现大规模准确注释。
---

## 摘要
预测基因功能是基因组和宏基因组数据分析中关键且具有挑战性的步骤。当前的自动注释工具通常依赖于查询数据库中最相似的单一序列，并且难以稳健地设置注释的命中阈值。每个注释对应的蛋白质稀疏性使得难以自信地分配低代表性家族的基因功能。在此，我们提出了一种用于功能注释的对比学习框架。FAMUS（使用监督对比学习的功能注释方法）将查询序列与一系列谱隐马尔可夫模型进行比较，并将相似性分数转换到一个紧凑的向量空间中，该空间最小化来自同一家族的蛋白质之间的距离。查询与所有谱的相似性分数被用于其表示，而不是仅考虑排名最高的命中。未注释的序列在训练期间被作为负样本纳入，使得能够稳健地检测超出参考数据库范围的蛋白质，而无需用户定义阈值。使用这种方法，FAMUS在KEGG Orthology注释上优于KEGG原生的KofamScan，在PANTHER家族注释上优于InterPro的InterProScan。因此，我们使用来自KEGG Orthology、InterPro家族、OrthoDB和EggNOG数据库的蛋白质家族创建了四个蛋白质注释模型。所有四个模型均以conda包形式提供，并通过我们用户友好的Web服务器提供，允许用户注释大规模数据集。FAMUS是第一个基于对比学习的全面且模块化的注释框架。它同时支持预定义数据库和用户自定义数据库以实现定制化注释，并且可以轻松集成到任何基因组和宏基因组分析流程中，以促进准确的大规模功能注释。

## Abstract
Predicting gene function is a pivotal and challenging step in genomic and metagenomic data analysis. Current automatic annotation tools typically rely on the single most similar sequence from the query database and struggle to robustly set hit thresholds for annotation. The sparsity of proteins per annotation makes it challenging to confidently assign gene function for underrepresented families. Here, we present a contrastive learning framework for functional annotation. FAMUS (Functional Annotation Method Using Supervised contrastive learning) compares query sequences to a full array of profile Hidden Markov Models and transforms the similarity scores into a condensed vector space that minimizes the distance of proteins from the same family. The similarity scores of a query to all profiles are used for its representation instead of considering only the top-ranking hit. Unannotated sequences are incorporated as negative examples during training, enabling robust detection of proteins that fall outside the scope of the reference database without requiring a user-defined threshold. Using this approach, FAMUS outperformed KEGGs native KofamScan for KEGG Orthology annotation and InterPros InterProScan for PANTHER family annotation. We thus created four protein annotation models using protein families from the KEGG Orthology, InterPro family, OrthoDB, and EggNOG databases. All four models are available as a conda package and via our user-friendly web server, allowing users to annotate large-scale datasets. FAMUS is the first comprehensive and modular annotation framework based on contrastive learning. It supports both pre-defined and user-specific databases for tailored annotation, and can be easily integrated into any genomic and metagenomic analysis pipeline to facilitate accurate, large-scale functional annotation.

---

## 论文详细总结（自动生成）

# FAMUS：一种面向大规模蛋白质注释的少样本学习框架 —— 论文详细总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：现有基因功能自动注释工具（如基于序列相似性的BLAST、基于谱隐马尔可夫模型（pHMM）的KofamScan、InterProScan等）存在三大局限：
  - **最优命中依赖**：仅使用最高相似性得分，未充分利用全部分数信息，导致对远源同源物和模糊情况注释不佳。
  - **低特异性pHMM**：对于序列多样性高、簇内相似度低的蛋白家族，pHMM特异性差，易产生高假阳性或低检出率。
  - **阈值设定困难**：最优截断值因家族而异，手动调整不具扩展性，难以稳健区分“已知”与“未知”蛋白。
- **研究背景**：大型数据库（KEGG、InterPro、EggNOG、OrthoDB）中大量家族仅有稀疏样本（如KEGG中20%的KO家族≤100条序列），传统多分类器训练困难。受计算机视觉中对比学习（尤其是Siamese网络、Triplet网络、Supervised Contrastive Learning, SupCon）启发，可将分类转化为比较任务，适用于少样本场景。

## 2. 论文提出的方法论

### 核心思想
- 采用监督对比学习（SupCon），将查询序列与**所有**子家族pHMM的相似性得分向量（而非仅最优命中）作为输入，通过神经网络投影到低维嵌入空间，使同家族蛋白在该空间中聚集，不同家族及未标注序列被推开。
- 在训练中引入**未标注序列作为负样本**，实现无需用户定义阈值即可检测超出参考数据库范围的蛋白（即OOD检测）。
- 支持**多数据库模块化**，可预定义或用户自定义数据库。

### 关键技术细节
1. **数据预处理与子家族生成**：
   - 对每个蛋白家族去冗余（mmseqs2 cluster, 0.8覆盖, 90%序列同一性）。
   - 对代表性序列进行二次聚类（mmseqs2 cluster, 0.5覆盖）生成子家族，覆盖80%的代表性序列，剩余序列通过搜索分配至已有pHMM。
   - 对少于6条序列的子家族使用hmmemit人工扩充。
   - 每个子家族构建pHMM（MAFFT多序列比对 + hmmbuild）。

2. **特征向量构建**：
   - 训练集采样（KEGG中每个子家族最多60条；未标注序列与标注序列数量平衡）。
   - 使用hmmsearch对所有子家族pHMM进行搜索，取最佳域位得分（best domain bit score），得到N×M矩阵（N为序列数，M为子家族数），作为网络输入。
   - **避免数据泄露**：采用KofamKoala的三折策略，每个子家族分成三等份，用其中两份建pHMM，对第三份评分，重复三次。

3. **网络架构**：
   - 输入层大小 = M（子家族数，KEGG模型为38,628），三个隐藏层（各320神经元，SiLU激活），输出层320维，L2归一化至单位超球面。
   - 损失函数：SupCon（sum-inside-the-log），使用余弦相似度，温度参数τ。
   - 批次构建：随机采样16个标签，每个标签最多8个样本，另加64个未标注样本，共96-192样本。
   - 优化器：Adam（无权重衰减，无dropout），学习率1e-4，每15个epoch减半。

4. **推理与OOD检测**：
   - 将所有训练序列通过模型得到嵌入。
   - 输入查询序列获得嵌入后，计算与所有训练嵌入的欧氏距离。
   - 最近邻若为标注样本且距离小于全局阈值（由三折交叉验证选择最大化加权F1的平均阈值），则分配该家族标签；否则标记为“unknown”。

### 算法流程（文字说明）
1. 输入：蛋白家族序列集 → 去冗余 → 子家族聚类 → pHMM构建。
2. 训练：采样序列 → hmmsearch获得位分向量 → 训练SupCon网络，使用包含未标注样本的批次。
3. 推理：查询序列 → hmmsearch → 网络嵌入 → 最近邻距离与阈值比较 → 输出标注或“unknown”。

## 3. 实验设计

### 数据集/场景
- **主要评估**：KEGG Orthology（KO）和PANTHER蛋白家族。使用时间分割评估：2021年5月训练，2023年5月新增序列（8.2M去冗余序列，其中3.49M有KO标签，4.71M无标签）作为测试集；PANTHER版本18训练，版本19测试。
- **额外模型**：InterPro、OrthoDB（仅选≥200条序列的家族）、EggNOG（COG+KOG+arCOG）；这些数据库使用常规随机分割（80%训练，20%测试）。
- **未知序列比例**：5%、25%、50%、75%、95%五个水平，每个水平随机采样5次共5,000条序列。

### Benchmark与对比方法
- **FAMUS**：综合版（高分辨率，使用子家族）、轻量版（每个家族仅一个pHMM）。
- **基线**：最佳pHMM命中分类器（最高位分且通过阈值，否则“unknown”）。
- **现有工具**：KofamScan（KEGG）、InterProScan（PANTHER）。对于KofamScan，预测为位分最高且通过显著性阈值的KO；对于InterProScan，预测为E值最低的PANTHER家族。

### 评估指标
- **加权F1分数**（主指标，考虑类别不平衡）
- **微F1分数**（补充）
- **精确率**（仅对明确标注的序列，包含未标注序列视为假阳性）

## 4. 资源与算力

- **硬件**：AMD EPYC 7443 24核处理器，RTX A6000 GPU（10,752 CUDA核心），24虚拟CPU，Rocky Linux 9.5。
- **运行时间**：主瓶颈为pHMM搜索阶段。综合模型因pHMM数量多（如KEGG 38,627个子家族）较慢，轻量模型（如KEGG 24,784个家族）与KofamScan相当或更快；GPU加速提升有限（模型参数少）。
- **训练时间**：论文未明确给出总训练时长，仅提及学习率衰减策略（每15epoch减半），未说明epoch总数或训练时长。

## 5. 实验数量与充分性

- **多数据库验证**：在KEGG、PANTHER、InterPro、OrthoDB、EggNOG五个数据库上训练模型，但主要性能对比仅针对KEGG和PANTHER。
- **多未知比例**：5个不同未知比例（5%-95%） × 5次随机采样，共25组评估，统计稳定。
- **多指标**：加权F1、微F1、精确率三个角度。
- **消融/比较**：FAMUS综合版 vs 轻量版 vs 基线HMM vs 现有工具。无针对对比损失函数或网络结构的消融实验。
- **公平性**：使用时间分割避免数据泄露（KEGG、PANTHER）；对于其他数据库使用随机分割。确保训练与测试序列无90%以上相似性（mmseqs去冗余）。但未讨论KofamScan/InterProScan版本时间对齐问题（KofamScan使用2021年6月profile，与FAMUS训练数据时间匹配）。

**充分性评价**：实验设计合理，对比全面，但缺失消融实验（如不使用子家族、不使用未标注负样本、不同网络深度等）来验证各组件贡献。此外，仅对KEGG和PANTHER做详细性能对比，其他数据库仅提供模型未做性能分析。

## 6. 论文的主要结论与发现

1. **性能优势**：FAMUS在KEGG和PANTHER注释上整体优于KofamScan和InterProScan，尤其是在高比例未知序列场景（50%-95%，更接近实际宏基因组）时表现更佳。
2. **高精确率**：FAMUS在精确率上与KofamScan相当，优于InterProScan，表明其标注可靠，但可能以一定召回率损失为代价（保守策略）。
3. **OOD检测能力**：通过将未标注序列作为负样本，FAMUS无需用户阈值即可有效识别不在参考数据库中的蛋白，降低假阳性。
4. **少样本学习有效**：对比学习框架能处理稀疏家族（少样本），无需大量正样本。
5. **模块化与可用性**：提供四个预训练模型（KEGG、InterPro、OrthoDB、EggNOG），支持conda安装和Web服务器，支持自定义数据库，易于集成。

## 7. 优点

- **创新性**：首次将监督对比学习应用于通用大规模蛋白质功能注释，克服传统pHMM方法的三大局限。
- **充分利用全谱信息**：输入全pHMM得分向量，而非单一最佳命中，提升分辨能力。
- **自动OOD检测**：无需人工阈值，利用未标注负样本训练，更适合真实宏基因组数据。
- **少样本友好**：对比学习的组合采样性质使模型能从稀疏家族中学习。
- **模块化设计**：支持多种数据库和用户自定义，提供轻量与综合两种模式，平衡速度与精度。
- **可复现与易用**：代码、pHMM、模型参数开源，提供conda包和Web服务器。
- **严格数据泄漏防范**：三折策略确保训练序列不参与自身pHMM构建。

## 8. 不足与局限

- **训练时间未报告**：未给出完整训练所需的epoch数和耗时，影响复现与资源评估。
- **消融实验缺失**：未量化子家族聚类、未标注负样本、网络深度等各组件的影响。
- **数据库覆盖不完全**：InterPro仅用家族（排除超家族），OrthoDB仅用≥200条序列的组，EggNOG仅用COG/KOG/arCOG，可能遗漏部分功能信息。
- **性能基准局限**：主要对比仅针对KEGG和PANTHER，其他数据库未做详细评估；且对比方法仅KofamScan和InterProScan，未与近期基于语言模型的方法（如CLEAN、ATGO）比较（但提及它们预处理开销大）。
- **通用性局限**：依赖pHMM搜索作为预处理，对于全新蛋白（无同源域）可能缺乏有效信号。
- **全局阈值设定**：使用单一全局阈值，可能不适用于所有家族，家族特异性阈值可能更优。
- **商业数据库限制**：KEGG数据需从FTP获取，非完全公开，可能影响第三方复现。

（完）
