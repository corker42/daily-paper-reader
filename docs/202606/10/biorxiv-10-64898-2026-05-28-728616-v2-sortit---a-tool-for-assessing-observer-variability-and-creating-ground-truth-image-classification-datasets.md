---
title: SortIT - A Tool For Assessing Observer Variability And Creating Ground Truth Image Classification Datasets
title_zh: SortIT - 一种评估观察者变异性和创建地面真值图像分类数据集的工具
authors: "Uegami, W., Bisson, T., Okoshi, E. N., Costa da Silva, F. G., Munkhdelger, J., Lami, K., Zerbe, N., Bychkov, A., Fukuoka, J."
date: 2026-06-02
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.28.728616v2.full.pdf"
tags: ["query:fundus-class"]
score: 6.0
evidence: 创建图像分类地面真值数据集的工具，对眼底病分类至关重要
tldr: 病理评估中观察者间变异性影响诊断可靠性。SortIT是一种开源web应用，支持多标注者独立标注图像图块，导出数据用于变异性分析和共识标注创建。该工具已在有丝分裂分割、前列腺癌分级和肉芽肿分类中验证有效，为建立高质量病理AI训练数据集和评估标注一致性提供了便捷方案。
source: biorxiv
selection_source: fresh_fetch
motivation: 病理评估主观性强，观察者间变异性大，需要高质量共识数据集以开发可靠的AI诊断工具。
method: 开发了开源web应用SortIT，支持多个标注者独立对图像图块进行标注，并通过权限控制与数据导出实现变异性分析与共识构建。
result: 在三个用例中（有丝分裂分割、前列腺癌分级、肉芽肿分类）展示了SortIT有效建立共识标注并评估观察者变异性。
conclusion: SortIT作为开源工具，能够系统建立高质量标注数据集，评估观察者变异性，为病理AI的准确性和泛化性提供基础。
---

## 摘要
病理评估中的观察者间变异性是一个公认的挑战，影响诊断可靠性和疾病理解。由于评估的主观性，这种变异性存在于许多亚专业中。应用于全切片图像的人工智能有潜力标准化程序并减少病理学中的变异性，但过渡到这些技术并不能保证改进。建立具有共识注释的可靠地面真值数据集对于开发稳健的AI解决方案至关重要。我们介绍了SortIT，一个开源网络应用程序，它有助于系统地创建和评估地面真值图像块注释。SortIT使多个注释者能够独立标记图像块，并具有灵活的用户权限控制。注释数据可以导出，用于观察者变异的统计分析，以及从共识块创建地面真值数据集。我们概述了使用SortIT的几个用例协议：（1）肿瘤区域中的有丝分裂分割，（2）通过与专家共识比较来评估前列腺癌分级的人工智能解决方案，以及（3）通过注释区分性块级特征进行肉芽肿分类。SortIT的主要优势在于其易于部署，使其对广泛的用户可访问和可用。总体而言，SortIT提供了一个有价值的工具来建立高质量的地面真值数据集并全面评估观察者变异性。使用系统注释方法对地面真值质量进行关键评估对于开发准确且可泛化的诊断AI工具至关重要。其开源性质促进了社区的采用和进一步开发。

## Abstract
Interobserver variability in pathological assessments is a well-recognized challenge that impacts diagnostic reliability and disease understanding. This variability exists across many subspecialties due to the subjective nature of evaluations. Artificial intelligence (AI) applied to whole slide images has potential to standardize procedures and reduce variability in pathology, but transitioning to these technologies does not guarantee improvement. Establishing reliable ground truth datasets with consensus annotations is crucial for developing robust AI solutions. We introduce SortIT, an open-source web application that facilitates systematic creation and evaluation of ground truth image tile annotations. SortIT enables multiple annotators to independently label tiles, with flexible user permission controls. Annotated data can be exported for statistical analysis of observer variation and for creating ground truth datasets from consensus tiles. We outline protocols using SortIT for several use cases: (1) mitosis segmentation in tumor regions, (2) evaluating AI solutions for prostate cancer grading by comparing to expert consensus, and (3) granuloma classification by annotating discriminative tile-level features. Key strengths of SortIT lies in its ease of deployment, making it accessible and usable for a wide range of users. Overall, SortIT provides a valuable tool to establish high-quality ground truth datasets and comprehensively assess observer variability. Critical evaluation of ground truth quality using systematic annotation methodologies is crucial for developing accurate and generalizable diagnostic AI tools. Its open-source nature facilitates community adoption and further development.