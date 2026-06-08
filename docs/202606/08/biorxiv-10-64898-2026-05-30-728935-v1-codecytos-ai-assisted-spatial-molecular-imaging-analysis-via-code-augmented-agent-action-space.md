---
title: "CodeCytos: AI-assisted spatial molecular imaging analysis via code-augmented agent action space"
title_zh: CodeCytos：通过代码增强的智能体行动空间实现AI辅助空间分子成像分析
authors: "Vo, H. Q., Ly, S. T., Wan, Z., Nguyen, A.-V., Zhao, H., Sheng, J., Wong, S. T. C., Nguyen, H. V."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.30.728935v1.full.pdf"
tags: ["query:retina-agent"]
score: 6.0
evidence: 代码增强代理框架用于空间分子成像，类比医疗中的代理系统
tldr: 传统组织图像分析工具依赖手动干预，且仅支持固定特征，难以适应复杂空间研究。CodeCytos提出基于代码的推理智能体框架，实现动态可编程的空间分子成像分析。在四个不同组织数据集上，该框架在无任务特定提示下优于基线方法，且引入领域无关的少量编码推理示例可显著提升性能。该工作展示了代码动作智能体在加速空间特征探索和生物标志物发现中的潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间成像分析工具缺乏自动化和定制化能力，难以高效探索复杂组织中的自定义细胞特征。
method: 提出CodeCytos，一种基于代码增强的智能体框架，通过编程式交互实现动态、可定制的空间分子成像数据分析。
result: 在四个专家标注数据集上，CodeCytos在最小提示设置下优于基线，且加入领域无关的少量示例可进一步提升性能。
conclusion: 代码动作智能体能有效辅助空间分子成像的定制特征探索，加速生物标志物发现过程。
---

## 摘要
传统的组织图像分析软件为细胞分析提供了基础功能，包括分割、基本形态特征提取和空间组织分析。然而，这些工具通常需要人工干预，并且与代码驱动的自动化集成不佳，限制了复杂空间组织研究的效率和可扩展性。此外，它们在自定义分析方面提供的灵活性有限，通常仅支持一组固定的预实现空间细胞特征。为了解决这些限制，我们提出了CodeCytos，这是一个基于编码的推理智能体框架，能够实现与空间分子成像数据的动态、可编程交互，以提高自动化和定制化能力。CodeCytos旨在简化自定义空间细胞特征的探索，并适应多样化的研究需求。我们通过对来自四种不同组织类型（额叶皮层、非小细胞肺癌、胰腺和扁桃体）的四个专家策划数据集进行案例研究，展示了其实用性。我们在现实的最小提示设置下评估CodeCytos，其中生物科学家提出简单问题，没有任务特定的指令或关于空间细胞分析的上下文信息，并基准测试了多个具有强大编码能力的LLM骨干网络。我们进一步表明，整合定制的、领域无关的少量样本上下文编码推理示例（空间分析领域外随机采样的演示）可以在不需要昂贵、专家制作的领域内演示的情况下显著提高性能。总体而言，CodeCytos优于基线方法，凸显了代码行动智能体在空间分子成像中辅助自定义特征探索和加速生物标志物发现的潜力。

## Abstract
Conventional tissue image analysis software provides foundational capabilities for cellular analysis, including segmentation, basic morphological feature extraction, and spatial organization analysis. However, these tools often require manual intervention and are not well integrated with code-driven automation, limiting efficiency and scalability for complex spatial tissue studies. In addition, they offer limited flexibility for custom analyses, as they typically support only a fixed set of pre-implemented spatial cellular features. To address these limitations, we propose CodeCytos, a coding-based reasoning agent framework that enables dynamic, programmable interaction with spatial molecular imaging data, to improve automation and customization. CodeCytos is designed to streamline the exploration of custom spatial cellular features and adapt to diverse research needs. We demonstrate its utility through case studies on four expert-curated datasets from distinct tissue types: frontal cortex, non-small-cell lung cancer, pancreas, and tonsil. We evaluate CodeCytos under a realistic minimal prompt setting, where bioscientists pose simple questions without task-specific instructions or contextual information about spatial cellular analysis, and benchmark multiple LLM backbones with strong coding capabilities. We further show that incorporating tailored, domain-agnostic few-shot in-context coding-reasoning examples (randomly sampled demonstrations outside the spatial analysis domain) can substantially improve performance without requiring costly, expert-crafted in-domain demonstrations. Overall, CodeCytos outperforms baseline approaches, highlighting the potential of code-action agents to assist with custom feature exploration in spatial molecular imaging and to accelerate biomarker discovery.