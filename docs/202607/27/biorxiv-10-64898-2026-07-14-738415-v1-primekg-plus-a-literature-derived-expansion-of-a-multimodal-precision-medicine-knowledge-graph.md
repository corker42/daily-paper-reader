---
title: "PrimeKG-Plus: a literature-derived expansion of a multimodal precision medicine knowledge graph"
title_zh: PrimeKG-Plus：基于文献扩展的多模态精准医学知识图谱
authors: "Nguyen, T. T. D., Nguyen-Phuong, T., Nguyen, Q.-H., Abbasi, A. M., Le Phan, H.-D., Nguyen, L. B.-A., Phan, N.-T., Curabaz, N. N., Hauser, A. S., Tanoli, Z., Nguyen, D. T., Kooistra, A. J."
date: 2026-07-18
pdf: "https://www.biorxiv.org/content/10.64898/2026.07.14.738415v1.full.pdf"
tags: ["query:fsrh"]
score: 8.0
evidence: 使用大语言模型扩展专注于罕见神经系统疾病的医学知识图谱
tldr: "针对生物医学知识图谱更新滞后的问题，本文提出PrimeKG-Plus，通过LLM辅助从637篇PubMed文献提取关系，结合OpenTargets等新资源，扩展了PrimeKG。扩展聚焦罕见神经疾病，新增447,288条药物-蛋白-疾病路径，并捕获55个新分子实体，提升了药物重定位的连通性。"
source: biorxiv
selection_source: carryover_cache
figures_json: "[{\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-001.webp\", \"caption\": \"\", \"page\": 0, \"index\": 1, \"width\": 1697, \"height\": 1003, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-002.webp\", \"caption\": \"\", \"page\": 0, \"index\": 2, \"width\": 1690, \"height\": 1021, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-003.webp\", \"caption\": \"\", \"page\": 0, \"index\": 3, \"width\": 1698, \"height\": 872, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-004.webp\", \"caption\": \"\", \"page\": 0, \"index\": 4, \"width\": 1682, \"height\": 575, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-005.webp\", \"caption\": \"\", \"page\": 0, \"index\": 5, \"width\": 1668, \"height\": 989, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-006.webp\", \"caption\": \"\", \"page\": 0, \"index\": 6, \"width\": 1538, \"height\": 2367, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-007.webp\", \"caption\": \"\", \"page\": 0, \"index\": 7, \"width\": 1677, \"height\": 984, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-008.webp\", \"caption\": \"\", \"page\": 0, \"index\": 8, \"width\": 1709, \"height\": 1114, \"label\": \"Figure\"}, {\"url\": \"assets/figures/biorxiv/biorxiv-10-64898-2026-07-14-738415-v1/fig-009.webp\", \"caption\": \"\", \"page\": 0, \"index\": 9, \"width\": 1696, \"height\": 918, \"label\": \"Figure\"}]"
motivation: 现有知识图谱如PrimeKG静态不变，无法反映快速演变的生物医学知识，影响药物重定位应用。
method: 更新原始资源至2025年，集成OpenTargets等，用LLM从文献提取关系，经归一化、UMLS映射和专家审核，聚焦罕见神经疾病。
result: 网络分析显示药物-疾病连通性改善，新增44.7万条路径，FDA验证捕获55个新药物节点。
conclusion: PrimeKG-Plus提供最新知识图谱，支持基于网络的药物重定位和精准医学应用。
---

## 摘要
生物医学知识发展迅速，但大多数以疾病为中心的知识图谱在发布后保持不变。我们提出了PrimeKG-Plus，它是PrimeKG的扩展，将所有20个原始数据资源更新到2025年12月可用的版本，并整合了额外资源，包括OpenTargets、RepurposeDrugs和nSIDES。该知识图谱进一步通过从637篇PubMed摘要和PMC全文文章中提取的关系进行扩展，这些提取工作采用了大语言模型辅助的策展流程。提取的关系通过标准化、基于UMLS的同义词映射、基于SapBERT嵌入的相似性排序以及人类专家审查进行精炼，以确保数据质量。这一基于文献的扩展聚焦于罕见神经系统疾病，包括Canavan病、C型尼曼-匹克病、泰-萨克斯病和巴顿病。网络拓扑分析表明，扩展后的知识图谱改善了通过图谱的3-6跳间接药物-疾病连接性，同时新增了447,288条药物-蛋白质-疾病路径，连接了先前无法到达的药物-疾病对。时间FDA验证捕获了51个新的分子实体作为药物节点（这些实体在2021年6月的PrimeKG数据截止日期之后获批），其中46个在原始PrimeKG中缺失。通过将新整合和更新的资源与系统策展的文献衍生关联相结合，PrimeKG-Plus为基于网络的药物重定位和精准医学应用提供了一个最新的知识图谱。数据和代码公开可用。

## Abstract
Biomedical knowledge evolves rapidly, yet most disease-centered knowledge graphs remain unchanged after publication. We present PrimeKG-Plus, an extension of PrimeKG that updates all 20 original data resources to releases available as of Dec 2025 and incorporates additional resources, including OpenTargets, RepurposeDrugs, and nSIDES. The graph is further expanded with relations extracted from 637 PubMed abstracts and PMC full-text articles using a large-language-model-assisted curation workflow. Extracted relations were refined through normalization, UMLS-based synonym mapping, SapBERT embedding based similarity ranking, and human expert review to ensure data quality. This literature-driven expansion focuses on rare neurological disorders, including Canavan disease, Niemann-Pick disease type C, Tay-Sachs disease and Batten disease. Network topology analyses indicate that the expanded graph improves indirect drug-disease connectivity of 3-6 hops through the graph while adding 447,288 Drug-Protein-Disease paths linking drug-disease pairs that were previously unreachable. Temporal FDA validation captured 55 new molecular entities after the June 2021 PrimeKG data cut-off as drug nodes, 46 absent from the original PrimeKG. By integrating newly incorporated and updated resources with systematically curated literature-derived associations, PrimeKG-Plus provides an up-to-date knowledge graph for network-based drug repurposing and precision medicine applications. Data and code are publicly available.

---

## 论文详细总结（自动生成）

# 论文总结：PrimeKG-Plus：基于文献扩展的多模态精准医学知识图谱

## 1. 核心问题与整体含义（研究动机和背景）
- **问题**：现有生物医学知识图谱（如 PrimeKG）发布后静态不变，而生物医学知识（数据库和文献）快速演进，导致图谱无法反映最新的药物、疾病、蛋白质关联，尤其对药物重定位和精准医学应用造成阻碍。
- **意义**：构建一个**持续更新、可结合文献证据**的知识图谱，能提升基于网络的药物发现和疾病机制推理的时效性与覆盖度，弥补结构化数据库与最新文献之间的鸿沟。

## 2. 论文提出的方法论
- **核心思想**：在保留 PrimeKG 原始模式（节点/关系类型）的前提下，从三个维度扩展：
  1. **更新所有原始数据库**至 2025 年 12 月版本；
  2. **整合新资源**（OpenTargets、RepurposeDrugs、nSIDES）；
  3. **文献关系提取**：针对四种罕见神经疾病，通过大语言模型辅助+人工审核流水线，从 637 篇 PubMed 文献中抽取出符合 PrimeKG 模式的关系。
- **关键技术细节**：
  - **文献提取**：使用 NotebookLM（内嵌 Gemini 模型），以固定提示模板（约 800 token，列出 30 种关系类型）驱动，从文献中提取实体对及关系类型。采用小批量、定期刷新环境以缓解位置偏置。
  - **实体归一化与验证**（三步）：
    1. **UMLS 映射**：规则归一化 → REST API 查询 UMLS，要求语义类型匹配；
    2. **语义恢复**：对未映射实体，使用 SapBERT 嵌入计算余弦相似度得到 Top20 候选，再用 Sentence-BERT 重排序，选择最佳 PrimeKG 实体名，再验证 UMLS；
    3. **专家复审**：自动流程无法解决的实体由医学专家结合原文上下文判定。
  - **图整合**：将验证后的关系链接到 PrimeKG-Plus 节点（通过节点标签、UMLS CUI 映射至 MONDO/HPO/NCBI 等本体）。若概念不在图中则创建新节点。
- **无公式/算法伪代码**，以上为文字流程。

## 3. 实验设计
- **数据集与场景**：
  - **源数据库**：DrugBank 5.1.13、STRING v12.0、DisGeNET、OpenTargets v25.12.0、DrugCentral（2023‑05‑10）、SIDER 4.1、nSIDES、CTD（2025‑10）、MONDO（2025‑11‑04）、HPO（2025‑10‑22）、GO（2025‑10‑10）、Reactome、Bgee（2025‑02‑03）、UBERON（2025‑11‑24）等。
  - **文献**：637 篇 PubMed 文献（Canavan 病、Niemann‑Pick C 型、Tay‑Sachs 病、Batten 病）。
- **基准**：原始 PrimeKG（2021 年 6 月版本）。
- **对比方法**：无对比其他知识图谱工具；主要与原始 PrimeKG 做统计对比（节点数、边数、连通性、FDA 新药覆盖、稀有疾病路径）。
- **评估角度**：
  - 节点/边类型分布对比；
  - 疾病节点分组效果（MONDO 分组）；
  - 全局连通性分析（非直接适应症的药物-疾病对的 k 跳可达比例）；
  - 时序 FDA 验证（2021‑07 至 2025‑12 获批 NME）；
  - 稀有疾病网络富集分析（新增边、1‑6 跳路径）。

## 4. 资源与算力
- **未明确说明**具体 GPU 型号、数量或训练时长。
- 文献中提到使用 **NotebookLM**（Google 云平台，内含 Gemini 2.5 Flash / Gemini 3），该平台未暴露底层算力参数。实体嵌入使用预训练的 **SapBERT** 和 **Sentence‑BERT** 模型（无训练步骤）。
- 数据处理与整合脚本在常规 CPU/内存环境下可运行，未提及超算需求。

## 5. 实验数量与充分性
- **实验数量**：约 6–7 组核心分析（节点统计、边统计、疾病分组、全局连通性、FDA 验证、稀有疾病富集 + 两项案例研究）。
- **充分性**：
  - **全面**：覆盖了图结构基本统计、时效性验证、领域特定（稀有疾病）贡献。
  - **局限**：未进行下游预测任务（如药物重定位、链接预测）的 benchmark 对比，作者自陈“结构合理性检查而非性能指标”；仅 4 种疾病，通用性待验证。
  - **客观公平**：与原始 PrimeKG 的对比基于相同脚本和过滤条件，结果合理。

## 6. 主要结论与发现
- **图规模**：总体节点数基本持平（–0.04%），疾病节点 +16.4%，药物 +17.9%；有向边总数下降 5.1%（因删减冗余的解剖-蛋白边和模糊的药物-疾病边），但疾病-蛋白边增长 221%，药物-药物边增长 6.8%。
- **连通性改善**：3–6 跳药物-疾病对数可达比例显著提升（例如 4 跳从 75.69% 升至 85.78%）；新增 **447,288** 条药物→蛋白→疾病路径，连接了原始图中无法连通的药物-疾病对。
- **时效性**：捕获 **55 个** 2021 年 7 月后获批的 NME，其中 **46 个** 不存在于原始 PrimeKG。
- **文献集成**：为四种疾病新增 550 条关系（30–353 条/病种），引入了 36 个新本体节点，丰富了疾病-机制-治疗路径（如 Miglustat 用于 NPC, Arimoclomol 等）。

## 7. 优点
- **系统性更新**：统一更新所有原始资源，确保与最新数据库同步，并添加新资源（OpenTargets, nSIDES, RepurposeDrugs）。
- **创新的文献策展流程**：LLM 辅助提取 + 多阶段实体归一化（UMLS + SapBERT/SBERT + 专家复审），在效率与质量之间取得平衡。
- **模式兼容**：保持 PrimeKG 的关系模式，可直接用于已有的 PrimeKG 方法和基准，降低迁移成本。
- **开放与可复现**：代码和全部数据（除许可限制的原始数据库外）公开，提供详细文档。

## 8. 不足与局限
- **疾病覆盖窄**：文献扩展仅针对四种罕见神经疾病，对其他疾病领域的泛化能力未验证。
- **LLM 偏差风险**：使用商业 LLM（NotebookLM）可能引入提取偏差或幻觉，且平台参数不透明，复现性受限。作者虽设了多轮审核，但未定量评估 LLM 提取的召回率/精确率。
- **总边数下降**：部分关系类型（如解剖-蛋白、药物-适应症）因过滤条件变化而减少，可能影响需要这些信息的任务。
- **缺乏下游任务验证**：未进行药物重定位或链接预测的实验，仅以拓扑分析说明改进，说服力有限。
- **计算资源未报告**：难以评估构建图的计算成本，也缺少对大型 LLM 调用成本的说明。
- **时间截点**：更新资源只到 2025 年 12 月，文献检索至 2025‑11，之后的新知识仍需再次更新。

（完）
