---
title: Automated Retinal Dysplasia Segmentation in Mouse Optical Coherence Tomography Scans Using a UNet-Based model
title_zh: 基于UNet模型的小鼠光学相干断层扫描中视网膜发育不良的自动分割
authors: "Mikroulis, A., Raishbrook, M. J., Palkova, M., Lindovsky, J., Prochazka, J., Sedlacek, R., Novosadova, V., Novak, D."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730047v1.full.pdf"
tags: ["query:retina-agent"]
score: 9.0
evidence: 小鼠OCT中视网膜发育不良的自动分割
tldr: "OCT是视网膜病变研究的关键成像技术，但手动标注耗时且主观。本文提出基于UNet的神经网络模型，自动分割小鼠OCT中的视网膜发育不良病灶。模型在205个标注堆栈上训练，40个堆栈上验证，F1>0.95，与专家一致性Dice>0.8。最终集成到跨平台应用OCTOPUS，支持批量处理、手动编辑和纵向追踪，有助于标准化实验室间评估。"
source: biorxiv
selection_source: fresh_fetch
motivation: 手动标注小鼠OCT病理区域耗时且存在评分者间变异，需要自动化解法以提升效率和一致性。
method: 基于UNet架构的神经网络模型，在205个专家标注的OCT堆栈上训练，并集成到跨平台应用OCTOPUS。
result: "模型在40个未见堆栈上F1>0.95，与专家标注的Dice中位数>0.8，实现高精度自动化分割。"
conclusion: 该开源工具可促进视网膜疾病小鼠模型的高通量表型分析和标准化OCT评估。
---

## 摘要
光学相干断层扫描（OCT）是临床前视网膜病变研究中领先的无创成像技术。然而，在小鼠OCT扫描中手动注释病理过程既费时又易受评分者间变异性的影响。为解决这些问题，我们开发了一种基于神经网络的模型，用于自动注释小鼠OCT扫描中的视网膜发育不良。该模型在205个专家注释的OCT堆栈上训练，并在40个未见过的堆栈上进行验证，其中一部分还进行了额外的专家注释比较。模型能以高精度（F1分数 > 0.95）检测病理，并与专家保持高度一致性（中位Dice分数 > 0.8）。我们将该模型集成到一个跨平台应用程序（'OCTOPUS'）中，该程序包含批处理、自动注释、手动注释编辑、基于眼底图像的病理区域估计的定量纵向跟踪，以及可导出为CSV和SVG格式的结果。我们的开源工具旨在促进和标准化实验室间的OCT评估，以用于视网膜疾病小鼠模型的高效临床前筛选和高通量表型分析。

## Abstract
Optical coherence tomography (OCT) is the state-of-the-art non-invasive imaging technique for preclinical retinopathy studies. However, manual pathology annotations in mouse OCT scans are labour-intensive and susceptible to inter-rater variability. To alleviate these issues, we developed a neural network-based model for automated annotation of retinal dysplasia in mouse OCT scans. Our model was trained on 205 expert-annotated OCT stacks and validated on 40 unseen stacks with additional expert annotation comparisons in a subset of them. The model detects pathologies with high accuracy (F1-score > 0.95) and consistency with experts (median Dice score > 0.8). We integrated the model into a cross-platform app ('OCTOPUS') that includes batch processing, automated annotation, manual annotation editing, and quantitative longitudinal tracking with pathological area estimation on the fundus image, and exportable results in CSV and SVG formats. Our open-source tool aims to facilitate and standardise OCT assessments between laboratories for efficient preclinical screening and high-throughput phenotyping in mouse models of retinal disease.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：小鼠视网膜疾病研究中，光学相干断层扫描（OCT）是关键的成像手段，但手动标注OCT图像中的病理区域（如视网膜发育不良）既耗时又存在评分者间变异性，限制了高通量表型分析和实验室间的标准化比较。
- **研究动机**：开发一种自动化的、准确的、可重复的病理分割方法，以替代人工标注，提高效率并降低主观偏差。
- **整体含义**：本研究旨在通过深度学习模型实现小鼠OCT扫描中视网膜发育不良的自动分割，并集成到跨平台工具中，促进临床前视网膜疾病研究的标准化和高通量筛选。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：采用基于UNet架构的神经网络模型，对小鼠OCT图像中的视网膜发育不良区域进行像素级分割。
- **关键技术细节**：
  - **数据准备**：使用205个专家标注的OCT堆栈作为训练集，40个未见过堆栈作为验证集。
  - **模型架构**：UNet（未说明具体变体如残差连接、注意力机制等，文中仅称“基于UNet的模型”）。
  - **训练细节**：未提及损失函数、优化器、学习率、数据增强等具体设置。
  - **集成应用**：训练好的模型被嵌入跨平台应用程序“OCTOPUS”，支持批处理、自动分割、手动编辑、纵向追踪以及眼底图像上病理面积估算，结果可导出为CSV和SVG格式。

### 3. 实验设计

- **数据集**：
  - 训练集：205个专家标注的OCT堆栈（具体数量、来源物种、病理类型未详细说明，仅指“视网膜发育不良”）。
  - 验证集：40个未见过堆栈（其中一部分还进行了额外专家标注以进行一致性比较）。
- **Benchmark**：未说明与现有方法（如其他分割网络或传统分割算法）的对比，仅与专家标注进行一致性评估。
- **评价指标**：
  - 模型检测精度：F1分数 > 0.95。
  - 与专家一致性：中位Dice分数 > 0.8。
- **缺失信息**：未提及交叉验证、独立测试集或不同病理严重程度的分层验证。

### 4. 资源与算力

- **文中未明确说明**：未提及使用的GPU型号、数量、训练时长、内存消耗等算力信息。仅说明模型基于UNet架构，可能为轻量级网络，但具体资源需求未知。

### 5. 实验数量与充分性

- **实验数量**：仅一组训练/验证实验（205训练，40验证），未进行消融实验、超参数对比或不同模型架构的比较。
- **充分性与公平性**：
  - **优点**：验证集数量（40个堆栈）相对合理，且包含额外专家标注以验证一致性。
  - **不足**：缺乏与现有基线模型（如U-Net++、DeepLab、nnU-Net等）的对比；未统计不同噪声、伪影或病理变异的场景；未做交叉验证；未提供错误分析（如假阳性/假阴性的解剖分布）。因此实验设计的充分性有限，但作为概念验证可行。

### 6. 论文的主要结论与发现

- **主要结论**：基于UNet的模型能够以高精度（F1 > 0.95）和专家一致性（Dice > 0.8）自动分割小鼠OCT扫描中的视网膜发育不良。该模型集成到OCTOPUS应用中，为实验室间标准化OCT评估提供了开源工具，有助于小鼠模型的高通量表型分析。

### 7. 优点

- **实用性**：模型集成到跨平台应用（OCTOPUS），具备批处理、手动编辑、纵向追踪等功能，直接面向用户需求。
- **性能可靠**：与专家的一致性高（Dice > 0.8），且F1 > 0.95表明检测能力出色。
- **开源与标准化潜力**：工具开源，有利于不同实验室之间的结果对比和重复使用。
- **选题价值**：解决了小鼠视网膜疾病研究中手动标注的瓶颈问题，具有明确的临床前应用价值。

### 8. 不足与局限

- **实验覆盖不足**：仅用单一数据集（可能来自同一实验室或同一种小鼠模型），未在不同品系、不同严重程度或不同成像设备上验证泛化性。
- **缺乏对比实验**：未与其他分割方法（如经典图像处理、其他深度学习架构）进行比较，无法判断该模型的相对优势。
- **算力与效率信息缺失**：未报告训练和推理速度，难以评估实际应用中的资源需求。
- **潜在偏差风险**：训练标注来自单一专家？还是多位专家？未说明标注者间一致性，且仅用一个验证集，可能存在过拟合风险。
- **应用限制**：仅针对“视网膜发育不良”一种病理，对其他视网膜病变（如视网膜脱离、脉络膜新生血管等）的通用性未知。此外，模型在低质量图像或存在伪影时的鲁棒性未探讨。

（完）
