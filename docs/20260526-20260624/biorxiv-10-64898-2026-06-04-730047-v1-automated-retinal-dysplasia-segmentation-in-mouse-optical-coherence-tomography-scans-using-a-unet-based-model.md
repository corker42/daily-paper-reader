---
title: Automated Retinal Dysplasia Segmentation in Mouse Optical Coherence Tomography Scans Using a UNet-Based model
title_zh: 基于UNet模型的小鼠光学相干断层扫描图像中视网膜发育不良的自动分割
authors: "Mikroulis, A., Raishbrook, M. J., Palkova, M., Lindovsky, J., Prochazka, J., Sedlacek, R., Novosadova, V., Novak, D."
date: 2026-06-06
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.730047v1.full.pdf"
tags: ["query:fundus-mc"]
score: 8.0
evidence: OCT扫描中视网膜发育异常的自动分割
tldr: "小鼠OCT扫描中视网膜病变的人工标注耗时且存在评分者间差异。本文基于UNet开发自动分割模型，在205个专家标注堆叠上训练，于40个未见堆叠验证，F1>0.95，与专家一致性中位Dice>0.8。集成到跨平台应用OCTOPUS，支持批处理、手动编辑和纵向追踪，有望促进实验室间标准化评估。"
source: biorxiv
selection_source: fresh_fetch
motivation: 手动标注小鼠OCT病理切片工作量大且易受主观差异影响，亟需自动化方法。
method: 采用UNet架构在205个专家标注的OCT堆叠上训练分割模型。
result: "模型在40个未见堆叠上F1>0.95，与专家一致性中位Dice>0.8。"
conclusion: 开发的OCTOPUS开源工具集成自动分割和编辑功能，实现高效、标准化评估。
---

## 摘要
目的：光学相干断层扫描（OCT）是目前临床前视网膜病变研究的先进非侵入性成像技术。然而，小鼠OCT扫描中的人工病理标注工作量大且易受评估者间差异影响。为缓解这些问题，我们开发了一种基于神经网络的小鼠OCT扫描图像视网膜发育不良自动标注模型。

方法：我们的模型在205个专家标注的OCT堆栈上进行训练，并在40个未见过的堆栈上进行验证，其中一部分还额外进行了专家标注比较。

结果：该模型能够高精度地检测病理（F1分数>0.95），且与专家标注的一致性高（中位Dice系数>0.8）。我们将该模型集成到一个跨平台应用（“OCTOPUS”）中，该应用包含批量处理、自动标注、手动标注编辑、基于眼底图像的病理区域定量纵向跟踪以及可导出为CSV和SVG格式的结果。

结论：我们的开源工具旨在促进和标准化各实验室间的OCT评估，以实现小鼠视网膜病变模型的高效临床前筛选和高通量表型分析。

## Abstract
PurposeOptical coherence tomography (OCT) is the state-of-the-art non-invasive imaging technique for preclinical retinopathy studies. However, manual pathology annotations in mouse OCT scans are labour-intensive and susceptible to inter-rater variability. To alleviate these issues, we developed a neural network-based model for automated annotation of retinal dysplasia in mouse OCT scans.

MethodsOur model was trained on 205 expert-annotated OCT stacks and validated on 40 unseen stacks with additional expert annotation comparisons in a subset of them.

ResultsThe model detects pathologies with high accuracy (F1-score > 0.95) and consistency with experts (median Dice score > 0.8). We integrated the model into a cross-platform app ("OCTOPUS") that includes batch processing, automated annotation, manual annotation editing, and quantitative longitudinal tracking with pathological area estimation on the fundus image, and exportable results in CSV and SVG formats.

ConclusionsOur open-source tool aims to facilitate and standardise OCT assessments between laboratories for efficient preclinical screening and high-throughput phenotyping in mouse models of retinal disease.