---
title: "Benchmarking attention-based methods for vision transformers' interpretability in retinal fundus imaging"
title_zh: 基于注意力方法的视觉Transformer在视网膜眼底成像中的可解释性基准测试
authors: "Bors, S., Beyeler, M., Trofimova, O., VascX Consortium,, Presby, D., Bontempi, D., Bergmann, S."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732470v1.full.pdf"
tags: ["query:fundus-class"]
score: 9.0
evidence: 在视网膜眼底影像上基准测试ViT注意力可解释方法
tldr: 视觉Transformer在视网膜眼底成像中表现优异，但基于注意力的可解释性方法缺乏忠实度与生物相关性的系统评估。本研究以RETFound（微调自UK Biobank图像预测17种视网膜血管表型）为基准，系统性比较原始注意力、注意力展开、梯度加权注意力展开和Chefer混合相关法四种归因技术。采用定性可视化、删除/插入扰动实验以及基于血管分割的相对注意力强度（RAI）指标进行全面评估。结果显示：梯度加权注意力展开在扰动测试中忠实度最佳，其归因图与血管解剖特征最为匹配；血管类型特异性模型能精准定位相应血管结构，证实方法捕获了生物学有用表征。该工作量化了方法间差异，并提供了医学影像可解释性的标准化评估框架，可推广至其他医学成像任务，推动透明且符合解剖学的AI系统发展。
source: biorxiv
selection_source: fresh_fetch
motivation: ViT在视网膜成像中性能强，但注意力归因方法缺乏忠实度和生物相关性的系统评估，亟需定量基准。
method: 以RETFound为基准，比较四种注意力归因方法，结合删除/插入实验和RAI指标进行定性和定量评估。
result: 梯度加权注意力展开在扰动测试中最优，归因图与血管解剖高度一致，且血管特异性模型聚焦对应结构。
conclusion: 建立了医学影像可解释性的标准化评估框架，揭示了方法间差异，推动透明且生物学可信的医疗AI发展。
---

## 摘要
基于视觉Transformer的深度学习模型在视网膜眼底成像中展现出强大性能，但其可解释性仍知之甚少。特别地，基于注意力的归因方法被广泛用于解释ViT预测，尽管在医学成像中其忠实性和生物学相关性的评估有限。在此，我们系统性地基准测试了四种基于注意力的可解释性方法应用于RETFound——一种基于视网膜ViT的基础模型，该模型我们先前微调以从英国生物银行眼底图像预测17种视网膜血管表型。我们比较了原始注意力、注意力展开、梯度加权注意力展开和Chefer的混合相关性方法，采用定性可视化和定量评估框架。为了评估归因的忠实性，我们进行了基于扰动的删除和插入实验，量化随着高关注图像区域被逐步移除或恢复时模型预测的变化。为了评估生物学特异性，我们进行了结构感知分析，通过注意力强度相对比率指标将归因图与血管分割和动静脉标签相结合。在不同模型中，归因图根据所选的可解释性方法而有显著差异，突显了严格定量评估的必要性。在评估的方法中，梯度加权注意力展开一致地实现了最强的扰动性能，并产生了与预测视网膜特征的解剖定义最一致的归因图。此外，尽管仅使用每个图像单个标量值作为监督进行训练，特定血管类型的模型系统地将注意力集中在相应的血管结构上。这些发现表明，基于注意力的归因方法捕获了具有生物学意义的血管表征，同时也揭示了归因行为中依赖于方法的变异性。这项工作为使用注释分割评估医学成像中的可解释性方法提供了一个定量框架，并有助于构建更透明且基于生物学的医疗AI系统。

## Abstract
Deep learning models based on Vision Transformers (ViTs) have shown strong performance in retinal fundus imaging, but their interpretability remains poorly understood. In particular, attention-based attribution methods are widely used to explain ViT predictions, despite limited evaluation of their faithfulness and biological relevance in medical imaging. Here, we systematically benchmark four attention-based interpretability methods for RETFound, a retinal ViT-based foundation model, that we previously fine-tuned to predict 17 retinal vascular phenotypes from UK Biobank fundus images1. We compare raw attention, attention rollout, gradient-weighted attention rollout, and Chefer's hybrid relevance-based method using both qualitative visualisation and quantitative evaluation frameworks. To assess attribution faithfulness, we perform perturbation-based deletion and insertion experiments, quantifying changes in model predictions as highly attended image regions are progressively removed or restored. To evaluate biological specificity, we run structure-aware analyses combining attribution maps with vessel segmentation and artery-vein labels through the Relative ratio of Attention Intensity (RAI) metric. Across models, attribution maps differed substantially depending on the selected interpretability method, highlighting the need for rigorous quantitative evaluation. Among the evaluated approaches, gradient-weighted attention rollout consistently achieved the strongest perturbation performance and produced attribution maps most closely aligned with the anatomical definition of the predicted retinal traits. Furthermore, vessel-type specific models systematically concentrate attention on the corresponding vascular structures despite being trained using only a single scalar value per image as supervision. These findings demonstrate that attention-based attribution methods capture biologically meaningful vascular representations, while also revealing method-dependent variability in attribution behaviour. This work provides a quantitative framework for evaluating interpretability methods in medical imaging with annotated segmentation and contributes toward more transparent and biologically grounded medical AI systems.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：视觉Transformer（ViT）在视网膜眼底成像中表现出优异性能，但基于注意力的可解释性方法在医学影像中的忠实性（faithfulness）和生物学相关性（biological relevance）缺乏系统性的定量评估。现有研究常直接使用原始注意力图或简单展开，却未验证其是否真实反映模型决策依据。
- **背景意义**：视网膜血管表型预测有助于疾病筛查和风险评估，但临床部署要求模型具备可解释性。论文以RETFound（视网膜ViT基础模型）为基准，微调预测17种血管表型，旨在建立一套可推广的标准化评估框架，推动透明且符合解剖结构的医学AI发展。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：通过定性可视化与定量评估相结合的方式，系统比较四种主流注意力归因方法，并引入基于血管分割的结构感知评价指标。
- **四种方法**：
  - 原始注意力（Raw Attention）
  - 注意力展开（Attention Rollout）
  - 梯度加权注意力展开（Gradient-weighted Attention Rollout）
  - Chefer混合相关法（Chefer's Hybrid Relevance-based method）
- **关键技术细节**：
  - **扰动实验**（Deletion & Insertion）：逐步移除或恢复图像中高注意力区域，量化模型预测得分的变化，评估归因图的忠实度。
  - **结构感知分析**：结合血管分割和动静脉标签，使用**注意力强度相对比率（RAI, Relative ratio of Attention Intensity）**指标，衡量归因图与解剖结构（血管、动脉、静脉）的重叠程度，评估生物学特异性。
- **文字化流程**：
  1. 输入视网膜眼底图像，经RETFound模型输出17种血管表型预测值；
  2. 对同一图像分别应用四种注意力归因方法，生成归因图；
  3. 在扰动实验中，按归因值从高到低删除/插入像素块，记录模型预测变化；
  4. 在结构分析中，将归因图与专家标注的血管分割图及动静脉标签对齐，计算RAI分数。

### 3. 实验设计：数据集、基准、对比方法

- **数据集**：英国生物银行（UK Biobank）眼底图像，用于微调RETFound并评估可解释性。
- **基准模型**：RETFound（视网膜ViT基础模型），微调后用于预测17种视网膜血管表型（如动脉宽度、静脉直径、分形维数等）。
- **对比方法**：
  - 四种注意力归因方法（原始注意力、注意力展开、梯度加权注意力展开、Chefer混合相关法）
  - 不同血管类型特异性模型（如仅预测动脉/静脉相关表型的模型）
- **评估维度**：
  - 定性：可视化归因图与血管解剖的对应关系
  - 定量：扰动实验（删除/插入曲线下面积）、RAI指标（与血管分割的重合度）

### 4. 资源与算力

- 论文摘要及元数据**未明确说明**所使用的GPU型号、数量、训练时长等算力信息。仅提及基于RETFound（预训练模型）进行微调，但未提供具体资源配置。

### 5. 实验数量与充分性

- **实验组数**：
  - 四种方法 × 多个模型（整体预测模型及血管类型特异性模型）→ 共数十组定性+定量结果
  - 扰动实验：删除和插入两条曲线
  - 结构分析：RAI指标在血管、动脉、静脉三种分割上的计算
- **覆盖范围**：仅基于UK Biobank单一数据集，未进行跨数据集验证；未与其他类别可解释性方法（如GradCAM、Integrated Gradients）对比；未包含消融实验分析各组件贡献。
- **客观性**：扰动实验和RAI指标均为客观量化，可重复性较好；但RAI指标依赖分割标注的质量，且未讨论标注误差影响。
- **充分性评价**：在当前研究范畴内较为充分，建立了评估框架并揭示了方法间差异，但缺少多中心、多任务泛化验证，属于初步基准测试。

### 6. 论文的主要结论与发现

- **方法性能排序**：梯度加权注意力展开在扰动实验中表现最优（忠实度最高），其归因图与预测视网膜特征的解剖定义最一致。
- **生物学特异性**：即使仅使用单标量值监督训练，血管类型特异性模型（如动脉表型预测模型）仍能将注意力集中到对应血管结构上，说明注意力方法捕获了生物学上有意义的表征。
- **方法依赖性**：不同归因方法产生的归因图差异显著，强调了必须进行定量评估而非仅依赖可视化。
- **框架价值**：该工作提供了使用注释分割评估医学影像可解释性的定量框架，可推广至其他医学成像任务。

### 7. 优点

- **系统定量评估**：同时从忠实度（扰动实验）和生物学相关性（RAI指标）两个维度评价，兼具内部与外部验证。
- **领域针对性**：引入血管分割标签，使评估贴近临床解剖需求，避免了仅依赖像素级扰动的抽象性。
- **方法全面性**：对比了四种代表性注意力归因方法，覆盖了纯注意力、因果展开、梯度加权、混合策略等多种思路。
- **揭示潜在价值**：证明即使弱监督（单标量标签）下，注意力归因也能定位到正确解剖结构，有助于增强临床信任。

### 8. 不足与局限

- **单一数据集与任务**：仅在UK Biobank眼底图像上进行，未验证在其他眼底数据集（如EyePACS、DRIVE）或其他医学影像模态（如X光、CT）上的泛化性。
- **方法覆盖不全**：未与梯度类（GradCAM）、类激活映射（CAM）、基于扰动或因果的可解释性方法对比，无法全面定位注意力方法的相对优势。
- **RAI指标依赖分割**：血管分割和动静脉标签的质量直接影响RAI结果，论文未讨论标注误差或进行鲁棒性检验。
- **计算开销未提及**：不同归因方法的计算成本未比较，可能影响实际部署选择。
- **临床转化验证缺失**：仅停留在模型归因分析，未进行临床专家评估或与疾病诊断关联分析，实际实用价值待验证。
- **可重复性限制**：论文依赖RETFound微调模型，但未提供模型权重或详细训练超参数，可能影响独立复现。

（完）
