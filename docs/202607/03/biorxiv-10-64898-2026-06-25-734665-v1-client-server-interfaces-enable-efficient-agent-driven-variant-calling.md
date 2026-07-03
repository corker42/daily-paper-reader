---
title: Client-server interfaces enable efficient agent-driven variant calling
title_zh: 客户端-服务器接口实现高效的智能体驱动变异检测
authors: "Yu, X., Zheng, Z., CHEN, L., QIn, Z., Guo, X., He, M., Luo, R."
date: 2026-06-28
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.25.734665v1.full.pdf"
tags: ["query:fsrh"]
score: 8.0
evidence: 基于LLM代理的医疗变异检测
tldr: LLM代理驱动生物信息学工具时，因工具面向人类设计导致大量开销。为此，将深度学习变异检测工具Clair3重构为客户端-服务器系统Clair3-Connect，客户端处理基因组数据并暴露模式定义的代理工具，服务器仅做神经网络推理。在APOE双倍型分型任务中，所有60次代理运行均正确，令牌使用量降至外壳驱动基线的6.8–14倍，且更稳定。重新设计为代理友好接口可提升效率和可靠性，应作为工具开发的一等产出。
source: biorxiv
selection_source: fresh_fetch
motivation: 现有生物信息学工具面向人类专家，LLM代理驱动时需大量交互和令牌，效率低下。
method: 将Clair3重构为客户端-服务器架构，客户端暴露模式定义的代理工具，服务器仅做推理，特征张量传输，基因组标识留在客户端。
result: "APOE分型任务中代理100%正确，令牌使用量降至12K（3回合），仅为外壳驱动基线的6.8–14倍，时间减少约75%，令牌波动从35%降至4%。"
conclusion: 为算法设计代理接口比第三方封装更高效可靠，应成为生物信息学工具开发的一等产出。
---

## 摘要
背景：大型语言模型（LLM）智能体越来越多地自动化生物信息学分析，但大多数现有生物信息学工具是为人类专家独立使用而构建的。驱动此类工具的智能体必须从面向人类的文档中推理其安装、配置和执行，每次结果需要多次交互、大量令牌和工具调用。因此，方法暴露给智能体的方式可能与方法本身同样重要。通过为这些工具设计智能体接口，智能体可以减少此类开销并提高智能体驱动分析的可靠性。

结果：为测试这一设计，我们将广泛使用的基于深度学习的长读长变异检测工具Clair3重新架构为客户端-服务器系统Clair3-Connect。客户端执行所有基因组学相关处理并持有可识别数据。服务器仅运行神经网络推理，客户端仅向服务器发送特征张量，而样本标识符和基因组上下文保留在客户端。客户端暴露了由模式定义、面向智能体的工具，智能体通过单次结构化调用进行调用。在APOE双倍型分型任务中，所有60次智能体运行均正确。智能体工具在3次交互中使用了12K令牌，比基于shell的基线（81K-163K令牌）少6.8至14倍，耗时约为四分之一，且稳定性更高（令牌使用量变异4%对比35%）。为保持客户端轻量化而省略堆积和分阶段处理，在50倍覆盖率下，SNP F1值比标准Clair3低0.1-0.3个百分点，而相互TLS和AES-256-GCM加密使端到端运行时间增加了7.2%。

结论：将成熟的算法重构为开发者构建的、位于安全客户端-服务器边界后的智能体工具，使其比第三方封装更高效、可靠且更易于为LLM智能体部署，因为第三方封装无法恢复仅其开发者知道的默认值和约定。智能体接口应成为生物信息学工具开发的一级交付物。

## Abstract
BackgroundLarge language model (LLM) agents increasingly automate bioinformatics analyses, but most existing bioinformatics tools were built for standalone use by human experts. An agent driving such a tool must reason about its installation, configuration, and execution from documentation for human, spending many turns, tokens, and tool calls per result. How a method is exposed to an agent can therefore matter as much as the method itself. By designing agentic interfaces for these tools, agent can reduce such overhead and improve the reliability of agent-driven analyses.

FindingsTo test this design, we re-architected Clair3, a widely used deep-learning-based long-read variant caller, into a client-server system, Clair3-Connect. The client performs all genomics related processing and holds the identifiable data. The server runs only neural-network inference, and the client sends only feature tensors to the server, while sample identifiers and genomic context remain on the client. The client exposes schema-defined agent-facing tools that an agent invokes through single structured calls. On an APOE diplotyping task, all 60 agent runs were correct. The agentic tools used 12K tokens in 3 turns, 6.8 to 14 times fewer tokens than the shell-driven baselines (81K-163K tokens), at about a quarter the wall-clock time and far more stably (4% versus 35% token usage variation). Dropping the pileup and phasing stages to keep the client light left SNP F1 within 0.1-0.3 points of standard Clair3 by 50x coverage, while mutual TLS and AES-256-GCM encryption added 7.2% to end-to-end runtime.

ConclusionsRecasting an established algorithm as developer-built, agentic tools behind a secure client-server boundary makes it more efficient, reliable, and easier to deploy for an LLM agent than a third-party wrapper, which cannot recover the defaults and conventions only its developers know. Agentic interfaces should be a first-class deliverable of bioinformatics tool development.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）

- **背景**：大型语言模型（LLM）智能体越来越多地被用于自动化生物信息学分析流程，但现有生物信息学工具（如变异检测器）几乎都是为**人类专家**设计的命令行程序。智能体驱动这些工具时，需要从面向人类的文档中推理安装、配置、参数、输出格式等，导致多次交互、大量令牌消耗和不可靠的解析。
- **核心问题**：方法的**暴露方式**（接口设计）对智能体的效率和可靠性影响巨大，甚至与方法本身同等重要。现有研究缺乏对生物信息学工具如何设计**智能体友好接口**的系统性探讨。
- **整体含义**：提出应把“智能体接口”作为工具开发的一等交付物，而不仅仅是事后添加的简单包装。通过重新设计接口（如结构化工具调用、客户端-服务器架构），可以显著降低智能体的开销并提高稳定性，同时保护数据隐私。

### 2. 论文提出的方法论：核心思想、关键技术细节

- **核心思想**：将现有的深度学习变异检测工具 **Clair3** 重构为**客户端-服务器系统 Clair3-Connect**，在客户端暴露**模式定义的智能体工具**（typed tools），服务器仅运行神经网络推理，客户端与服务器之间只传输**特征张量**（不包含样本标识符、基因组坐标等上下文）。
- **关键技术细节**：
  - **架构**：客户端负责读取比对文件、选择候选变异位点、构建 Clair3 全比对特征张量，并解码返回的概率为 VCF 输出；服务器使用 libtorch 加载 Clair3 模型（TorchScript），接收张量并返回每个位点的基因型概率。
  - **智能体工具**：客户端通过 gRPC 暴露三个结构化工具——`bam_header`（读取测序平台）、`discover_models`（发现可用模型）、`genotypes_at`（查询指定位置的基因型）。智能体只需一次结构化调用即可完成一个步骤，无需解析文本输出。
  - **隐私保护**：服务器不接收文件路径、样本名、坐标等，仅接收特征张量（int8 数组）。传输层支持 **mTLS**（信道加密）和 **AES-256-GCM**（每载荷加密），确保数据在传输中的机密性和完整性。
  - **轻量客户端**：去掉了标准 Clair3 的 piledup 模型和 reads phasing 阶段，仅使用全对齐模型，以减少客户端计算依赖（无需 GPU、深度学习运行时）。这引入了准确率权衡（主要在低覆盖度和高错误率数据上），但大幅降低了客户端资源需求。

### 3. 实验设计：数据集、基准、对比方法

- **任务与数据集**：
  1. **APOE 双倍型分型任务**：使用两个全基因组样本（HG00136、HG00150），聚焦于 chr19 上的两个 SNP（rs429358、rs7412）。智能体需推断测序平台（从 BAM 头获取）、选择对应模型、调用变异并组合双倍型。共 60 次独立运行（每个条件×每个样本×10 重复）。
  2. **变异检测准确率基准**：使用 HG003（训练集外样本）的三个平台数据——Illumina NovaSeq、Oxford Nanopore、PacBio HiFi Revio，分别在 chr1 和 chr20 上做 5 个覆盖度（10×、20×、30×、40×、50×）的滴定实验。对比**标准 Clair3**（完整管道）与**全对齐仅客户端（Clair3-Connect 默认配置）** ，使用 GIAB v4.2.1 基准和 hap.py 评估 SNP/Indel 的 F1、召回率、精度。
  3. **传输安全成本测量**：在同一主机（128核 CPU + 1×RTX 4090）上，使用 HG003 Oxford Nanopore chr20 的数据，测量四种传输配置（明文、mTLS、AEAD、mTLS+AEAD）的每请求延迟和端到端耗时。
- **对比方法**：
  - **智能体接口对比**：三种暴露方式：RawBinary（仅 shell）、Skills（shell + 专家技能文档）、Tools（仅结构化工具）。固定智能体模型为 `deepseek-v4-pro`，任务提示相同。
  - **变异检测准确率**：标准 Clair3 vs 全对齐仅客户端。

### 4. 资源与算力

- **推理服务器**：使用 1 块 **NVIDIA RTX 4090** GPU，主机为 128 核 CPU。服务器加载 TorchScript 模型进行推理，支持动态批处理（最大64张量或4ms等待）。
- **客户端**：无需 GPU，无需深度学习运行时（如 PyTorch），仅使用 Rust 编写的基因组处理模块。
- **训练资源**：论文未涉及模型训练，仅使用已训练好的 Clair3 检查点（导出为 TorchScript）。因此无训练算力消耗。
- **实验硬件**：所有端到端和延迟测量在单机 loopback 上进行，排除网络延迟。

### 5. 实验数量与充分性

- **智能体接口实验**：60 次独立运行（2 样本 × 3 条件 × 10 重复），覆盖率足够。但样本数量较少（仅两个），且任务单一（APOE 双倍型，仅两个位点），可能难以泛化到更复杂的工作流。
- **变异检测准确率实验**：1 个样本（HG003）、3 个平台、2 条染色体、5 个覆盖度，形成 30 个配置点。每个配置未明确重复次数（推测为单次，因为 hap.py 分析通常不需要多次），但表 1 中的客户端运行时使用了 10 次重复。整体实验规模中等，但缺少多个样本（如 GIAB 其余样本）和全基因组评估，存在偏差风险。
- **传输安全实验**：10 次配对重复，使用 Wilcoxon 检验，统计严谨。
- **消融实验**：部分存在（如去掉 pileup 和 phasing 的影响），但未深入分析不同客户端设计选择（如不同张量压缩策略、批处理大小）的影响。
- **总体**：实验设计较为合理，但覆盖范围有限，尤其在智能体任务多样性和变异检测样本多样性上不足。

### 6. 论文的主要结论与发现

1. **智能体接口显著提升效率与稳定性**：在 APOE 任务中，Tools 接口仅用 12K tokens、3 次交互，而 RawBinary 和 Skills 分别需要 81K/163K tokens、10/7.5 次交互。智能体工具接口的 token 使用变异仅为 4%，远低于 shell 基线的约 35%。所有 60 次运行结果均正确。
2. **轻量客户端在中等以上覆盖度下准确率接近标准 Clair3**：在 30×以上覆盖度，SNP F1 差距小于 1 个百分点；50×时仅 0.1-0.3 个百分点。但在低覆盖度（10×）和 ONT 数据上，Indel 差距仍可达 4-8 个百分点。
3. **传输安全开销可控**：AEAD 加密每请求增加约 7.4 ms，但在端到端流程中（CPU 瓶颈为主）仅增加 7.2%（约 2 秒），可被实际部署接受。
4. **开发者构建的 agentic tools 优于第三方包装**：因为只有开发者知道工具默认值、缺失记录约定等“操作语义”，这些难以从命令行输出中自动推导。例如，Clair3 默认不输出参考位点，shell 代理需依赖提示中的特殊约定才能正确推断，而 Tools 接口直接返回显式 0/0 基因型。

### 7. 优点：方法或实验设计上的亮点

- **创新性**：首次系统性地将经典生物信息学工具重构为具有结构化、模式化接口的客户端-服务器系统，专门为 LLM 智能体设计，而不是简单包装。
- **隐私保护设计**：通过仅传输特征张量（不包含样本标识和基因组坐标），以及支持双层加密，在共享或远程推理场景中减少敏感信息暴露风险。
- **轻量客户端**：无需 GPU，内存 4-11 GB，运行时间数十秒到几分钟，便于在无 GPU 环境中部署。
- **清晰的对比实验**：固定智能体模型和任务，仅改变接口，直接量化了 token 消耗、时间、变异性，证明了接口设计的重要性。
- **开源与可复现**：代码公开在 GitHub（HKU-BAL/Clair3-Connect），包含所有实验脚本和配置。

### 8. 不足与局限

- **任务覆盖有限**：智能体实验仅使用 APOE 双倍型分型（2 个位点，2 个样本），未测试更复杂的多步骤流程（如全基因组变异检测、结构变异分析、组装等），难以证明方法在广泛场景下的通用性。
- **变异检测准确率仅评估了一个样本（HG003）**：缺少其他 GIAB 样本（如 HG002、HG004）或不同群体样本，可能存在在特定样本上过拟合的风险。
- **实验重复性**：准确率基准中未明确每个覆盖度是否重复多次，且仅覆盖两条染色体，未在全染色体水平上验证性能（除流程分析外）。
- **智能体模型单一**：仅使用 `deepseek-v4-pro`，未测试其他 LLM（如 GPT-4、Claude 3），其结果对模型选择的泛化能力未知。
- **客户端简化引入的准确率牺牲**：在低覆盖度、高错误率数据上放弃 pileup 和 phasing 导致准确率下降，该方法不适用于所有场景（如低深度或超高错误率长读长数据）。
- **传输安全测量在 loopback 上**：未考虑真实网络延迟，实际部署中加密开销占比可能发生变化。
- **工具集受限**：仅改造了一个工具（Clair3），未与其他生物信息学工具（如对齐器、组装器、结构变异检测器）联合测试，缺乏对工作流构成影响的评估。

（完）
