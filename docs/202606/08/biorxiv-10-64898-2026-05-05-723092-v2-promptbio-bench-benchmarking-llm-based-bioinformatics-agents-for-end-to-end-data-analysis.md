---
title: "PromptBio-Bench: Benchmarking LLM-based Bioinformatics Agents for End-to-End Data Analysis"
title_zh: PromptBio-Bench：基于LLM的生物信息学智能体端到端数据分析的基准测试
authors: "Guo, W., Zhang, M., Han, B., Ma, Y., Leng, Y., Hebbar, S., Zhou, X., Gu, W., Yang, X., Dhar, S."
date: 2026-06-01
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.05.723092v2.full.pdf"
tags: ["query:retina-agent"]
score: 6.0
evidence: LLM生物信息学代理基准，与医疗AI代理开发相关
tldr: 当前缺乏对基于大语言模型的生物信息学智能体进行系统性评估的基准。为此，PromptBio-Bench构建了包含244个专家精选任务的评测套件，并设计了结构化文件比较与评分框架。对三个代表性智能体的测试显示，所有智能体的准确性均随任务难度增加而显著下降。该基准为追踪智能体在生物信息学领域的进展提供了标准化基础设施。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有评估方法无法系统衡量LLM智能体在真实生物信息学工作流中的表现。
method: 构建包含244个跨难度任务的专家筛选数据集和结构化文件比较评分框架。
result: 三个先进生物信息学智能体表现相近，但准确性随任务难度递增而明显下降。
conclusion: PromptBio-Bench为智能体生物信息学的进步提供了可重复的基准评估工具。
---

## 摘要
基于大型语言模型（LLM）的智能体在自动化生物信息学工作流方面具有变革潜力；然而，对其能力的系统评估仍然有限，阻碍了对其实际应用准备情况的清晰评估。我们提出了PromptBio-Bench，这是一个包含244个专家精心策划的任务的综合评估套件，涵盖不同难度级别的生物信息学和数据科学，以及一个针对结构化文件比较和与专家参考答案文件评分进行评估的框架。对三个最先进的生物信息学智能体的评估显示，Biomni和ToolsGenie之间的性能相当，所有智能体在任务难度增加时准确率显著下降。随着基础模型和智能体框架的不断发展，PromptBio-Bench为系统跟踪智能体生物信息学的进展提供了宝贵的基准基础设施。

## Abstract
Large language model (LLM)-based agents hold transformative potential for automating bioinformatics workflows; however, systematic evaluations of their capabilities remain limited, hindering a clear assessment of their readiness for real-world application. We introduce PromptBio-Bench, a comprehensive evaluation suite of 244 expert-curated tasks spanning bioinformatics and data science at varied difficulty levels, and an evaluation framework for structured file comparison and scoring against expert reference answer files. Evaluation of three state-of-the-art bioinformatics agents revealed comparable performance between Biomni and ToolsGenie, with all agents showing a marked decline in accuracy as task difficulty increased. As foundation models and agent frameworks continue to evolve, PromptBio-Bench provides a valuable benchmark infrastructure for systematically tracking progress in agentic bioinformatics.