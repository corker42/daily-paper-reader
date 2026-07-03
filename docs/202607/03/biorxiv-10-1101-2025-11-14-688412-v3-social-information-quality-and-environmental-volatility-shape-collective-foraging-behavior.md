---
title: Social Information Quality and Environmental Volatility Shape Collective Foraging Behavior
title_zh: 社交信息质量和环境波动性塑造集体觅食行为
authors: "Chirkov, V., Kurvers, R. H. J. M., Deffner, D., Romanczuk, P."
date: 2026-06-26
pdf: "https://www.biorxiv.org/content/10.1101/2025.11.14.688412v3.full.pdf"
tags: ["query:fsrh"]
score: 8.0
evidence: 使用多智能体强化学习研究集体觅食行为
tldr: 集体觅食需平衡私人探索与社会信息利用，但信息类型和环境波动性的影响未知。本研究通过多智能体强化学习模型发现，低质量社会线索（如位置）仅能支持稳定环境下的脆弱策略，而高质量社会信息（如报酬）使个体能选择性复制并灵活切换追踪或探索行为。揭示了信息质量与生态背景相互作用是集体行为涌现的关键机制。
source: biorxiv
selection_source: fresh_fetch
motivation: 探究社会信息类型和环境波动性如何共同影响个体决策与群体觅食策略的适应性。
method: 构建空间显式多智能体强化学习模型，系统改变资源波动性与社会线索类型。
result: 低质量社会信息仅在稳定环境有效，高质量信息支持行为多样性并适应波动环境。
conclusion: 信息质量与生态背景的相互作用是决定集体行为涌现的关键机制。
---

## 摘要
集体觅食在动物界广泛存在，使动物能够更有效地发现资源。然而，集体觅食者需要平衡私人探索与使用社交信息之间的关键权衡。社交信息可以以非常不同的形式出现，从简单的位置线索到复杂的收益信息。然而，可用的社交线索类型和环境波动性如何塑造集体觅食行为尚不十分清楚。我们通过一个空间显式模型来解决这个问题，其中智能体通过多智能体强化学习追踪移动资源。智能体在随机探索、私人追踪和社交吸引之间进行选择。我们系统地改变了资源波动性和可用社交线索的类型，以分析它们对个体和集体行为的影响。我们的结果表明，社交信息的质量决定了涌现的集体行为。低质量社交线索（例如位置、动作）导致一种脆弱的策略，该策略在稳定环境中有效，但随着波动性增加而失效。相反，高质量社交信息（例如收益）使行为多样化：智能体选择性模仿他人，并根据环境波动性灵活地在个体追踪或探索之间切换。我们的发现揭示了信息质量与生态背景之间的相互作用是支配从个体决策规则中涌现出不同形式集体行为的重要机制。

## Abstract
Collective foraging is widespread across the animal kingdom, allowing animals to more effectively discover resources. However, collective foragers need to balance a key trade off between private exploration and using social information. Social information can come in very distinct forms, ranging from simple positional cues to complex payoff information. However, how the types of available social cues and environmental volatility shape collective foraging behavior is not well understood. We address this using a spatially-explicit model in which agents track a mobile resource via multi-agent reinforcement learning. Agents choose between random exploration, private tracking, and social attraction. We systematically varied resource volatility and the type of available social cues to analyze their effect on individual and collective behavior. Our results show that the quality of social information dictates the emerging collective behavior. Low-quality social cues (e.g., positions, actions) result in a fragile strategy that is effective in stable environments but fails as volatility increases. Conversely, high-quality social information (e.g., payoffs) enables behavioral diversity: Agents selectively copy others and flexibly change between individual tracking or exploration depending on the environmental volatility. Our findings identify the interplay between information quality and ecological context as an important mechanism governing the emergence of distinct forms of collective behavior from individual decision rules.

---

## 论文详细总结（自动生成）

# 论文详细中文总结

## 1. 核心问题与整体含义（研究动机和背景）

- **核心问题**：集体觅食中个体需要在私人探索（独立搜索）与利用社会信息之间做出权衡。然而，社会信息的形式多样（从简单的位置线索到复杂的收益信息），环境波动性（资源移动速度）也各异，这两者如何共同影响个体决策规则和涌现的集体觅食行为尚不清楚。
- **研究动机**：经典模型通常预设固定的启发式（如“复制成功者”），无法捕捉动物灵活整合多维社会信息的过程。本文利用多智能体强化学习（MARL）让智能体直接从经验中学习最优决策策略，从而揭示信息质量与环境波动性的交互作用如何塑造集体行为。
- **整体含义**：发现社会信息质量是决定集体策略灵活性的关键：低质量信息导致脆弱策略（只适用于稳定环境）；高质量信息则允许行为多样性（选择性复制、灵活切换），使群体能适应高度波动的环境。这为理解动物（乃至人类）集体智能的生态基础提供了机制性见解。

## 2. 论文提出的方法论

- **核心思想**：构建一个空间显式的集体觅食模型，智能体通过MARL优化决策，以追踪一个做相关随机游走的移动资源。系统改变资源速度（环境波动性）和智能体可获取的社会线索类型（信息质量），观察涌现的个体和集体行为。
- **关键技术细节**：
  - **环境与资源**：连续二维 20×20 区域，资源按照相关随机游走移动，步长服从截断帕累托分布（产生偶尔的长距离位移，类似 Levy 行走）。资源速度 `v_resource` 设为 0.1、0.3、0.5 倍于智能体最大速度 `v_max`。
  - **智能体动作空间**：三个离散动作——① 随机探索（相关随机游走，全速）；② 私人追踪（以概率 `p_track=0.1` 向资源中心移动，否则静止，模拟成本和减速）；③ 社会吸引（全速向观察到的某个同伴移动）。
  - **智能体观测**：五维向量，包括自身奖励、同伴是否存在、到同伴的距离、同伴上一时刻的动作、同伴上一时刻的带噪声奖励。社会信息条件逐步添加这些特征（从仅私有到包含全部且噪声递减）。
  - **训练算法**：采用多智能体近端策略优化（MAPPO），集中训练（共享策略网络参数、使用全局信息的批评家）分散执行（测试时仅用局部观测）。网络为两层 256 单元的 MLP，tanh 激活。
  - **奖励函数**：`r_i(t) = 1 / (1 + d_i^2)`，其中 `d_i` 是智能体与资源的欧氏距离，激励靠近资源。

## 3. 实验设计

- **数据集 / 场景**：全部为模拟场景，无真实数据集。场景由两个因子交叉构成：
  - 资源速度（3 级）：慢（0.1×v_max）、中（0.3×v_max）、快（0.5×v_max）。
  - 社会信息质量（7 级）：仅私有、+距离、+动作、+高噪声报酬（σ=0.1）、+中等噪声（σ=0.05）、+低噪声（σ=0.01）、+无噪声。
- **Benchmark / 对比方法**：本文未与其他经典模型（如生产者-消费者模型、固定启发式策略）直接进行定量比较，而是通过系统内部比较不同信息条件和资源速度下的表现。此外，进行了三类鲁棒性分析：
  - 追踪成本变化（有效追踪速度：0.05、0.2、0.3 倍 v_max）。
  - 去中心化训练（IPPO）。
  - 视觉范围减小（15、10、5、1 单位）。
- **评价指标**：归一化奖励（实际奖励/最大可能奖励）、行为概率分布、动作概率热图。

## 4. 资源与算力

- **GPU 型号**：单个 NVIDIA A100 或 V100S GPU。
- **训练时长**：每次运行平均 17.9 小时（标准差 1.8 小时）。
- **训练迭代**：每个条件 480 次迭代，每次迭代收集 500,000 个环境帧（即 500 个 episode，每 episode 1000 步），总计 2.4 亿环境交互。
- **种子数量**：每个条件使用 7 个独立随机种子。
- **总运行次数**：主要实验 21 个条件（7 信息 × 3 速度）× 7 种子 = 147 次；鲁棒性实验另有总计约 7+7+3 个条件（追踪成本 3 水平 × 7 种子、去中心 21×7、视觉范围 3 水平无多种子，但文中说明去中心也用了 7 种子），总运行次数超过 200 次。

## 5. 实验数量与充分性

- **主要实验**：7 信息质量 × 3 资源速度 × 7 种子 = 147 组独立训练，每组有 5000 评估 episode（共约 73.5 万评估 episode），统计了 95% 置信区间，充分性良好。
- **鲁棒性实验**：
  - 追踪成本（3 种水平，覆盖从低成本到高成本），7 种子。
  - 去中心化训练（IPPO），覆盖全部 21 个条件，7 种子。
  - 视觉范围（3 种减小的范围，各 1 种子）。
- **策略一致性分析**：对每个条件的 7 个种子进行行为向量余弦相似度聚类，排除罕见的不一致种子（仅约 3.5%），确保报告的是主流策略。
- **充分性评价**：实验设计系统、全面，覆盖了信息质量和环境波动性的主要组合，并检验了关键建模假设的敏感性。但局限在于全部为模拟实验，缺乏真实动物行为数据验证。对比方法仅为自己内部，未与经典模型（如 “copy-the-majority” 等）做定量对比，可能削弱了外部参考价值。

## 6. 论文的主要结论与发现

1. **社会信息的价值高度依赖环境波动性**：在稳定环境中，低级线索（距离、动作）即可大幅提升表现；在波动环境中，只有高质量报酬信息才能持续有效，且噪声极低时不必要，中等噪声（σ=0.05）已足够。
2. **低质量社会信息导致“凝聚追踪”（Cohesive Tracking）策略**：群体主要依赖昂贵的私人追踪，辅以非选择性社会吸引以保持紧密集群，在稳定环境中表现优异，但随着波动增加迅速下降。
3. **高质量报酬信息催生灵活的两种策略**：
   - **追踪-复制（Track-or-Copy）**：当私人追踪可行时，默认追踪，当观察到更成功的同伴时复制之。
   - **探索-复制（Explore-or-Copy）**：当追踪不可行（高波动或高成本），放弃追踪改为随机探索，仍利用报酬线索选择性聚集于成功个体，形成分布式集体感知。
4. **策略选择由追踪可行性驱动**：追踪可行性由有效追踪速度与资源速度之比决定；改变内部成本或外部波动均可触发策略切换，验证了机制的稳健性。
5. **分散训练降低了凝聚追踪策略的协调性**：去中心化训练下，低级信息条件表现显著下降，群体依赖个体追踪而失去凝聚力；高质量信息条件则受影响较小。

## 7. 优点

- **方法新颖**：使用多智能体强化学习让策略从经验中涌现，避免了预定义启发式的局限性，能够发现反直觉的优化策略（如 “Explore-or-Copy” 的分布式感知）。
- **系统化参数扫描**：同时改变信息质量和环境波动性两个关键维度，并做三维热图可视化，清晰揭示了交互效应。
- **深入的鲁棒性分析**：检验了追踪成本、去中心化训练、视觉范围等假设，增强了结论的可靠性。
- **策略可视化直观**：通过动作概率热图和轨迹快照，生动展示了不同策略下的个体决策规则和群体空间模式，有助于理解机制。
- **统计严谨**：多随机种子、策略一致性筛选、置信区间报告，减少了偶然性影响。

## 8. 不足与局限

- **模型简化限制了生态真实性**：
  - 智能体无记忆（仅依赖当前观测），无法整合时序信息或学习资源轨迹。
  - 每次只能随机观察一个同伴，不能同时聚合多个同伴信息，且假设均匀采样（实际动物常偏重近邻）。
  - 资源为单个移动目标，未考虑多资源、竞争、资源消耗等现实因素。
- **社会信息获取成本被低估**：论文假设社会吸引的成本低于私人追踪，但实际中评估同伴的报酬可能需要额外时间和认知开销；若获取成本高，可能改变策略选择。
- **缺乏与经典模型或实证数据的定量对比**：只展示了内部比较，未与生产者-消费者模型、信息级联模型等对比，也未用真实动物数据进行校准或验证，削弱了预测的可落地性。
- **集中训练假设与实际不符**：集中训练共享参数可能产生不现实的合作行为；尽管去中心实验验证了部分鲁棒性，但性能下降表明凝聚策略对学习算法敏感。
- **异质性未被充分探索**：智能体初始同质，未引入个体差异或角色分工（如明确的领导者/跟随者），而现实群体中常存在异质性。
- **应用限制**：结论主要适用于追踪单个移动资源的场景，难以直接推广到资源斑块分布、群体迁徙、人类社交网络等更复杂情境。

（完）
