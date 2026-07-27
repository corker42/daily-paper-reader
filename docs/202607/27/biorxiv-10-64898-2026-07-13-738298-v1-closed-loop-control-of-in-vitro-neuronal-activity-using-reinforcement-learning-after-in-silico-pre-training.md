---
title: Closed-loop control of in vitro neuronal activity using reinforcement learning after in silico pre-training
title_zh: 基于硅内预训练的强化学习闭环控制体外神经元活动
authors: "Carvalho, E., Mateus, J. C., Pinto, R., Aroso, M., Aguiar, P."
date: 2026-07-20
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.13.738298v1.full.pdf"
tags: ["query:fsrh"]
score: 8.0
evidence: 强化学习用于体外神经元活动的闭环控制，结合硅预测练
tldr: 生物神经网络复杂非平稳，传统方法难以推导最优控制策略。本研究通过强化学习在生物物理校准的数字孪生模型中预训练，再转移到体外培养的神经元网络，实现了对网络爆发的状态依赖控制。迁移策略不仅优于启发式控制，且刺激使用更为高效。钙成像揭示其机制在于空间和时间上的优化，利用了局部网络拓扑和内在生理动态。这一方法为基于强化学习的神经调控提供了可行方案。
source: biorxiv
selection_source: fresh_fetch
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738298-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1913, \"height\": 964, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738298-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1876, \"height\": 1619, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738298-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1915, \"height\": 1068, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-13-738298-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1892, \"height\": 1844, \"label\": \"Figure\"}]"
motivation: 推导最优刺激控制策略因生物网络复杂非平稳而困难，传统强化学习探索对组织有害。
method: 在生物物理校准的数字孪生模型中预训练强化学习策略，然后迁移到体外培养神经元网络进行闭环控制。
result: 迁移策略优于启发式控制，刺激使用受限，钙成像揭示其利用网络拓扑和时间动态进行时空优化。
conclusion: 证明了数字孪生预训练到活体网络的转移策略可行，为基于强化学习的神经调控提供了新范式。
---

## 摘要
利用电刺激控制特定的神经元动力学对于治疗性神经调控至关重要，但由于生物神经网络复杂且非平稳的特性，推导最优控制策略仍然具有挑战性。虽然强化学习提供了强大的闭环控制框架，但它依赖于长时间的刺激驱动探索，这与活体组织的生理限制难以协调。在此，我们展示了一种从硅内到体外的迁移策略，能够实现对培养神经元网络爆发的有效状态依赖控制。迁移后的策略优于启发式控制，同时保持了受限的刺激使用。同步钙成像揭示了所学策略的机制基础：智能体在空间和时间上优化刺激，利用局部网络拓扑和内在的生理时间动力学。这些结果确立了体外芯片大脑培养作为基于强化学习的神经调控的可行垫脚石，并证明可以在生物物理校准的数字孪生中推导出有效的控制策略，并直接迁移到活体网络中。

## Abstract
Controlling specific neuronal dynamics with electrical stimulation is critical for therapeutic neuromodulation, yet deriving optimal control policies remains challenging due to the complex and non-stationary nature of biological neuronal networks. While reinforcement learning (RL) offers a powerful closed-loop control framework, its reliance on prolonged stimulus-driven exploration is difficult to reconcile with the physiological limits of living tissue. Here, we demonstrate an in silico-to-in vitro transfer strategy that achieves efficient state-dependent control of network bursting in cultured neurons. The transferred policy outperforms heuristic controls, while maintaining constrained stimulation usage. Concurrent calcium imaging reveals the mechanistic basis of the learned policy: the agent optimizes stimulation spatially and temporally, exploiting local network topology and intrinsic physiological temporal dynamics. These results establish in vitro brain-on-chip cultures as a tractable stepping stone for RL-based neuromodulation and demonstrate that effective control policies can be derived in biophysically calibrated digital twins and transferred directly to living networks.