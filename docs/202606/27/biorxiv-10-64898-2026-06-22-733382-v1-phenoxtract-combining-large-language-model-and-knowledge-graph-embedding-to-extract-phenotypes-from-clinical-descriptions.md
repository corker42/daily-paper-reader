---
title: "PhenoXtract: combining Large Language Model and Knowledge Graph embedding to extract phenotypes from clinical descriptions"
title_zh: PhenoXtract：结合大语言模型与知识图谱嵌入从临床描述中提取表型
authors: "Berardelli, S., BRIERE, G., Loire, B., De Paoli, F., Gazzo, A. M., Limongelli, I., Magni, P., Zucca, S., Baudot, A."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.22.733382v1.full.pdf"
tags: ["query:retina-agent"]
score: 6.0
evidence: 结合大语言模型和知识图谱从临床文本中提取表型，支持医疗AI
tldr: 临床表型标准化对精准诊断至关重要，但手动提取费时费力。PhenoXtract结合大语言模型和知识图谱嵌入，构建多步流水线：先用LLM抽取候选实体，再映射至增强版HPO知识图谱。在专家标注数据集上召回0.70、精确0.85，计算速度10-20秒/文本，且多数指标超越现有工具。该混合方法为规模化自动临床表型提取提供了新思路。
source: biorxiv
selection_source: fresh_fetch
motivation: 手动从临床文本中提取并映射表型到HPO耗时且易错，亟需自动化方法提高效率与一致性。
method: 提出PhenoXtract，使用LLM识别候选表型实体，通过知识图谱嵌入将实体映射到增强版HPO本体。
result: 在三个基准数据集上召回0.70、精确0.85，其中两个数据集的性能超过当前最优工具，单文本处理仅10-20秒。
conclusion: LLM与知识图谱嵌入结合的混合方法在大规模自动临床表型抽取中展现出显著潜力。
---

## 摘要
动机：标准化的表型描述对于准确诊断至关重要，然而临床医生和研究人员在从科学文献或患者临床记录中手动提取表型并将其映射到人类表型本体方面面临挑战。深度学习的最新进展为自动化提供了新的机遇。我们开发了PhenoXtract，一种新颖的表型提取方法，它结合了大语言模型和知识图谱嵌入。PhenoXtract是一个多步骤流程，以临床描述为输入，使用大语言模型提取候选表型实体，并将其映射到经过丰富的人类表型本体版本中的术语，该本体作为知识图谱处理。结果：针对专家策划的真值数据集的评估显示，PhenoXtract的召回率为0.70，精确率为0.85，与手动提取的表型具有一致性，每次文本分析的计算时间为10-20秒。此外，在评估的三个真值数据集中，PhenoXtract在其中的两个上超越了基于规则和基于深度学习的最新工具。这些结果表明，结合大语言模型和知识图谱嵌入的混合方法代表了大规模自动化临床表型提取的一个有前景的方向。

## Abstract
Motivation: Standardized phenotypic descriptions are essential for accurate diagnosis, yet clinicians and researchers face challenges in manually extracting and mapping phenotypes from scientific literature or patient clinical records to the Human Phenotype Ontology. Recent advances in deep learning offer new opportunities for automation. We developed PhenoXtract, a novel phenotype extraction approach that combines Large Language Models and Knowledge Graph embedding. PhenoXtract is a multistep pipeline that takes clinical descriptions as input, extracts candidate phenotype entities using large language models, and maps them to terms from an enriched version of the Human Phenotype Ontology, processed as a knowledge graph. Results: Evaluation against expert-curated ground-truth datasets show a recall of 0.70 and precision of 0.85 for PhenoXtract, demonstrating concordance with manually extracted phenotypes, with a computation time of 10-20 seconds for each text analyzed. Moreover, PhenoXtract surpasses rule-based and deep learning-based state-of-the-art tools in two out of the three ground-truth datasets evaluated. These results suggest that hybrid approaches combining Large Language Models and Knowledge Graph embeddings represent a promising direction for automated clinical phenotyping at scale.