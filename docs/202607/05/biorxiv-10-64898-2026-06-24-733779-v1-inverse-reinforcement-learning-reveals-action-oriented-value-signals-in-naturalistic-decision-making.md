---
title: Inverse reinforcement learning reveals action-oriented value signals in naturalistic decision making
title_zh: 逆向强化学习揭示自然决策中面向行动的价值信号
authors: "Lee, S. H., Chung, C., Oh, M.-h., Ahn, W.-Y."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.24.733779v1.full.pdf"
tags: ["query:fsrh"]
score: 6.0
evidence: 使用逆强化学习建模决策
tldr: 自然主义决策中行为价值难以用传统模型刻画。逆强化学习可从复杂行为中推断潜在奖励轨迹。fMRI实验发现，该奖励轨迹与背侧纹状体等价值相关脑区活动显著相关，还涉及认知控制和感觉运动区域。表明IRL奖励是动作导向价值的有效代理，能揭示价值与多系统交互。
source: biorxiv
selection_source: fresh_fetch
motivation: 探讨逆强化学习推断的价值信号是否映射到大脑活动，以理解自然决策中的价值计算。
method: 在fMRI扫描中让被试执行实时驾驶任务，用逆强化学习从行为推断时刻奖励轨迹，并与脑活动关联。
result: IRL奖励与背侧纹状体活动最相关，还关联认知控制、感觉运动等分布式区域。
conclusion: 逆强化学习奖励可作为自然主义决策中动作导向价值的可靠神经代理，反映价值与多种认知过程的交互。
---

## 摘要
认知神经科学的一个主要挑战是解释在复杂和自然环境中目标导向行为的价值是如何计算的。标准的决策计算模型在受控的试次范式下非常成功，但通常不适用于自然范式中实时展开的行为。逆向强化学习（IRL）提供了一种从自然环境中观察到的行为推断潜在评估状态的方法，但其神经可解释性仍然很大程度上未知。在这里，我们研究了在fMRI扫描期间执行实时驾驶任务时，从IRL导出的逐时刻奖励轨迹是否映射到大脑中的价值信号。IRL导出的奖励轨迹与背侧纹状体（常与价值导向的行动选择相关）的活动关联最为显著。它们还与支持其他过程（包括认知控制和感觉运动处理）的分布式区域表现出关联。这种模式表明，IRL奖励捕获了以奖励回路为中心的分布式神经活动，可能反映了价值评估如何与其他过程相互作用。总之，这些发现表明，IRL奖励为自然决策中面向行动的评估提供了行为学基础且时间分辨率的代理指标。

## Abstract
A major challenge for cognitive neuroscience is to explain how value of a goal-directed behavior is computed in complex and naturalistic environments. Standard computational models of decision making have been highly successful in controlled, trial-based paradigms, but they are often ill-suited to real-time behavior unfolding in naturalistic paradigms. Inverse reinforcement learning (IRL) offers a way to infer latent evaluative state from observed behavior in naturalistic environments, but its neural interpretability remains largely unknown. Here, we investigated whether moment-to-moment reward trajectories derived from IRL map onto value signals in the brain during a real-time driving task performed during fMRI scanning. IRL-derived reward trajectories were most robustly associated with activity in the dorsal striatum, a region often linked to value-guided action selection. They also showed associations with distributed regions supporting additional processes, including cognitive control and sensorimotor processing. This pattern suggests that IRL reward captures distributed neural activity centered on the reward circuitry, potentially reflecting how valuation interacts with other processes. Together, these findings suggest that IRL reward provides a behaviorally grounded, temporally resolved proxy for action-oriented valuation during naturalistic decision making.