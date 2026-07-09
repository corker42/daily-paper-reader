---
title: Clinical Trial and Ontology-Derived Positive and Negative Benchmark Datasets for Drug Repurposing Across Rare Diseases
title_zh: 用于罕见疾病药物重定位的临床试验与本体衍生的正负基准数据集
authors: "Ravandi, C. B., Mowrey, W., Chatterjee, A., Khanshan, F., Haddadi, P., Mobarec, J. C., Lambden, S., Eliassi-Rad, T., Ricchiuto, P., Risa, G."
date: 2026-07-08
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732135v2.full.pdf"
tags: ["query:fsrh"]
score: 8.0
evidence: 罕见病药物重定位基准数据集
tldr: 药物重定位研究缺乏标准化、决策导向的基准，难以评估模型跨疾病泛化能力。本研究基于临床试验数据构建正基准IxIDN，包含574种罕见病和5336条边；基于Orphanet罕见病本体构建负基准ORDON，包含793种罕见病和5000条边。两个基准分别捕获实际药物开发决策和生物学距离，为疾病-疾病关联学习提供严格评估框架。所有数据公开可用，支持可复现的模型评价。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-15-732135-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1541, \"height\": 1926, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-15-732135-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 797, \"height\": 895, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-15-732135-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1685, \"height\": 733, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-15-732135-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1699, \"height\": 680, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-06-15-732135-v2/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1711, \"height\": 579, \"label\": \"Figure\"}]"
motivation: 现有基准缺乏真实决策导向，无法有效评估计算模型在药物重定位中的泛化能力和实用性。
method: 从临床试验投影疾病-药物关联构建正基准IxIDN，从罕见病本体层次结构衍生负基准ORDON。
result: IxIDN涵盖574种罕见病、5336条正边；ORDON涵盖793种罕见病、5000条负边。
conclusion: IxIDN和ORDON联合为机制驱动药物重定位提供权威、可复用的决策级基准。
---

## 摘要
评估药物潜在应用是药物开发中的基本挑战。目前缺乏标准化的、面向决策的基准测试，用以检验计算模型能否以反映真实世界制药投资决策的方式跨疾病泛化治疗假设。为弥补这一空白，我们引入了两个互补资源：适应症扩展投资决策网络（IxIDN）和Orphanet罕见病本体负网络（ORDON）。IxIDN是一个源自临床试验的正基准，通过将药物-疾病关联从制药临床试验投射到疾病-疾病网络构建而成；每条边连接那些针对同一药物进入临床试验的疾病对，从而捕捉了已经做出具体适应症扩展决策的案例。当前版本包含574种罕见病和5,336条边。相比之下，ORDON则是一个源于权威Orphanet罕见病本体的严格的、具有生物学意识的负基准。它根据精心策划的层级结构和遗传相关的遗传模式识别出最大分离的疾病对，提供793种罕见病和5,000条边，代表跨治疗领域的高分离阴性候选。IxIDN和ORDON共同实现了从临床试验到疾病本体的严格跨证据泛化，测试疾病-疾病关联学习（DDAL），这是以机制为中心的药物重定位和适应症扩展的核心任务。所有数据均公开可用，并附带详细元数据，支持对透明、决策相关基准上的模型进行可重复评估。

## Abstract
Evaluating the potential applications of a medicine is a fundamental challenge in drug development. There is a lack of standardized, decision-oriented benchmarks that test whether computational models can generalize therapeutic hypotheses across diseases in ways that reflect real-world pharmaceutical investment decision making. To address this gap, we introduce two complementary resources: the Indication Expansion Investment Decision Network (IxIDN) and the Orphanet Rare Disease Ontology Negative-network (ORDON). IxIDN is a clinical-trial-derived positive benchmark constructed by projecting drug-disease associations from pharmaceutical clinical trials into a disease-disease network; each edge connects disease pairs that have entered clinical trials for the same drug, thereby capturing cases when concrete indication-expansion decisions have been made. The current release contains 574 rare diseases and 5,336 edges. In contrast, ORDON serves as a stringent, biology-aware negative benchmark derived from the authoritative Orphanet Rare Disease Ontology. It identifies maximally distant disease pairs according to curated hierarchical structure and genetics-linked inheritance patterns, providing 793 rare diseases and 5,000 edges that represent high-separation negative candidates across therapeutic areas. Together, IxIDN and ORDON enable rigorous cross-evidence generalization from clinical trials to disease ontology, testing for Disease-Disease Association Learning (DDAL), a core task for mechanism-centered drug repurposing and indication expansion. All data are publicly available with detailed metadata, enabling reproducible evaluation of models on transparent, decision-relevant benchmarks.

---

## 论文详细总结（自动生成）

# 论文结构化总结

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：药物重定位（drug repurposing）研究中缺乏标准化、面向决策的基准数据集，现有数据集和评估方式无法真实反映计算模型跨疾病泛化治疗假设的能力。现有知识图谱模型存在“捷径学习”（shortcut learning）问题，仅在相同图谱上训练评估会夸大性能；大语言模型则产生“未接地”的关联（hallucination），它们基于文本统计而非因果机制，容易提出表面合理但生物学上无意义的假设。
- **整体含义**：论文主张将药物重定位从“标签迁移”（label transfer）转变为“机制迁移”（mechanism transfer），并定义“疾病-疾病关联学习”（Disease-Disease Association Learning, DDAL）作为核心任务。为此，作者构建了两个互补的基准：正基准IxIDN（基于真实临床试验投资决策）和负基准ORDON（基于本体层次结构最大分离的疾病对），用以严格评估模型对疾病间可治疗转移性的建模能力。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程

- **核心思想**：疾病之间的相关性应通过“可治疗可转移性”来定义，即两个疾病如果共享可被同一药物靶向的通路或机制，则视为可治疗性相关。基准构建分为两个步骤：
  - **IxIDN（正样本）**：从制药临床试验数据中提取疾病-药物二分图，其中边表示该药物针对该疾病至少进入一项临床试验。然后将二分图通过无权重投影（unweighted projection）转化为疾病-疾病网络：两个疾病之间有边当且仅当存在至少一种药物对两种疾病都进行过临床试验，代表真实世界中的适应症扩展投资决策。当前版本包含574种罕见病、5336条边。
  - **ORDON（负样本）**：利用权威Orphanet罕见病本体（ORDO）的层次结构，计算所有疾病对的最远公共祖先（Lowest Common Ancestor, LCA）距离，选择距离最大的5000对作为严格负样本（处于分布右尾）。这些疾病对在生物学和治疗领域上具有最大分离度，例如小脑性共济失调伴癫痫与ALK阳性大B细胞淋巴瘤（LCA距离为17跳）。当前版本包含793种罕见病、5000条边。
- **关键技术细节**：
  - IxIDN的投影基于“同一药物同时试验两种疾病”的简单规则，无需额外权重。
  - ORDON的LCA距离求和作为分离度指标，从所有疾病对的分布中选取前5000个最远对，以缓解正负样本不平衡。
  - 为公平评估，所有模型在验证时需避免直接使用临床试验数据（对LLM通过提示语约束，对知识图谱模型通过剔除药物节点防止泄露）。

## 3. 实验设计：使用了哪些数据集 / 场景，它的 benchmark 是什么，对比了哪些方法

- **数据集与基准**：主要使用IxIDN-ORDON基准文件（IxIDN_ORDON_benchmark.csv，共10336个样本，5336正+5000负，随机打乱）。此外提供来源文件IxIDN_df.csv和ORDON_df.csv。数据源自Open Targets和Orphanet公共资源。
- **评估场景**：DDAL任务，即对给定的疾病对预测一个连续关联分数（0到1），区分正样本（IxIDN）和负样本（ORDON）。
- **对比方法**：分为四个验证协议：
  1. **LLM推理**：GPT-5.5、Claude Opus 4.7、Gemini 3，使用参数化评分和工具增强的智能体推理。
  2. **迭代智能体检索与推理**：Edison Scientific和Phylo平台（多步检索增强生成）。
  3. **零样本知识图谱基础模型**：TxGNN（经过修改，在训练时剔除药物节点以防信息泄露）。
  4. **间接链接预测**：DeepDR、HeTDR、HGTDR（通过计算每个疾病对预测的前10种药物的交集大小来间接评估）。
- **评估指标**：AUROC、预测分数分布（图4）、Wasserstein距离等。

## 4. 资源与算力

- 论文中未明确说明训练或推理所使用的GPU型号、数量、训练时长等算力资源。作者仅提及使用了AstraZeneca的科学计算平台（SCP），但未提供具体硬件配置。因此，此部分信息缺失。

## 5. 实验数量与充分性

- **实验数量**：共进行了四个协议下的多模型评估：LLM（3种）、agentic AI（2种）、知识图谱基础模型（1种），以及间接链接预测（3种）。此外，还分析了TxGNN在有无数据泄露情况下的性能对比。
- **充分性与客观性**：
  - 实验覆盖了多种主流AI范式（LLM、agentic系统、图神经网络），具有代表性。
  - 对LLM实施了提示语约束，对知识图谱模型实施了节点剔除，尽量降低了数据泄露风险，保证了评估的公平性。
  - 报告了AUROC和分数分布，并提供了Wasserstein距离作为统计分离度。
  - 但缺少消融实验（例如不同LCA截断阈值的影响、不同投影策略的对比）以及对模型超参数敏感性分析。此外，只使用了罕见病数据集，未在非罕见病上验证泛化性。
  - 间接链接预测的实验较为基础（仅展示交集分布，未给出整体分类指标）。
- 总体而言，实验设计较为严谨，但仍有深度拓展空间。

## 6. 论文的主要结论与发现

- IxIDN和ORDON基准能够有效区分真实世界药物重定位决策与生物学无关的疾病对。模型评估显示，即使是先进的AI系统在该基准上也仅能获得中等性能（AUROC约0.7-0.8），远未达到完美分离，表明该基准构成了有意义的挑战。
- 当数据泄露被严格控制时（如TxGNN剔除药物节点），模型性能下降至接近随机，凸显了现有模型对训练数据拓扑结构的依赖，缺乏真正的机制泛化能力。
- 间接链接预测方法（DeepDR、HeTDR、HGTDR）在IxIDN上的药物交集很小，说明这些模型未能有效捕获临床试验隐含的治疗转移信号。
- 因此，IxIDN-ORDON提供了一个有价值的、决策导向的评估框架，有望推动更具泛化能力和机制基础的药物重定位模型的发展。

## 7. 优点：方法或实验设计上的亮点

- **创新性**：首次提出基于临床试验投资决策的正基准和基于本体层次最大距离的负基准，将评估从标签共现转向机制可转移性。
- **严谨性**：对LLM和agentic系统采用盲测（去除标签和ID）、提示语约束，对知识图谱模型采用数据泄露控制，评估流程透明。
- **实用性**：所有数据公开可用，附带详细元数据，便于可复现地评估不同模型。
- **互补性**：正负基准分别从实证决策和生物学先验两个层面定义关联，共同构成全面挑战。
- **可视化与统计验证**：提供了网络度分布、LCA距离分布、AUROC曲线等，使基准特性透明。

## 8. 不足与局限

- **实验覆盖有限**：仅使用罕见病数据集，未在非罕见病或更多样化的疾病类别上验证基准的通用性；负样本仅基于本体结构距离，可能忽略某些实际无关但本体距离近的疾病对。
- **数据泄漏风险依然存在**：尽管采取了限制，但LLM预训练语料可能已包含大量临床试验信息，难以完全消除。
- **缺乏消融实验**：未探讨不同LCA截断值、不同投影策略（如加权投影）对基准难度的影响。
- **间接链接预测评估较为粗糙**：仅展示了药物交集分布，未计算标准分类指标（如AUROC、F1）。
- **资源信息缺失**：未报告计算资源，影响实验的可复现性和性能比较。
- **模型种类有限**：未包含传统机器学习方法（如随机森林、SVM）作为基线，也未包含最新的图基础模型（如BioGPT等）。
- **应用限制**：IxIDN正样本仅反映曾进入临床试验，不一定等于实际有效；ORDON负样本可能忽略某些实际上具有共享机制的疾病对（由于本体结构不完美）。基准应被诠释为治疗假设的证据水平，而非绝对真理。

（完）
