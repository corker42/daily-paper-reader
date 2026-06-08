---
title: SortIT - A Tool For Assessing Observer Variability And Creating Ground Truth Image Classification Datasets
title_zh: SortIT——评估观察者变异性和创建真实图像分类数据集的工具
authors: "Uegami, W., Bisson, T., Okoshi, E. N., Costa da Silva, F. G., Munkhdelger, J., Lami, K., Zerbe, N., Bychkov, A., Fukuoka, J."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728616v2.full.pdf"
tags: ["query:fundus-class"]
score: 6.0
evidence: 用于创建图像分类真实标注集的工具，可应用于眼底疾病
tldr: 病理评估中的观察者间变异性影响诊断可靠性。为创建可靠的ground truth数据集以训练稳健的AI模型，本文提出SortIT开源Web应用。该工具允许多名标注者独立标注图像切片，并灵活设置权限，标注数据可导出用于统计观察者变异和生成共识数据集。已成功应用于有丝分裂分割、前列腺癌分级和肉芽肿分类等场景，其易部署性和开源特性有助于社区推广。
source: biorxiv
selection_source: fresh_fetch
motivation: 病理评估存在主观性导致的观察者间变异，需要系统性工具来创建高质量ground truth以提升AI诊断的可靠性。
method: 开发SortIT开源Web应用，支持多用户独立标注图像切片，灵活控制权限，并可导出标注数据进行变异分析和共识构建。
result: 针对有丝分裂分割、前列腺癌分级和肉芽肿分类等场景，SortIT有效支持了观察者变异评估和共识数据集创建。
conclusion: SortIT作为易部署的开源工具，能够系统评估观察者变异并构建高质量ground truth，对开发准确泛化的病理AI至关重要。
---

## 摘要
病理评估中的观察者间变异性是一个公认的挑战，影响着诊断可靠性和疾病理解。由于评估的主观性，这种变异性存在于许多亚专业领域。应用于全切片图像的人工智能有可能标准化流程并减少病理学中的变异性，但过渡到这些技术并不能保证改进。建立具有共识标注的可靠真实数据集对于开发稳健的人工智能解决方案至关重要。我们介绍SortIT，一个开源网络应用程序，用于促进真实图像瓦片注释的系统创建和评估。SortIT使多位注释者能够独立标记瓦片，并具有灵活的用户权限控制。注释数据可以导出，用于观察者变异性的统计分析，以及从共识瓦片创建真实数据集。我们概述了使用SortIT的几个用例协议：（1）肿瘤区域的有丝分裂分割，（2）通过与专家共识比较来评估前列腺癌分级的人工智能解决方案，以及（3）通过注释区分性瓦片级特征进行肉芽肿分类。SortIT的主要优势在于其易于部署，使其对广泛用户可访问和可用。总体而言，SortIT为建立高质量的真实数据集和全面评估观察者变异性提供了有价值的工具。使用系统化注释方法对真实质量进行批判性评估对于开发准确且可泛化的诊断人工智能工具至关重要。其开源特性促进了社区的采用和进一步发展。

## Abstract
Interobserver variability in pathological assessments is a well-recognized challenge that impacts diagnostic reliability and disease understanding. This variability exists across many subspecialties due to the subjective nature of evaluations. Artificial intelligence (AI) applied to whole slide images has potential to standardize procedures and reduce variability in pathology, but transitioning to these technologies does not guarantee improvement. Establishing reliable ground truth datasets with consensus annotations is crucial for developing robust AI solutions. We introduce SortIT, an open-source web application that facilitates systematic creation and evaluation of ground truth image tile annotations. SortIT enables multiple annotators to independently label tiles, with flexible user permission controls. Annotated data can be exported for statistical analysis of observer variation and for creating ground truth datasets from consensus tiles. We outline protocols using SortIT for several use cases: (1) mitosis segmentation in tumor regions, (2) evaluating AI solutions for prostate cancer grading by comparing to expert consensus, and (3) granuloma classification by annotating discriminative tile-level features. Key strengths of SortIT lies in its ease of deployment, making it accessible and usable for a wide range of users. Overall, SortIT provides a valuable tool to establish high-quality ground truth datasets and comprehensively assess observer variability. Critical evaluation of ground truth quality using systematic annotation methodologies is crucial for developing accurate and generalizable diagnostic AI tools. Its open-source nature facilitates community adoption and further development.