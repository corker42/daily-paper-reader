---
title: A Web-based software toolkit for accessible and best-practice machine learning analyses in biomedical research
title_zh: 一个基于网络的软件工具包，用于生物医学研究中易于使用且符合最佳实践的机器学习分析
authors: "Morais Lyra Junior, P. C., Qiu, J., Van Dang, K., Pybus, A., Narvaez-Bandera, I., Singh, M. A., Gu, Q., Sargent, L., Creason, A. L., Goecks, J."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730487v1.full.pdf"
tags: ["query:fundus-class"]
score: 7.0
evidence: 用于生物医学图像分类的基于网络的机器学习工具包
tldr: 机器学习在生物医学研究中日益重要，但需要专业知识及方法论规范。为此，开发了GLEAM软件工具包，基于Galaxy平台提供无代码Web工具，可处理表格、图像和多模态数据。它标准化数据划分、模型选择、训练与评估流程。在免疫疗法响应预测、皮肤病变分类和癌症复发预测三个任务中，GLEAM生成了高准确率模型，并提升了分析的可重复性与严谨性。
source: biorxiv
selection_source: fresh_fetch
motivation: 生物医学研究者需要易用且遵循最佳实践的机器学习工具，以降低计算门槛并提高结果质量。
method: GLEAM在Galaxy工作台上构建，提供无代码Web工具，标准化数据划分、模型选择、训练、评估和报告流程。
result: 在三个生物医学任务中，GLEAM产生高精度预测模型，并显著提升了分析透明度、可重复性和严谨性。
conclusion: GLEAM使生物医学研究者能轻松应用机器学习，同时确保分析符合最佳实践，适用于多模态数据。
---

## 摘要
机器学习在生物医学研究中日益核心，但良好地运用机器学习通常需要大量的计算专业知识和严谨的方法学才能产生高质量的结果。为了让生物医学研究人员更容易使用机器学习工具，同时支持最佳实践方法，我们开发了Galaxy学习与建模（GLEAM）软件工具包。GLEAM通过一组基于Web、无需编码的软件工具，使研究人员能够对表格、图像和多模态生物医学数据集进行监督式机器学习分析。GLEAM标准化了数据划分、模型选择、训练、评估和报告流程，帮助研究人员以更高的严谨性和一致性应用机器学习。GLEAM运行在Galaxy计算工作台上，并利用Galaxy的核心功能，使所有分析都易于访问、可重复且可扩展。我们在三个生物医学任务上验证了GLEAM：预测患者对免疫疗法的反应、皮肤病变分类和癌症复发预测。在这些任务中，GLEAM生成了高度准确的预测模型，并提高了透明度、可重复性和严谨性。

## Abstract
Machine learning is increasingly central to biomedical research, but using machine learning well often requires substantial computational expertise and methodological care to produce high-quality results. To make machine learning tools more accessible to biomedical researchers while supporting best-practice approaches, we developed the Galaxy Learning and Modeling (GLEAM) software toolkit. GLEAM enables researchers to perform supervised machine learning analyses through a set of web-based, code-free software tools for tabular, image, and multimodal biomedical datasets. GLEAM standardizes data partitioning, model selection, training, evaluation, and reporting, helping researchers apply machine learning with greater rigor and consistency. GLEAM runs on the Galaxy computational workbench and uses Galaxys core features to make all analyses accessible, reproducible, and scalable. We validated GLEAM on three biomedical tasks: predicting patient response to immunotherapy, skin lesion classification, and cancer recurrence prediction. Across these tasks, GLEAM produced highly accurate predictive models and improved transparency, reproducibility, and rigor.