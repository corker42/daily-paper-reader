---
title: "Orion: Towards Lab Automation with Computer-Using Agents"
title_zh: Orion：迈向基于计算机代理的实验室自动化
authors: "Ma, C., Trinh, L., Bucci, M., Regev, A., Wang, H."
date: 2026-06-16
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.13.732095v1.full.pdf"
tags: ["query:retina-agent"]
score: 8.0
evidence: 用于生物医学图像分析和实验室自动化的AI代理
tldr: "实验室发现依赖于计算工作流，但受限于软件使用和视觉检查。Orion是一个计算机使用AI代理，结合大语言模型与终端、GUI控制和多步推理，实现自动化。它在生物医学检索任务上准确率超90%，学会使用CellProfiler和QuPath工具。在100小时自主探索中生成52份报告，其中22个假说被优先考虑，展示了从图像数据到假说的可审计路线。"
source: biorxiv
selection_source: fresh_fetch
motivation: 计算工作流中软件操作和知识整合依赖人工，自动化程度低。
method: Orion通过大语言模型结合终端执行、GUI控制和自适应多步推理，操作软件和访问网络资源。
result: "在检索任务上准确率>90%，学会CellProfiler和QuPath，100小时生成52份报告，22个假说被专家认可。"
conclusion: 计算机使用AI代理可扩展实验室自动化，实现从实验数据到假说的自主分析。
---

## 摘要
实验室发现越来越依赖于将实验数据与分析、解释和后续假设连接起来的计算工作流。然而，这些工作流仍然受到专用软件劳动密集型使用、通过图形用户界面进行视觉检查以及跨多个来源的知识整合的限制。在这里，我们提出Orion，一种用于生物医学图像分析和解释的计算机使用AI代理，通过自动化实验室工作的计算层向实验室自动化迈进。Orion在共享计算环境中结合了大型语言模型与终端执行、GUI控制和自适应多步推理。它可以检查视觉数据、操作标准科学软件、挖掘网络资源，并进行端到端的分析和解释工作流，无需定制软件集成。在基准测试中，Orion在生物医学数据库和文献检索任务上实现了超过90%的准确率，学会了使用流行工具CellProfiler和QuPath分别对细胞和组织图像进行定量分析，并促进了实验成像数据中的自主发现。在100小时的大规模扰动成像数据集自主探索中，Orion生成了52份研究报告，其中人类科学家审查后优先考虑了22个合理的机制假设。这些结果表明，使用计算机的AI代理可以显著扩展实验室自动化的范围，为从实验成像数据到定量分析、报告和生物学基础假设提供可扩展且可审计的途径。

## Abstract
Laboratory discovery increasingly depends on computational workflows that connect experimental data to analysis, interpretation and follow-up hypotheses. Yet these workflows remain constrained by labor-intensive use of specialized software, visual inspection through graphical user interfaces, and integration of knowledge across multiple sources. Here, we present Orion, a computer-using AI agent for biomedical image analysis and interpretation that moves towards lab automation by automating this computational layer of laboratory work. Orion combines large language models with terminal execution, GUI control and adaptive multi-step reasoning in a shared computing environment. It can inspect visual data, operate standard scientific software, mine web resources and conduct end-to-end analysis and interpretation workflows without requiring bespoke software integrations. Across benchmarks, Orion achieved over 90% accuracy on biomedical database and literature retrieval tasks, learned to use the popular tools CellProfiler and QuPath for quantitative analysis of cellular and tissue images, respectively, and facilitated autonomous discovery in experimental imaging data. In 100 hours of autonomous exploration of a large-scale perturbation imaging dataset, Orion generated 52 research reports, of which human scientist review prioritized 22 plausible mechanistic hypotheses. These results show that computer-using AI agents can substantially expand the reach of laboratory automation, providing a scalable and auditable route from experimental imaging data to quantitative analysis, reports and biologically grounded hypotheses.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **研究动机**：实验室发现越来越依赖连接实验数据与计算分析、解释和后续假设的计算工作流。然而，这些工作流受限于：专用软件的使用需要大量人工操作、通过图形用户界面进行视觉检查、以及跨多个来源的知识整合依赖科学家手动完成，自动化程度极低。
- **整体含义**：本文提出Orion——一种用于生物医学图像分析和解释的“计算机使用AI代理”，通过自动化实验室工作的计算层，向实验室自动化迈出重要一步。Orion能够像人类科学家一样操作标准科学软件、检查视觉数据、挖掘网络资源，并自主完成从实验图像数据到定量分析、报告和生物学假设的端到端流程，无需定制软件集成，有望显著扩展实验室自动化的范围。

## 2. 论文提出的方法论：核心思想、关键技术细节、公式或算法流程
- **核心思想**：将大型语言模型（LLM）与计算机交互能力结合，构建一个能够自主操作计算环境中各类软件和资源的AI代理，特别针对生物医学图像分析场景。
- **关键技术细节**：
  - **架构**：Orion在共享计算环境中结合了大型语言模型（LLM）与**终端执行**（命令行操作）、**GUI控制**（图形用户界面操作，如点击、拖动、输入等）以及**自适应多步推理**（根据任务进展动态调整后续步骤）。
  - **能力**：可以检查视觉数据（如显微镜图像）、操作标准科学软件（如CellProfiler、QuPath）、挖掘网络资源（如数据库、文献检索），并进行端到端的分析和解释工作流。
  - **无需定制集成**：不需要为特定软件编写API或插件，Orion通过模拟人类使用计算机的方式（操作鼠标键盘、执行命令）来完成任务。
- **算法流程**（文字说明）：
  1. 接收用户任务描述（例如“分析这批细胞图像，找出与对照组有显著差异的基因扰动”）。
  2. 代理调用LLM生成多步计划，包括：访问数据、启动软件（如CellProfiler）、设置分析参数、运行定量分析、阅读结果、检索文献数据库、综合信息、撰写研究报告。
  3. 每步执行时，通过终端或GUI操作与计算环境交互；若遇到错误或意外结果，自适应调整计划。
  4. 最终输出包含定量分析结果、图表和解释的研究报告，并记录完整的可审计轨迹。
- **公式**：文中未提及具体数学公式。

## 3. 实验设计：使用了哪些数据集/场景，它的benchmark是什么，对比了哪些方法
- **数据集/场景**：
  - **(1) 生物医学数据库和文献检索任务**：使用标准生物医学数据库（可能包括PubMed、Protein Data Bank等）进行信息检索。
  - **(2) 细胞图像定量分析**：使用CellProfiler对细胞图像进行自动化分析（具体数据集未在摘要中明示，推测为标准公开细胞图像数据集）。
  - **(3) 组织图像定量分析**：使用QuPath对组织图像进行定量分析。
  - **(4) 大规模扰动成像数据集自主探索**：一个大规模扰动（perturbation）成像数据集，包含多种基因或药物扰动的细胞表型图像，进行100小时的自主探索。
- **Benchmark**：
  - 检索任务：以准确率（accuracy）为指标，目标>90%。
  - 工具学习：能否成功学会使用CellProfiler和QuPath进行定量分析（定性评估）。
  - 自主发现：生成的研究报告数量、人类科学家审查后优先考虑的合理机制假设数量。
- **对比方法**：文中未明确提及对比基线方法，主要展示Orion自身的性能，属于探索性研究。

## 4. 资源与算力
- **文中未明确说明**：摘要和元数据中均未提及使用的GPU型号、数量、训练时长等算力信息。仅提到“100小时的大规模扰动成像数据集自主探索”，但这属于推理/运行时长，而非训练时长。训练Orion模型所用的算力资源未知。

## 5. 实验数量与充分性
- **实验数量**：
  - 检索任务：一组基准测试，准确率>90%（具体测试用例数未说明）。
  - 工具学习：CellProfiler和QuPath两个软件各进行学习使用验证，可能各包含若干组图像分析任务。
  - 自主探索：一次性100小时连续运行，生成52份研究报告；其中22个假设被人类科学家优先考虑。
- **充分性分析**：
  - **优点**：自主探索实验规模较大（100小时、52份报告），展示了端到端自动化的可行性；检索任务准确率高，表明基础能力可靠。
  - **不足**：缺乏与其他自动化方法的定量对比实验；消融实验（如去掉LLM、去掉GUI控制、去掉终端执行等）未提及；单一数据集（扰动成像）的自主发现结果是否具有泛化性存疑；工具学习仅验证了两个软件，更广泛的科学软件适用性未知。整体实验设计偏重概念验证，系统性评估不足。

## 6. 论文的主要结论与发现
- Orion在生物医学数据库和文献检索任务上实现了超过90%的准确率。
- 它学会了使用CellProfiler和QuPath分别对细胞和组织图像进行定量分析，无需定制集成。
- 在大规模扰动成像数据集上，经过100小时自主探索，生成了52份研究报告；经人类科学家审查后，其中22个合理的机制假设被优先考虑。
- 结论：计算机使用AI代理可以显著扩展实验室自动化的范围，为从实验成像数据到定量分析、报告和生物学假设提供可扩展且可审计的途径。

## 7. 优点：方法或实验设计上的亮点
- **通用性**：不依赖特定软件API，通过模拟人类操作（终端+GUI）即可与任何标准科学软件交互，大幅降低集成成本。
- **自适应多步推理**：能够动态调整计划，处理错误，适应复杂工作流。
- **端到端自动化**：从原始图像到研究报告的完整链路，包括定量分析、文献挖掘、报告生成，减少人工干预。
- **可审计性**：所有操作步骤可记录和追溯，保证科学可重复性。
- **实验结果有实际价值**：自主探索中生成的假设经人类科学家审查后部分被优先考虑，说明代理能产生有生物学意义的输出。

## 8. 不足与局限
- **实验覆盖有限**：仅验证了两个软件（CellProfiler, QuPath）和一种数据类型（成像数据），对更广泛的生物学实验室场景（如基因序列分析、蛋白质结构预测等）未涉及。
- **缺乏对比基线**：未与现有方法（如传统脚本、其他AI代理如AutoGPT、或其他实验室自动化方案）进行性能对比，难以衡量相对优势。
- **消融实验缺失**：未分析各组件（终端、GUI、多步推理）的贡献，也未测试在不同LLM骨干下的表现。
- **主观评估风险**：假设优先级由人类科学家审查，可能存在主观偏差；22个假设中最终有多少被实验验证未提及。
- **可扩展性挑战**：100小时仅生成52份报告，效率可能受限于LLM推理速度和GUI操作延迟；大规模部署时算力成本未评估。
- **安全与可控性**：AI代理自主操作计算机可能带来意外错误或安全风险（如误删文件、访问禁止网站），文中未讨论防护机制。

（完）
