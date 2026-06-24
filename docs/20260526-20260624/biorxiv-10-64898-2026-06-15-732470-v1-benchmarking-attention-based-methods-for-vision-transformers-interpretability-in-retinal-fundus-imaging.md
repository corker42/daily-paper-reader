---
title: "Benchmarking attention-based methods for vision transformers' interpretability in retinal fundus imaging"
title_zh: 基于注意力的视觉Transformer在视网膜眼底成像中可解释性方法的基准测试
authors: "Bors, S., Beyeler, M., Trofimova, O., VascX Consortium,, Presby, D., Bontempi, D., Bergmann, S."
date: 2026-06-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.15.732470v1.full.pdf"
tags: ["query:fundus-mc"]
score: 8.0
evidence: 眼底影像可解释性基准测试
tldr: Vision Transformer在视网膜眼底成像中可解释性不足。本文系统评估了四种注意力归因方法在RETFound模型上的表现，发现梯度加权注意力展开在扰动实验和生物特异性分析中最佳，揭示了方法依赖的变异性。该工作提供了定量评估框架，促进透明医疗AI。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有的注意力可解释性方法在医学图像中的忠实性和生物相关性缺乏系统评估。
method: 在RETFound模型上比较原始注意力、注意力展开、梯度加权注意力展开和Chefer混合方法，采用扰动实验和血管分割结构感知分析。
result: 梯度加权注意力展开在扰动性能和与解剖结构对齐方面均优于其他方法。
conclusion: 提供了评估医学影像可解释性的量化框架，证明注意力方法能捕捉生物学有意义的血管表示。
---

## 摘要
基于视觉Transformer（ViT）的深度学习模型在视网膜眼底成像中表现出强大的性能，但其可解释性仍然难以理解。特别是，尽管在医学成像中对其忠实性和生物学相关性的评估有限，但基于注意力的归因方法被广泛用于解释ViT预测。在此，我们系统地对四种基于注意力的可解释性方法进行基准测试，用于RETFound——一个基于视网膜ViT的基础模型，我们之前对其进行了微调，以从英国生物银行眼底图像中预测17种视网膜血管表型。我们比较了原始注意力、注意力展开、梯度加权注意力展开和Chefers混合相关性方法，使用了定性的可视化和定量的评估框架。为了评估归因的忠实性，我们进行了基于扰动的删除和插入实验，量化了当高度关注的图像区域被逐步移除或恢复时模型预测的变化。为了评估生物特异性，我们进行了结构感知分析，通过注意力强度相对比（RAI）指标将归因图与血管分割和动静脉标签相结合。在不同的模型中，归因图根据所选的可解释性方法而有显著差异，突出了进行严格定量评估的必要性。在评估的方法中，梯度加权注意力展开始终达到最强的扰动性能，并产生与预测视网膜特征的解剖定义最一致的归因图。此外，尽管仅使用每张图像单个标量值作为监督，但特定血管类型的模型系统地将注意力集中在相应的血管结构上。这些发现表明，基于注意力的归因方法捕获了具有生物学意义的血管表示，同时也揭示了归因行为中依赖于方法的变化性。这项工作为在医学成像中使用注释分割评估可解释性方法提供了一个定量框架，并有助于建立更透明和基于生物学的医学AI系统。

## Abstract
Deep learning models based on Vision Transformers (ViTs) have shown strong performance in retinal fundus imaging, but their interpretability remains poorly understood. In particular, attention-based attribution methods are widely used to explain ViT predictions, despite limited evaluation of their faithfulness and biological relevance in medical imaging. Here, we systematically benchmark four attention-based interpretability methods for RETFound, a retinal ViT-based foundation model, that we previously fine-tuned to predict 17 retinal vascular phenotypes from UK Biobank fundus images1. We compare raw attention, attention rollout, gradient-weighted attention rollout, and Chefers hybrid relevance-based method using both qualitative visualisation and quantitative evaluation frameworks. To assess attribution faithfulness, we perform perturbation-based deletion and insertion experiments, quantifying changes in model predictions as highly attended image regions are progressively removed or restored. To evaluate biological specificity, we run structure-aware analyses combining attribution maps with vessel segmentation and artery-vein labels through the Relative ratio of Attention Intensity (RAI) metric. Across models, attribution maps differed substantially depending on the selected interpretability method, highlighting the need for rigorous quantitative evaluation. Among the evaluated approaches, gradient-weighted attention rollout consistently achieved the strongest perturbation performance and produced attribution maps most closely aligned with the anatomical definition of the predicted retinal traits. Furthermore, vessel-type specific models systematically concentrate attention on the corresponding vascular structures despite being trained using only a single scalar value per image as supervision. These findings demonstrate that attention-based attribution methods capture biologically meaningful vascular representations, while also revealing method-dependent variability in attribution behaviour. This work provides a quantitative framework for evaluating interpretability methods in medical imaging with annotated segmentation and contributes toward more transparent and biologically grounded medical AI systems.