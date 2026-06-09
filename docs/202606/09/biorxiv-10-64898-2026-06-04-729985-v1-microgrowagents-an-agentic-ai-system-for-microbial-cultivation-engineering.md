---
title: "MicroGrowAgents: An Agentic AI System for Microbial Cultivation Engineering"
title_zh: MicroGrowAgents：面向微生物培养工程的智能体AI系统
authors: "Naseem, S., Miller, M. A., Sun, N., Joachimiak, M. P."
date: 2026-06-05
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.04.729985v1.full.pdf"
tags: ["query:retina-agent"]
score: 6.0
evidence: 医疗保健中的智能体系统
tldr: 微生物培养优化传统方法依赖人工实验，效率低下。本文提出MicroGrowAgents智能体系统，集成知识图谱、代谢建模与最优实验设计，通过28个智能体和50项技能实现自动化培养基设计。应用于甲基杆菌AM1，在70种条件下评估生物量、氧化还原活性与稀土吸收，经蒙特卡洛重采样确定一个稳定帕累托最优培养基。该系统降低了实验负担，加速了生长条件发现，并提供完整溯源，推动可重现的数据驱动微生物培养。
source: biorxiv
selection_source: fresh_fetch
motivation: 传统微生物培养优化依赖大量试错，效率低且难以探索高维营养参数空间，亟需自动化智能方法减少实验负担。
method: 构建28个专用智能体与50项技能，整合知识图谱、文献挖掘、基因组注释及MaxPro算法，自动生成并优化培养基设计方案。
result: 针对甲基杆菌AM1设计70种条件，经三重目标评估与蒙特卡洛重采样，唯一稳定帕累托最优培养基MPOB_058出现频率0.99。
conclusion: MicroGrowAgents实现了证据驱动的假设生成，显著提升微生物培养优化效率与可重复性，具有广泛应用前景。
---

## 摘要
微生物培养优化仍然劳动密集且效率低下，需要大量实验筛选来识别合适的生长条件。传统的单因素轮换法在探索复杂的多维营养参数空间时尤为低效。我们提出了MicroGrowAgents，一个AI驱动的基于智能体的系统，通过整合知识图谱、代谢建模和最优实验设计，自动化优化生长培养基的设计。该系统采用28个专门智能体和50项技能，查询结构化生物学知识（KG-Microbe：864,363个已验证物种）、挖掘文献证据（245+篇论文）、执行基因组引导设计（57个基因组，667,000+个注释特征），并使用MaxPro算法生成统计上最优的实验设计。我们将该方法应用于扭脱甲基杆菌AM1，在四次重复中培养了70种设计条件，并评估了三个并行目标：生物量（740 nm处的OD600）、氧化还原活性（Biolog代理的Abs590）和镧系元素摄取（砷偶氮III测量的残留Nd）。对重复级别不确定性进行蒙特卡洛重采样（1000次迭代）识别出一个稳定的帕累托最优培养基MPOB_058（隶属频率0.99），以及两个边界候选者和六个罕见出现者，为后续的设计-构建-测试-学习轮次提供了一个稳健的锚定集。化学相似性搜索（208,000+嵌入）、代谢缺口分析和多模态推理的集成实现了基于证据的假设生成，减少了实验负担，同时加速了促生长条件的发现。MicroGrowAgents提供了完整的出处追踪，包括加密校验和以及90.5%的文献引用覆盖率，推进了可重复、数据驱动的微生物培养方法。

## Abstract
Microbial cultivation optimization remains labor-intensive and inefficient, requiring extensive experimental screening to identify suitable growth conditions. Traditional one-factor-at-a-time approaches are particularly ineffective for exploring complex, multidimensional nutrient parameter spaces. We present MicroGrowAgents, an AI-driven, agent-based system that automates the design of optimized growth media through integration of knowledge graphs, metabolic modeling, and optimal experimental design. The system employs 28 specialized agents and 50 skills that query structured biological knowledge (KG-Microbe: 864,363 validated species), mine literature evidence (245+ papers), perform genome-guided design (57 genomes, 667,000+ annotated features), and generate statistically optimal experimental designs using the MaxPro algorithm. We applied the approach to Methylorubrum extorquens AM1 by cultivating 70 designed conditions in quadruplicate and assessing three concurrent objectives: biomass (OD600 at 740 nm), redox activity (Abs590 Biolog proxy), and lanthanide uptake (residual Nd measured by arsenazo III). Monte-Carlo resampling of the replicate-level uncertainty (1000 iterations) identified a single stable Pareto-optimal medium, MPOB_058 (membership frequency 0.99), together with two borderline candidates and six rare appearers, providing a robust anchor set for subsequent rounds of design-build-test-learn. The integration of chemical similarity search (208,000+ embeddings), metabolic gap analysis, and multi-modal reasoning enables evidence-based hypothesis generation that reduces experimental burden while accelerating discovery of growth-promoting conditions. MicroGrowAgents provides complete provenance tracking with cryptographic checksums and 90.5% literature citation coverage, advancing reproducible, data-driven approaches to microbial cultivation.