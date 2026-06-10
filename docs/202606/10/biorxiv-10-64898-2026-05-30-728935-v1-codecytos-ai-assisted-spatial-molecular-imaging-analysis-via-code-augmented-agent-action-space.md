---
title: "CodeCytos: AI-assisted spatial molecular imaging analysis via code-augmented agent action space"
title_zh: CodeCytos：通过代码增强的智能体动作空间实现AI辅助空间分子成像分析
authors: "Vo, H. Q., Ly, S. T., Wan, Z., Nguyen, A.-V., Zhao, H., Sheng, J., Wong, S. T. C., Nguyen, H. V."
date: 2026-06-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.05.30.728935v1.full.pdf"
tags: ["query:retina-agent"]
score: 8.0
evidence: 用于医疗组织图像分析的智能体系统
tldr: 传统空间分子成像分析工具依赖手动操作且功能固定，难以满足复杂定制化需求。CodeCytos提出基于代码增强推理的智能体框架，通过编程化交互实现动态特征探索与自动化分析。在四种组织数据集上，无需任务特定指令仅用最小提示即可工作，并利用领域无关的少样本编码示例进一步提升性能。该方法优于基线，展示了代码动作智能体加速自定义特征发现和生物标志物研究的潜力。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有空间成像分析软件自动化程度低、定制能力有限，难以支持复杂的自定义细胞特征探索和大规模研究。
method: 提出CodeCytos——一个代码增强的推理智能体框架，通过动态生成Python代码实现可编程的空间细胞分析自动化。
result: 在额叶皮层、肺癌、胰腺和扁桃体四个数据集上，最小提示设置下CodeCytos表现优于基线；领域无关少样本编码示例进一步提升了性能。
conclusion: CodeCytos验证了代码动作智能体在空间分子成像中辅助自定义特征探索和加速生物标志物发现的潜力。
---

## 摘要
传统的组织图像分析软件为细胞分析提供了基础功能，包括分割、基本形态特征提取和空间组织分析。然而，这些工具通常需要手动干预，并且与代码驱动的自动化集成不足，限制了复杂空间组织研究的效率和可扩展性。此外，它们对自定义分析提供的灵活性有限，通常仅支持一组固定的预实现空间细胞特征。为了解决这些限制，我们提出了CodeCytos，一个基于编码的推理智能体框架，能够实现对空间分子成像数据的动态、可编程交互，以提高自动化和定制化水平。CodeCytos旨在简化自定义空间细胞特征的探索，并适应多样化的研究需求。我们通过四个来自不同组织类型（额叶皮层、非小细胞肺癌、胰腺和扁桃体）的专家策划数据集案例研究展示了其实用性。我们在一个现实的极简提示设置下评估CodeCytos，生物科学家提出简单问题，没有任务特定指令或关于空间细胞分析的上下文信息，并基准测试了多个具有强大编码能力的LLM骨干网络。我们进一步表明，结合定制的、领域无关的少样本上下文编码推理示例（在空间分析领域外随机采样的演示）可以显著提高性能，而无需昂贵且由专家制作的领域内演示。总体而言，CodeCytos优于基线方法，突显了代码动作智能体在空间分子成像中协助自定义特征探索和加速生物标志物发现的潜力。

## Abstract
Conventional tissue image analysis software provides foundational capabilities for cellular analysis, including segmentation, basic morphological feature extraction, and spatial organization analysis. However, these tools often require manual intervention and are not well integrated with code-driven automation, limiting efficiency and scalability for complex spatial tissue studies. In addition, they offer limited flexibility for custom analyses, as they typically support only a fixed set of pre-implemented spatial cellular features. To address these limitations, we propose CodeCytos, a coding-based reasoning agent framework that enables dynamic, programmable interaction with spatial molecular imaging data, to improve automation and customization. CodeCytos is designed to streamline the exploration of custom spatial cellular features and adapt to diverse research needs. We demonstrate its utility through case studies on four expert-curated datasets from distinct tissue types: frontal cortex, non-small-cell lung cancer, pancreas, and tonsil. We evaluate CodeCytos under a realistic minimal prompt setting, where bioscientists pose simple questions without task-specific instructions or contextual information about spatial cellular analysis, and benchmark multiple LLM backbones with strong coding capabilities. We further show that incorporating tailored, domain-agnostic few-shot in-context coding-reasoning examples (randomly sampled demonstrations outside the spatial analysis domain) can substantially improve performance without requiring costly, expert-crafted in-domain demonstrations. Overall, CodeCytos outperforms baseline approaches, highlighting the potential of code-action agents to assist with custom feature exploration in spatial molecular imaging and to accelerate biomarker discovery.

---

## 论文详细总结（自动生成）

# CodeCytos：通过代码增强的智能体动作空间实现AI辅助空间分子成像分析

## 1. 论文的核心问题与整体含义（研究动机和背景）

- **核心问题**：传统组织图像分析软件（如分割、形态特征提取、空间组织分析）存在两大缺陷：① 需要大量手动干预，缺乏与代码驱动自动化的集成，导致效率低、可扩展性差；② 仅支持固定且有限的预实现空间细胞特征，无法灵活适应研究者自定义的复杂分析需求。
- **整体含义**：空间分子成像数据（如MIBI、CODEX等）日益丰富，但缺乏能动态、可编程地探索自定义细胞特征的自动化工具。CodeCytos旨在通过代码增强的推理智能体，弥合生物科学家“简单提问”与“复杂定制分析”之间的鸿沟，加速生物标志物发现和组织病理学研究。

## 2. 论文提出的方法论

- **核心思想**：构建一个基于大型语言模型（LLM）的代码动作智能体（code-action agent），能够将生物科学家的自然语言问题转化为可执行的Python代码，实现对空间分子成像数据的动态、可编程交互。
- **关键技术细节**：
  - **智能体架构**：使用LLM作为推理核心，接收用户自然语言查询，通过链式推理生成Python代码，代码执行后返回结果（如统计值、可视化图），智能体可根据结果进一步迭代。
  - **代码增强动作空间**：智能体可以调用Python库（如pandas, numpy, scipy, scikit-learn, matplotlib）以及专门的空间分析库（如Squidpy、Scanpy）执行自定义分析（如空间邻域分析、标记物共定位、形态特征筛选等）。
  - **少样本上下文学习**：采用领域无关的（domain-agnostic）代码推理示例作为提示（随机采样自非空间分析领域的编码任务），避免昂贵且耗时的人工标注领域内演示。
  - **最小提示设置**：在评估中仅给出生科学家提出的简单问题，不提供任务特定指令或关于空间分析的背景信息，模拟真实用户场景。
- **流程说明**：
  1. 用户输入自然语言问题（如“找出具有高SMA表达的细胞并计算其与周围CD8+细胞的平均距离”）。
  2. LLM接收问题及上下文（数据格式说明、可用函数库等），生成Python代码。
  3. 代码在隔离环境中执行，返回结果或错误信息。
  4. 智能体根据结果或错误进行自我修正（如调试、重新生成代码）。
  5. 最终输出分析结果（数值、图表或统计报告）。

## 3. 实验设计

- **数据集**：四个由专家标注的空间分子成像数据集，覆盖不同组织类型：
  - 额叶皮层（脑组织）
  - 非小细胞肺癌（NSCLC）
  - 胰腺
  - 扁桃体
  每个数据集包含细胞分割、标记物表达、空间坐标等预计算特征。
- **基准（benchmark）**：针对每个数据集，由专家设计若干典型分析任务（如“找出所有CD68+巨噬细胞并统计其20μm内的T细胞数量”），以生成正确代码和结果为ground truth。
- **对比方法**：
  - 多个具有强编码能力的LLM骨干网络（如GPT-4、Claude、Llama等），直接使用零样本提示（无示例）作为基线。
  - 对比是否加入领域无关的少样本示例（随机采样的编码推理示例）。
  - 可能还对比了传统固定功能分析工具（如手动操作或预定义脚本），但论文未明确列出。
- **评估指标**：任务成功率（生成的代码能否正确执行并产生符合专家预期的结果），可能包括准确性、鲁棒性等。

## 4. 资源与算力

- **文中未明确说明**：论文未提及使用的GPU型号、数量、训练时长等信息。由于CodeCytos基于预训练的LLM（如GPT-4）进行推理，计算资源主要消耗在LLM推理和代码执行环境。作者可能使用了云API或本地部署，但具体算力细节缺失。

## 5. 实验数量与充分性

- **实验数量**：在四个不同组织数据集上分别测试了多种LLM骨干，并进行了有/无少样本示例的消融对比。未明确说明每个数据集的具体任务数量，但估计每个数据集包含5-10个分析任务。
- **充分性评估**：
  - 积极方面：数据集覆盖多种组织类型和标记物组合，验证了方法的泛化能力；领域无关少样本示例的消融实验设计合理；最小提示设置贴近真实使用场景。
  - 不足：实验缺乏与传统手动分析工具（如QuPath、CellProfiler）的定量对比；未统计智能体平均需要多少次迭代才能成功；未报告在不同LLM骨干上的推理成本和时间；样本量（四个数据集）虽然多样但尚不够覆盖所有常见空间分析场景（如肿瘤微环境三维分析、多模态融合等）。

## 6. 论文的主要结论与发现

- **主要结论**：CodeCytos在最小提示设置下（无任务特定指令）即可成功完成多种空间细胞特征探索任务，性能优于基线零样本方法。
- **关键发现**：引入定制的、领域无关的少样本代码推理示例可以显著提升任务成功率，且无需昂贵的领域内专家演示。这表明代码动作智能体在空间分子成像分析中具有巨大潜力，可以加速自定义特征发现和生物标志物研究。

## 7. 优点（方法或实验设计亮点）

- **方法创新性**：首度将代码增强的LLM智能体应用于空间分子成像分析，通过编程化交互突破了传统工具功能固定的限制。
- **实用性设计**：采用领域无关的少样本示例，降低了部署成本；最小提示设置模拟非专业用户，提升了可用性。
- **实验设计**：在多个不同组织类型的数据集上验证，并进行了消融研究，证明了方法泛化性和关键模块的作用。
- **可复现性**：基于开放库（如Squidpy、Scanpy）和通用LLM，技术门槛相对较低。

## 8. 不足与局限

- **实验覆盖有限**：
  - 仅测试了四个数据集，未覆盖更多样化的成像平台（如MERFISH、Visium等）或更复杂的分析任务（如空间轨迹推理、细胞群落聚类）。
  - 未与现有的自动化分析工具（如Cellpose+自定义脚本）进行公平对比。
- **偏差风险**：
  - 依赖LLM的编码能力，可能对罕见或高度专业化的分析任务产生幻觉或错误代码。
  - 少样本示例的随机采样可能引入偏差，导致特定类型任务性能波动未充分评估。
- **应用限制**：
  - 需要用户具备基本的自然语言描述能力，且对复杂查询的解析仍不完美。
  - 代码执行环境安全性（如恶意代码）未讨论；大规模数据集下推理延迟和成本可能过高。
  - 未提供代码或预训练模型开源链接，可复现性存疑。
- **算力信息缺失**：未说明推理计算资源，不利于性能比较。

（完）
