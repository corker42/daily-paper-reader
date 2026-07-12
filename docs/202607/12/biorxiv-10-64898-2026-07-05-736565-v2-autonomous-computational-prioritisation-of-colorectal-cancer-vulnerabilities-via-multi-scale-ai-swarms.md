---
title: Autonomous computational prioritisation of colorectal cancer vulnerabilities via multi-scale AI swarms
title_zh: 通过多尺度AI群体自主计算优先排序结直肠癌脆弱性
authors: "Baker, C., Ren, T., Rafferty, K., Wang, H., McDade, S."
date: 2026-07-10
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.05.736565v2.full.pdf"
tags: ["query:fundus-mc"]
score: 8.0
evidence: 面向医学诊断（癌症脆弱性）的多智能体AI群体
tldr: 针对AI科学发现中语义推理与复杂生物学的鸿沟，以及现有方法缺乏统计约束和可解释性的问题，提出神经符号框架Octopus，整合本地化多智能体群与正则化预测环境。利用CRISPR依赖数据、XGBoost SHAP归因及体内外模型，自动优先排序结直肠癌脆弱性。自主识别IGF2为5-氟尿嘧啶耐药候选，经Benjamini-Hochberg校正和独立小鼠体内实验验证显著。该工作建立了可验证的本地化自动优先排序范式，桥接假设生成与临床生存预测。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736565-v2/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 921, \"height\": 752, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736565-v2/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1851, \"height\": 678, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736565-v2/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 921, \"height\": 712, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-05-736565-v2/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 906, \"height\": 838, \"label\": \"Figure\"}]"
motivation: 现有多智能体框架缺乏统计约束和临床可解释性，难以可靠翻译多尺度生物发现。
method: 提出Octopus神经符号框架，集成本地化多智能体群、XGBoost SHAP和正则化预测环境，自动优先排序CRISPR及体内外数据。
result: 自主识别IGF2为5-FU耐药脆弱性，经Benjamini-Hochberg校正（q=0.0292）和体内PDX模型验证（p=0.0373）。
conclusion: 框架成功桥接自动假设生成与统计约束的临床生存预测，实现可验证的自动优先排序。
---

## 摘要
自动化科学发现的加速从根本上受到大型语言模型（LLMs）的语义推理与哺乳动物生物学复杂、非线性现实之间认知差距的瓶颈限制。尽管最近的多智能体框架已实现自主假设生成和体外实验分析，但它们通常缺乏多尺度临床转化所需的严格统计约束。此外，尽管算法临床数字孪生成功预测了生物学状态，但它们往往依赖于不透明的潜在空间，为了预测准确性而牺牲了机制可解释性。在这里，我们引入了多尺度自主发现引擎（Octopus），这是一个神经符号框架，它将完全本地化、保护隐私的多智能体群体与正则化预测算法环境相结合。该系统并非止步于孤立的细胞分析，而是自主地根据体外CRISPR依赖性数据（CCLE）优先排序治疗假设，使用XGBoost SHAP向量追踪特征归因级联，并正交地将新出现的脆弱性在计算机中转化以预测体内哺乳动物肿瘤轨迹（PDX）和人类总体生存期（Marisa）。在对结直肠癌转录组进行完全无监督的扫描中，该流程自主地将胰岛素样生长因子2（IGF2）优先排序为对5-氟尿嘧啶耐药的重要候选脆弱性。经过严格的Benjamini-Hochberg错误发现率校正（q = 0.0292，对数秩检验p = 0.0007）后，该发现仍保持显著性，并成功预测了独立小鼠队列中显著的体内肿瘤体积缩小（混合效应LMM p = 0.0373）。通过将智能体假设生成与统计界定的临床生存期相连接，该框架为生物医学发现的自动计算优先排序建立了一个可验证的本地范式。

## Abstract
The acceleration of automated scientific discovery has been fundamentally bottlenecked by the epistemic gap between the semantic reasoning of large language models (LLMs) and the complex, non-linear reality of mammalian biology. While recent multi-agent frameworks have achieved autonomous hypothesis generation and in vitro experimental analysis, they frequently lack the rigorous statistical constraints required for multi-scale clinical translation. Furthermore, while algorithmic clinical digital twins successfully forecast biological states, they often rely on opaque latent spaces, sacrificing mechanistic interpretability for predictive accuracy. Here, we introduce the Multi-Scale Autonomous Discovery Engine (Octopus), a neuro-symbolic framework that unites a fully localised, privacy-preserving multi-agent swarm with regularised predictive algorithmic environments. Rather than stopping at isolated cellular assays, the system autonomously prioritises therapeutic hypotheses against in vitro CRISPR dependency data (CCLE), traces feature attribution cascades using XGBoost SHAP vectors, and orthogonally translates emergent vulnerabilities in silico to predict in vivo mammalian tumour trajectory (PDX) and human overall survival (Marisa). In a fully unsupervised sweep of colorectal cancer transcriptomes, the pipeline autonomously prioritised Insulin-like Growth Factor 2 (IGF2) as a significant candidate vulnerability to 5-Fluorouracil resistance. The discovery maintained significance after rigorous Benjamini-Hochberg false discovery rate correction (q = 0.0292, Log-Rank p = 0.0007) and successfully predicted significant in vivo tumour volume shrinkage in an independent mouse cohort (Mixed-Effects LMM p = 0.0373). By bridging agentic hypothesis generation with statistically bounded clinical survival, this framework establishes a verifiable, local paradigm for the automated computational prioritisation of biomedical discoveries.

---

## 论文详细总结（自动生成）

## 1. 核心问题与整体含义（研究动机和背景）

- **研究动机**：自动化科学发现受限于大型语言模型（LLM）的语义推理与哺乳动物生物学复杂非线性现实之间的认知差距。现有的多智能体框架虽然能自主生成假设和体外实验分析，但缺乏多尺度临床转化所需的严格统计约束；另一方面，临床数字孪生模型预测准确但依赖不透明的潜在空间，牺牲了机制可解释性。
- **背景**：该研究旨在桥接智能体假设生成与统计界定的临床生存预测，建立可验证、本地化的自动优先排序范式，用于高效识别癌症治疗脆弱性。

## 2. 论文提出的方法论

- **核心思想**：提出**Octopus**神经符号框架，将完全本地化、隐私保护的多智能体群体与正则化的算法预测环境（数字孪生）相结合，强制智能体的所有假设通过SHAP特征归因级联进行定量映射，并自动化完成多尺度验证。
- **关键技术细节**：
  - **多智能体群体**：使用4-bit量化的Gemma-4模型，通过llama.cpp后端完全本地执行，并通过严格的有向无环图约束和GPU VRAM刷新技术防止上下文中毒和语义幻觉。
  - **算法世界模型**：基于XGBoost构建高度正则化的预测环境（估计器数量80、最大深度1、学习率0.05、L1=0.5、L2=1.0），用于拟合体外CRISPR依赖性数据（CCLE）以预测5-FU耐药性。
  - **因果SHAP级联**：利用XGBoost的SHAP向量模拟基因敲除（CRISPR in silico），通过递归衰减系数（λ=0.5）和时间步长（t1,t2,t3）模拟信号通路塌陷，生成可解释的机制级联。
  - **多尺度验证流水线**：自动将体外特征归因翻译到体内（PDX小鼠队列）和临床（人类队列），使用Kaplan-Meier生存分析、Cox比例风险回归（校正年龄、分期、MSI、CMS）和线性混合效应模型，并应用Benjamini-Hochberg校正控制多重检验。

## 3. 实验设计

- **数据集**：
  - **体外**：Cancer Cell Line Encyclopedia（CCLE）的转录组表达和GDSC2药物敏感性（AUC）数据，严格筛选肠道细胞系。
  - **体内**：独立Patient-Derived Xenograft（PDX）小鼠队列（N=86），包含治疗前后的肿瘤体积变化。
  - **临床**：Marisa队列（GSE39582），包含585例结直肠癌患者的基因表达和总生存期。
- **基准与对比方法**：论文未明确设置传统基准或对比其他方法。仅通过统计显著性（FDR校正q<0.05）和体内验证证明自主优先排序的有效性。
- **评估指标**：R²（体外预测拟合度）、Log-Rank p值、Cox HR（95% CI）、混合效应模型p值、FDR校正q值。

## 4. 资源与算力

- **论文未明确说明使用的GPU型号、数量和训练时长**。仅提到使用完全本地化的4-bit量化的Gemma-4模型，通过llama.cpp后端执行，并自主刷新GPU VRAM。未提及具体硬件细节或训练计算量。

## 5. 实验数量与充分性

- **实验数量**：主要实验为一次完整的无监督扫描，自主筛选了高变异转录组特征空间（约300个转录本），最终确定IGF2。未进行多轮独立重复或超参数搜索。
- **消融实验**：未涉及消融实验（如移除SHAP级联、去除统计校正、改变正则化参数等）。
- **公平性与客观性**：采用了严格的统计约束（Benjamini-Hochberg校正、Cox多变量分析、混合效应模型）和独立体内验证，增加了可信度。但缺乏与现有AI科学发现系统（如Co-Scientist、AI Scientist）的直接对比，且仅应用于单一癌症类型和单一药物，泛化性待验证。

## 6. 论文的主要结论与发现

- Octopus框架成功自主识别**胰岛素样生长因子2（IGF2）** 作为结直肠癌中对5-氟尿嘧啶（5-FU）敏感性的显著候选脆弱性。
- 在体外XGBoost模型上，IGF2表达是前10预测驱动因子；通过SHAP模拟敲除后，模型预测的耐药性随时间塌陷。
- 在临床Marisa队列中，高IGF2表达与更差的总生存期显著相关（Log-Rank p=0.0007，FDR q=0.0292；多变量Cox HR=1.09，95% CI 1.02-1.16）。
- 在独立PDX小鼠模型中，高IGF2表达组在5-FU治疗后肿瘤体积显著缩小（混合效应LMM p=0.0373）。
- 验证了该框架能桥接语义假设生成与统计学界定的临床生存，实现可验证的多尺度自动优先排序。

## 7. 优点

- **隐私保护**：完全本地化部署，避免将患者数据暴露给外部云API，符合HIPAA/GDPR要求。
- **神经符号结合**：将LLM的语义推理与XGBoost的统计可解释性（SHAP）结合，强制智能体输出基于数学证据。
- **多尺度验证**：自动将体外发现翻译到体内和临床，克服传统AI仅止于体外分析的局限。
- **严格统计约束**：采用FDR校正、多变量Cox、混合效应模型，有效控制假阳性。
- **机制可解释性**：通过SHAP级联动态模拟基因敲除效应，提供机制路径可视化。

## 8. 不足与局限

- **数据局限性**：仅使用bulk转录组数据，未纳入表观遗传、翻译后修饰、肿瘤微环境空间异质性。
- **模拟简化**：in silico CRISPR模拟未真实反映基因组双链断裂后的补偿机制。
- **回顾性验证**：所有验证基于已有回顾性队列，缺乏前瞻性临床试验证据。
- **实验覆盖不足**：未进行消融实验，未与其他自动科学发现系统比较，未测试多种癌症或多种药物。
- **应用限制**：架构高度依赖XGBoost和SHAP，对于更复杂的非线性任务（如多模态病理图像）需进一步扩展。
- **算力说明不足**：未公开具体的GPU型号、数量和训练耗时，影响复现性和效率评估。

（完）
