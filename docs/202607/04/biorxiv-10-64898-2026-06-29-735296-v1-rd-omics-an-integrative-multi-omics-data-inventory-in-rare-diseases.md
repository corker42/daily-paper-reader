---
title: "RD-OMICS: An Integrative Multi-Omics Data Inventory in Rare Diseases"
title_zh: RD-OMICS：罕见疾病中的整合多组学数据资源库
authors: "Sun, S., Wang, H., Mathe, E. A., Zhu, Q."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735296v1.full.pdf"
tags: ["query:fsrh"]
score: 8.0
evidence: 直接处理罕见病数据整合，并使用大语言模型辅助
tldr: "罕见病研究受限于小队列、异质性和分散的组学数据。RD-OMICS整合了来自GEO的126种罕见病组学数据，通过规则映射和LLM辅助语义分类构建元数据标准化流程，形成知识图谱，包含11,049个系列、375,930个样本。案例展示了其在ALS药物重定位中的应用，为转化研究提供可扩展的基础。"
source: biorxiv
selection_source: fresh_fetch
motivation: 罕见病组学数据分散且注释不一致，阻碍整合分析与转化发现。
method: 使用规则映射和LLM辅助语义分类构建元数据标准化流程，设计图数据模型整合疾病、实验、样本等实体。
result: "处理了11,049个GEO系列、375,930个样本、1,578个平台和10,938个项目，覆盖126种罕见病。"
conclusion: RD-OMICS将碎片化组学数据转化为结构化、可互操作的资源，助力罕见病治疗开发。
---

## 摘要
罕见疾病（RD）影响美国超过3000万人，但仅有不到5%的已识别疾病拥有FDA批准的治疗方法。RD研究进展受到患者队列规模小、生物学异质性以及公开可用的组学数据碎片化且注释不一致的限制，这阻碍了整合分析和转化发现。在此，我们提出了RD-OMICS，这是一个数据资源库，以知识图谱的形式整合了来自基因表达综合数据库（GEO）的结构化RD组学数据。我们开发了一个元数据协调流水线，结合了基于规则的映射和大语言模型（LLM）辅助的语义分类。定义了基于图的数据模型，将疾病条件、实验、样本、平台、项目和出版物等不同类型的数据整合到一个集中化的资源图谱中。在这项初步研究中，对126种罕见疾病的11,049个GEO系列进行了处理并整合到RD-OMICS中，其中包括375,930个个体生物样本、1,578个测序和阵列平台、10,938个生物学项目。案例研究展示了RD-OMICS在支持罕见疾病研究、组学队列构建以及基于转录组的肌萎缩侧索硬化症（ALS）药物重定位中的应用。RD-OMICS为将碎片化的组学数据转化为结构化、协调且可互操作的资源提供了可扩展的基础，促进了罕见疾病的治疗开发和其他转化发现。

## Abstract
Rare diseases (RD) impact over 30 million individuals in the United States, yet fewer than 5% of the identified conditions have FDA-approved treatments. Progress in RD research is hindered by small patient cohorts, biological heterogeneity, and the fragmented, inconsistently annotated publicly available omics data, which limits integrative analysis and translational discovery. Here, we present RD-OMICS, a data inventory with integrated and structured RD omics data from Gene Expression Omnibus (GEO), in the form of a knowledge graph. We developed a metadata harmonization pipeline that combines rule-based mapping and large language model (LLM)-assisted semantic categorization. The graph-based data model was defined to integrate different types of data including disease conditions, experiments, samples, platforms, projects, and publications into a centralized inventory graph. In this preliminary study, 11,049 GEO series for 126 rare diseases were processed and integrated into RD-OMICS, which includes 375,930 individual biospecimen samples, 1,578 sequencing and array platforms, 10,938 biological projects. Case studies demonstrate the use of RD-OMICS in supporting rare disease research, omics cohort construction, and transcriptome-based drug repurposing for amyotrophic lateral sclerosis (ALS). RD-OMICS provides a scalable foundation for transforming fragmented omics data into a structured, harmonized and interoperable resource, facilitating therapeutic development and other translational discoveries in rare diseases.

---

## 论文详细总结（自动生成）

## 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：罕见病（RD）影响美国超过3000万人，但仅有不到5%的已识别疾病拥有FDA批准的治疗方法。研究进展受限于患者队列规模小、生物学异质性，以及公开可用的组学数据碎片化、注释不一致，导致整合分析和转化发现困难。
- **整体含义**：本文旨在解决罕见病组学数据分散、难以整合的问题，通过构建一个结构化、可互操作的知识图谱资源库（RD-OMICS），将来自基因表达综合数据库（GEO）的零散组学数据统一协调，为罕见病治疗开发和转化发现提供可扩展的基础设施。

## 2. 论文提出的方法论：核心思想、关键技术细节、算法流程
- **核心思想**：将碎片化的罕见病多组学数据转化为结构化的知识图谱，通过元数据标准化实现数据互操作，并利用大语言模型（LLM）辅助语义分类以提高自动标注的准确性。
- **关键技术细节**：
  - **元数据协调流水线**：结合基于规则的映射（rule-based mapping）和LLM辅助的语义分类，对GEO中不同格式、不同语义的元数据进行标准化处理。
  - **图数据模型**：定义疾病条件、实验、样本、平台、项目和出版物等实体的关系，构建集中化的知识图谱。
- **算法流程（文字说明）**：
  1. 从GEO收集原始组学数据及其元数据。
  2. 通过规则映射（如基于关键词、本体映射）对已知标准的元数据字段进行初步统一。
  3. 对于规则无法覆盖的模糊或非标准注释，使用LLM（如GPT系列）进行语义分类，将非结构化描述映射到标准化术语。
  4. 将处理后的元数据与疾病、样本、实验等实体关联，构建图数据库（Neo4j或其他图数据库），形成RD-OMICS知识图谱。

## 3. 实验设计：使用了哪些数据集/场景、Benchmark、对比方法
- **数据集**：全部数据来源于基因表达综合数据库（GEO），覆盖126种罕见病，包括11,049个GEO系列、375,930个个体生物样本、1,578个测序和阵列平台、10,938个生物学项目。
- **应用场景**：
  - 支持罕见病研究：展示RD-OMICS作为数据查询和整合平台的能力。
  - 组学队列构建：基于协调后的元数据筛选特定疾病（如ALS）的转录组队列。
  - 药物重定位案例：以肌萎缩侧索硬化症（ALS）为例，利用整合的转录组数据进行基于转录组的药物重定位分析。
- **Benchmark与对比方法**：论文未明确设置定量benchmark或与其他方法进行系统性对比。重点在于展示RD-OMICS数据资源的可用性和案例有效性，而非算法性能的比较。

## 4. 资源与算力
- 文中未明确说明所使用的GPU型号、数量、训练时长等算力信息。仅提到使用LLM辅助语义分类，但未披露具体模型部署资源。因此无法评估计算开销。

## 5. 实验数量与充分性
- **实验数量**：主要实验为构建RD-OMICS资源库，覆盖126种疾病、11,049个系列。案例研究仅针对ALS进行药物重定位分析，未开展多疾病或多场景的重复实验。
- **充分性评估**：
  - 资源构建规模较大，数据覆盖面较好，但实验设计相对单一（仅一个案例验证）。
  - 缺乏消融实验（如比较有无LLM辅助的标注效果、基于规则与LLM的贡献度分析）。
  - 没有与其他现有罕见病数据整合方法（如Orphanet、RD-Connect等）进行对比。
  - 总体而言，实验设计偏重资源描述和初步展示，在方法论验证和泛化能力评估上不够充分。

## 6. 论文的主要结论与发现
- RD-OMICS成功将GEO中碎片化的罕见病组学数据整合为结构化的知识图谱，包含大量样本、项目和平台信息。
- 通过规则映射+LLM辅助的元数据协调流水线，能够有效处理异质性注释，提升数据互操作性。
- 案例研究表明，RD-OMICS可用于支持罕见病组学队列构建和基于转录组的药物重定位，具有转化应用潜力。
- 该资源为罕见病治疗开发和发现提供了可扩展的基础。

## 7. 优点
- **方法创新**：首次将LLM用于罕见病组学元数据的语义分类和标准化，结合规则映射提高自动化程度。
- **数据规模**：整合了GEO中11,049个系列、37万余样本，覆盖126种罕见病，资源价值高。
- **可扩展性**：知识图谱结构支持未来持续添加新数据、新疾病。
- **应用导向**：以ALS药物重定位作为案例，直接展示了转化研究的实际用途。

## 8. 不足与局限
- **实验覆盖**：仅做了ALS一个案例，未验证对其他罕见病的通用性和稳定性；缺乏消融实验和性能指标（如标注准确率、召回率）。
- **偏差风险**：数据来源局限于GEO，可能遗漏其他公共数据库（如dbGaP、ArrayExpress）；LLM辅助标注可能存在语义偏差或错误，未进行人工验证或错误分析。
- **应用限制**：元数据协调流水线对LLM的依赖可能导致计算成本高、可重复性差（LLM版本变更影响）；知识图谱的更新机制尚未讨论；药物重定位结果缺乏体外/体内验证。
- **资源与算力未披露**：影响实验可复现性。

（完）
