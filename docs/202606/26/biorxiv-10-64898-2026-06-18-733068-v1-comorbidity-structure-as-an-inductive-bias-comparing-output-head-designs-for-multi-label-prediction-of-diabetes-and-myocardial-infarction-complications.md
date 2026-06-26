---
title: "Comorbidity structure as an inductive bias: Comparing output-head designs for multi-label prediction of diabetes and myocardial infarction complications"
title_zh: 共病结构作为归纳偏置：比较糖尿病和心肌梗死并发症多标签预测的输出头设计
authors: "Asumboya, W. A., Agbenorhevi, P. K., Adams, C. F., Ayariga, D. A., Adjadeh, T., Adams Ziblim, S., Kwofie, S. K."
date: 2026-06-23
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.18.733068v1.full.pdf"
tags: ["query:fundus-mc"]
score: 6.0
evidence: 预测视网膜病变作为糖尿病并发症，与视网膜疾病分类相关
tldr: 临床并发症常被独立预测，但共病结构可提供归纳偏置。本文在2型糖尿病和心肌梗死两个多标签预测任务中，比较了独立基线、线性加性、乘性、对称CRF、残差MLP等输出头。结果发现，在糖尿病的共享微血管并发症中，对称CRF表现最一致，尤其在小训练集下；而在心肌梗死的异质电生理并发症中，无稳定胜出的交互头。这表明输出层设计应作为对疾病结构的假设，而非仅超参数选择。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究输出层设计是否应反映共病生物学结构，而非仅出于预测便利。
method: 在2型糖尿病和心肌梗死任务中，比较独立基线、线性加性、乘性、对称CRF、残差MLP等输出头在多标签预测中的效果。
result: 糖尿病中对称CRF最稳定，尤其小样本时；心肌梗死中各输出头排名不稳定，无一致最优。
conclusion: 输出层选择应作为对疾病结构的假设来报告和辩护，而非单纯超参数调优。
---

## 摘要
背景：临床并发症通常使用独立的sigmoid输出进行预测，即使目标标签源自相关的病理生理过程。本文探讨输出层的选择是否应同时考虑预测便利性和假定的并发症之间的生物学结构。核心前提是，标签依赖机制是对共病关系的明确假设，而非通用的模型添加。
方法：在两个临床不同的多标签预测任务中比较了输出头的假设。在2型糖尿病（T2D）中，针对肾病、神经病变和视网膜病变评估了六种输出头：独立基线、线性加性、乘性、对称条件随机场（CRF）、残差多层感知器（MLP）以及加性-乘性组合。在心肌梗死（MI）中，针对室性心动过速、心室颤动和房室传导阻滞评估了四种输出头：独立基线、线性加性、乘性和对称CRF。所有实验均使用五个训练数据比例和七个独立种子，在每个疾病场景中采用相同的共享骨干网络协议。
结果：在T2D中，对称CRF提供了最一致的改进模式，在完整数据和两个最低数据比例下排名最高，且仅增加了三个交互参数。在20%训练数据时，它是唯一一个总体均值超过独立基线的交互头。残差MLP尽管有123个交互参数，但在所有T2D数据比例下均低于基线。在MI中，排名随数据比例变化：乘性头在80%和60%时领先，CRF在100%和20%时领先，基线在40%时领先。加性-乘性组合头并未提高T2D的稳健性，并且在较低数据比例下显示出最大的负向基线相对偏差。
结论：研究结果支持以生物学为导向的输出层设计观点。当一个小型约束机制与T2D共享微血管结构的对称性相匹配时最为有用，而MI的异质电生理学则没有产生稳定的胜者。因此，输出层的选择应作为对疾病结构的假设来报告和辩护，而非常规的超参数决策。
作者总结：许多临床预测模型将并发症视为独立的结果，即使临床医生知道它们常常同时出现。我们研究了模型的最后一层是否应反映这种生物学知识。我们在两种疾病场景中比较了多种输出头：2型糖尿病（肾病、神经病变和视网膜病变共享共同的微血管起源）和心肌梗死（电并发症由共享和位置特异性机制混合引起）。我们发现，在糖尿病任务中，特别是当训练数据有限时，一个小型对称CRF头最为有用，而在心肌梗死中没有单个交互头占主导地位。这表明建模共病不仅是技术选择，更是对疾病过程之间关系的表述。我们的结果鼓励研究者将输出层设计作为临床建模论证的一部分来报告和辩护，而非将其视为常规超参数。

## Abstract
BackgroundClinical complications are often predicted with separate sigmoid outputs, even when the target labels arise from related pathophysiological processes. This paper asks whether output-layer choice should reflect both predictive convenience and the biological structure assumed among complications. The central premise is that label-dependence mechanisms are explicit hypotheses about comorbidity, not generic modelling additions.

MethodsOutput-head assumptions were compared across two clinically distinct multi-label prediction tasks. In Type 2 diabetes (T2D), six heads were evaluated for nephropathy, neuropathy, and retinopathy: independent baseline, linear additive, multiplicative, symmetric conditional random field (CRF), residual multilayer perceptron (MLP), and combined additive-multiplicative. In myocardial infarction (MI), four heads were evaluated for ventricular tachycardia, ventricular fibrillation, and atrioventricular block: independent baseline, linear additive, multiplicative, and symmetric CRF. All experiments used five training data fractions and seven independent seeds, with the same shared-backbone protocol within each disease setting.

ResultsIn T2D, the symmetric CRF gave the most consistent improvement pattern, ranking highest at full data and at the two lowest data fractions while adding only three interaction parameters. At 20% training data, it was the only interaction head whose aggregate mean exceeded the independent baseline. The residual MLP, despite 123 interaction parameters, remained below the baseline across all T2D fractions. In MI, rankings changed across fractions: the multiplicative head led at 80% and 60%, the CRF led at 100% and 20%, and the baseline led at 40%. The combined additive-multiplicative head did not improve robustness in T2D and showed the largest negative baseline-relative deviations at lower fractions.

ConclusionThe findings support a biology-guided view of output-layer design. A small constrained mechanism was most useful when its symmetry matched the shared microvascular structure of T2D, whereas the heterogeneous electrophysiology of MI produced no stable winner. Output-layer choice should therefore be reported and defended as an assumption about disease structure instead of a routine hyperparameter decision.

Author summaryMany clinical prediction models treat complications as separate outcomes, even when clinicians know they often arise together. We studied whether the last layer of a model should reflect that biological knowledge. We compared several output heads across two disease settings: Type 2 diabetes, where nephropathy, neuropathy, and retinopathy share a common microvascular origin, and myocardial infarction, where electrical complications arise from a mixture of shared and location-specific mechanisms. We found that a small symmetric CRF head was most useful in the diabetes task, especially when training data were limited, while no single interaction head dominated in myocardial infarction. This suggests that modelling comorbidity is not only a technical choice; it is a statement about how disease processes relate to one another. Our results encourage researchers to report and justify output-layer design as part of the clinical modelling argument, rather than treating it as a routine hyperparameter.