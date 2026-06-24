---
title: A multi-agent system for spine MRI report generation from multi-sequence imaging
title_zh: 一种用于多序列脊柱MRI报告生成的多智能体系统
authors: "Xiao, Z., Yang, J., Sun, G., Zhang, H., Xu, H., Yao, Y., Miller, Z. D., King, W. E., Kanani, M. M., Andre, J. B., Chu, S., Zhang, M., Kinahan, P. E., Cross, N. M., Wang, S."
date: 2026-06-11
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.07.730703v1.full.pdf"
tags: ["query:fundus-mc"]
score: 8.0
evidence: 用于医疗诊断的多智能体系统
tldr: "脊柱MRI报告生成需整合多序列信息，现有方法难以兼顾序列特异性。SpineAgent多智能体框架通过预训练DINOv3编码器并引入持续训练学习合成器，融合T1/T2及其他序列信号，实现患者级嵌入。在17项脊柱病变预测中平均AUROC提升10.8%，跨厂商和队列泛化性强，并支持病理定位、分割及图文检索。集成37个专业代理后，端到端报告生成在自动指标和放射科医师评估中均达领先水平，提供了准确、可解释、通用的解决方案。"
source: biorxiv
selection_source: fresh_fetch
motivation: 脊柱MRI解读复杂耗时，需高效整合多序列信息以提升诊断准确性和效率。
method: 预训练DINOv3编码器区分T1/T2序列，通过持续训练学习合成器融合其他序列，构建多智能体系统处理诊断、定位和检索任务。
result: "17个脊柱病变预测AUROC平均提升10.8%，跨厂商和队列验证泛化性，且实现病理区域定位与检索。"
conclusion: SpineAgent通过分解任务为专业代理，实现了准确、可解释且泛化的脊柱MRI报告生成。
---

## 摘要
脊柱病变是全球疼痛和残疾的主要原因之一。脊柱磁共振成像（MRI）是临床评估的核心，但其解读仍然复杂且耗时，需要整合多个成像序列和解剖区域的信息。尽管近年来在自动化MRI分析方面取得了进展，但在保留序列特异性诊断信息的同时有效结合多序列数据仍是一个开放挑战。

在此，我们提出SpineAgent，一个用于脊柱MRI报告生成的多智能体框架，该框架基于一个多序列基础模型，该模型在32,047名患者和453,683个MRI序列的常规临床数据上进行训练，总共包含13,441,191张MRI切片。为了适应不同的序列模态，我们首先分别在T1和T2加权序列上预训练两个基于DINOv3的编码器。然后，我们引入一种持续训练策略，学习一个合成器，利用T1和T2编码器嵌入其他序列的图像，生成整合MRI序列间各种信号的患者级嵌入。利用这些嵌入，SpineAgent实现了最先进的性能，在17个脊柱状况预测任务中，平均AUROC比最佳竞争方法提高了10.8%，并在跨制造商和跨队列评估中表现出强大的泛化能力。除了分类，SpineAgent还通过识别与发现相关的切片和分割病理区域实现病理定位。它还支持多模态图像-报告检索，为可扩展和可解释的MRI报告生成提供了坚实基础。

我们进一步将这些经过验证的SpineAgent能力集成到37个专门智能体中，用于状况诊断、病理区域定位和临床相似病例检索。最后，我们将它们的输出作为结构化令牌整合到一个端到端训练的医学报告智能体中，用于报告生成。通过自动化指标和五位放射科专家的评估，SpineAgent在脊柱MRI报告生成中取得了领先性能。

总之，SpineAgent引入了一种用于多序列脊柱MRI理解的持续训练方法。通过将报告生成分解为由专门智能体处理的临床基础子任务，SpineAgent框架能够在不同成像序列和解剖区域上实现准确、可解释且泛化的脊柱MRI报告。

## Abstract
Spinal pathology is a leading cause of pain and disability worldwide. Spine magnetic resonance imaging (MRI) is central to clinical evaluation, yet its interpretation remains complex and time-consuming, requiring integration of information across multiple imaging sequences and anatomical regions. Despite recent advances in automated MRI analysis, effectively combining multi-sequence data while preserving sequence-specific diagnostic information remains an open challenge.

Here we present SpineAgent, a multi-agent framework for spine MRI report generation built upon a multi-sequence foundation model trained on routine clinical data from 32,047 patients and 453,683 MRI series, comprising a total of 13,441,191 MRI slices. To accommodate diverse modalities of sequences, we first pre-train two DINOv3-based encoders separately on T1- and T2-weighted sequences. We then introduce a continual training strategy that learns a synthesizer to embed images of other sequences using the T1 and T2 encoders, producing patient-level embedding that integrates various signals across MRI sequences. Using these embeddings, SpineAgent achieves state-of-the-art performance, with mean 10.8% AUROC improvement across 17 spinal condition-prediction tasks compared to the best competing method, and demonstrates strong generalizability under cross-manufacturer and cross-cohort evaluation. Beyond classification, SpineAgent enables pathology localization by identifying findings-relevant slices and segmenting pathological regions. It also supports multimodal image-report retrieval, providing a solid foundation for scalable and explainable MRI report generation.

We further integrate these validated capabilities of SpineAgent into 37 specialized agents for condition diagnosis, pathological-region localization, and clinically-similar-cases retrieval. Finally, we incorporate their outputs as structured tokens within a Medical Report Agent trained end-to-end for report generation. Through both automated metrics and expert evaluation by five radiologists, SpineAgent achieves leading performance in spine MRI report generation.

Together, SpineAgent introduces a continual training approach for multi-sequence spine MRI understanding. By decomposing report generation into clinically grounded subtasks addressed by specialized agents, the SpineAgent framework enables accurate, interpretable and generalizable spine MRI reporting across diverse imaging sequences and anatomical regions.