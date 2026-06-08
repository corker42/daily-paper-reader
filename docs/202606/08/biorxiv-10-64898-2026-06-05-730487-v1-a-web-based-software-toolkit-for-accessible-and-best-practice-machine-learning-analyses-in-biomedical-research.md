---
title: A Web-based software toolkit for accessible and best-practice machine learning analyses in biomedical research
title_zh: 一个基于网络的软件工具包，用于生物医学研究中可访问且遵循最佳实践的机器学习分析
authors: "Morais Lyra Junior, P. C., Qiu, J., Van Dang, K., Pybus, A., Narvaez-Bandera, I., Singh, M. A., Gu, Q., Sargent, L., Creason, A. L., Goecks, J."
date: 2026-06-07
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.05.730487v1.full.pdf"
tags: ["query:fundus-class"]
score: 6.0
evidence: 提供通用机器学习工具包，可应用于眼底疾病分类任务
tldr: 生物医学研究中机器学习应用广泛但需要专业知识和严谨方法。为降低门槛，开发了基于Galaxy平台的GLEAM工具包，提供无代码Web界面，标准化数据划分、模型选择、训练与评估流程。在免疫治疗反应预测、皮肤病变分类和癌症复发预测三个任务上验证，获得高精度模型。GLEAM显著提升了机器学习分析的可访问性、可重复性和严谨性。
source: biorxiv
selection_source: fresh_fetch
motivation: 使生物医学研究者无需编程即可进行规范化机器学习分析，避免方法错误。
method: 开发基于Galaxy的GLEAM工具包，提供无代码界面，标准化数据划分、模型选择、训练与评估流程。
result: 在三个生物医学任务上获得高精度预测模型，并提升分析透明度和可重复性。
conclusion: GLEAM降低了机器学习使用门槛，促进了生物医学研究中的最佳实践。
---

## 摘要
机器学习在生物医学研究中日益重要，但要应用好机器学习往往需要大量的计算专业知识和严谨的方法论才能获得高质量的结果。为了让生物医学研究者更易使用机器学习工具，同时支持最佳实践方法，我们开发了Galaxy Learning and Modeling (GLEAM) 软件工具包。GLEAM通过一组基于网络、无需编码的软件工具，使得研究者能够在表格、图像和多模态生物医学数据集上执行监督式机器学习分析。GLEAM标准化了数据划分、模型选择、训练、评估和报告流程，帮助研究者以更严谨、一致的方式应用机器学习。GLEAM运行在Galaxy计算工作台上，并利用Galaxy的核心功能，使所有分析均可访问、可重复、可扩展。我们在三个生物医学任务上验证了GLEAM：预测患者对免疫疗法的反应、皮肤病变分类以及癌症复发预测。在这些任务中，GLEAM生成了高精度的预测模型，并提高了透明度、可重复性和严谨性。

## Abstract
Machine learning is increasingly central to biomedical research, but using machine learning well often requires substantial computational expertise and methodological care to produce high-quality results. To make machinelearning tools more accessible to biomedical researchers while supporting best-practice approaches, we developed the Galaxy Learning and Modeling (GLEAM) software toolkit. GLEAM enables researchers to performsupervised machine learning analyses through a set of web-based, code-free software tools for tabular, image, and multimodal biomedical datasets. GLEAM standardizes data partitioning, model selection, training, evaluation,and reporting, helping researchers apply machine learning with greater rigor and consistency. GLEAM runs on the Galaxy computational workbench and uses Galaxy's core features to make all analyses accessible,reproducible, and scalable. We validated GLEAM on three biomedical tasks: predicting patient response to immunotherapy, skin lesion classification, and cancer recurrence prediction. Across these tasks, GLEAM producedhighly accurate predictive models and improved transparency, reproducibility, and rigor.