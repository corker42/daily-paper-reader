---
title: A Web-based software toolkit for accessible and best-practice machine learning analyses in biomedical research
title_zh: 一个基于Web的软件工具包，用于生物医学研究中可访问且符合最佳实践的机器学习分析
authors: "Morais Lyra Junior, P. C., Qiu, J., Van Dang, K., Pybus, A., Narvaez-Bandera, I., Singh, M. A., Gu, Q., Sargent, L., Creason, A. L., Goecks, J."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730487v1.full.pdf"
tags: ["query:fundus-class"]
score: 6.0
evidence: 基于网页的机器学习工具包支持医学图像分类，可迁移至眼底图像分析
tldr: 生物医学研究中机器学习应用需要专业知识且易出错。GLEAM工具包提供Web端无代码界面，支持表格、图像和多模态数据的监督学习。它标准化数据划分、模型选择、训练评估和报告，提升分析可重复性和严谨性。在免疫疗法响应预测、皮肤病变分类和癌症复发预测任务中取得高精度，增强了透明度和可复现性。
source: biorxiv
selection_source: fresh_fetch
motivation: 降低生物医学研究者使用机器学习的门槛，同时确保方法规范性和结果可复现性。
method: 基于Galaxy工作台构建无代码Web工具，集成标准化数据划分、模型搜索、评估和报告流程。
result: 在免疫疗法响应、皮肤病变分类和癌症复发预测任务中，模型准确率高且可重复性强。
conclusion: GLEAM使生物医学机器学习更易用、更规范，提升了研究透明度和可复现性。
---

## 摘要
机器学习日益成为生物医学研究的核心，但良好地使用机器学习通常需要大量的计算专业知识和方法论上的谨慎，才能产生高质量的结果。为了使生物医学研究人员更容易使用机器学习工具，同时支持最佳实践方法，我们开发了Galaxy学习与建模（GLEAM）软件工具包。GLEAM通过一套基于Web、无需代码的软件工具，使研究人员能够对表格、图像和多模态生物医学数据集进行监督机器学习分析。GLEAM标准化了数据分区、模型选择、训练、评估和报告，帮助研究人员以更高的严谨性和一致性应用机器学习。GLEAM在Galaxy计算工作台上运行，并利用Galaxy的核心功能，使所有分析都可访问、可重现且可扩展。我们在三个生物医学任务上验证了GLEAM：预测患者对免疫疗法的反应、皮肤病变分类和癌症复发预测。在这些任务中，GLEAM生成了高度准确的预测模型，并提高了透明度、可重现性和严谨性。

## Abstract
Machine learning is increasingly central to biomedical research, but using machine learning well often requires substantial computational expertise and methodological care to produce high-quality results. To make machinelearning tools more accessible to biomedical researchers while supporting best-practice approaches, we developed the Galaxy Learning and Modeling (GLEAM) software toolkit. GLEAM enables researchers to performsupervised machine learning analyses through a set of web-based, code-free software tools for tabular, image, and multimodal biomedical datasets. GLEAM standardizes data partitioning, model selection, training, evaluation,and reporting, helping researchers apply machine learning with greater rigor and consistency. GLEAM runs on the Galaxy computational workbench and uses Galaxy's core features to make all analyses accessible,reproducible, and scalable. We validated GLEAM on three biomedical tasks: predicting patient response to immunotherapy, skin lesion classification, and cancer recurrence prediction. Across these tasks, GLEAM producedhighly accurate predictive models and improved transparency, reproducibility, and rigor.