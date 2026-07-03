---
title: "Healthy-to-Stroke Translation of EEG-Based BMIs: EEG Characterization and Reinforcement Learning-Based Decoder Evaluation"
title_zh: 基于EEG的脑机接口从健康到中风迁移：EEG特征描述与基于强化学习的解码器评估
authors: "Via, Z., Kruse, A., Thapa, B. R., Bae, J."
date: 2026-06-29
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.23.733831v1.full.pdf"
tags: ["query:fsrh"]
score: 6.0
evidence: 基于Q学习核时差解码器的脑电图脑机接口中风解码
tldr: "脑机接口有望辅助中风康复，但神经重组导致解码困难。本研究分析健康与急性中风患者的运动想象EEG特征，并利用健康人群训练的Q-KTD解码器迁移至中风个体。结果表明，迁移学习使58%的患者首次解码成功率提升，平均增益7.34%，最大18.75%，但21人出现负迁移，存在显著个体差异。研究验证了离线可行性，可减少校准负担，但需个性化策略。"
source: biorxiv
selection_source: fresh_fetch
motivation: 减轻中风患者EEG解码的个体校准负担，探索健康人群训练的迁移学习可行性。
method: 分析109名健康与50名急性中风患者运动想象EEG特征，采用Q-KTD强化学习解码器进行健康-中风迁移学习。
result: "迁移学习使58%中风患者首次解码成功率提升，平均成功率从49.46%升至51.82%，最大增益18.75%，但42%出现负迁移。"
conclusion: 健康-中风迁移学习离线可行，可改善多数患者解码效果，但个体差异大，需自适应策略。
---

## 摘要
目的：基于EEG的脑机接口（BMIs）通过将神经活动转化为外部设备的控制命令，可能为患有中风相关运动障碍的个体提供辅助技术。然而，中风后的神经重组和个体间EEG变异性挑战了可靠的解码。本研究描述了健康和中风急性期参与者的运动想象EEG特征，并评估了群体训练的Q学习核时域差分（Q-KTD）解码器是否可以通过迁移学习改善个体中风解码。这些分析评估了基于EEG的BMI神经解码从健康到中风迁移的可行性。

材料与方法：使用公开可用的来自健康参与者（n=109）和中风急性期个体（n=50）的运动想象EEG数据集，分析左手和右手运动想象试验。选择这些数据集是因为它们的样本量相对较大且运动想象任务具有可比性。EEG特征描述包括基线和运动想象期的频带功率、ERD/ERS、半球不对称性和时频表示。对于Q学习核时域差分（Q-KTD）解码，使用运动想象开始后0-0.5秒的滤波时域EEG作为神经状态输入。将基于健康人群训练的Q-KTD模型迁移到个体中风参与者，并通过重复蒙特卡洛模拟比较有和无迁移学习在多个学习时期的解码性能。

结果：健康和中风急性期参与者表现出共同的运动想象相关EEG结构，包括开始后的μ节律抑制，而中风组表现出更大的参与者间变异性、更弥散的时频调制以及改变的半球不对称性。在假发现率校正后，窗口化频带功率中无通道级别的健康-中风差异保持显著。来自健康源的迁移学习在50名中风参与者中的29人（58%）提高了第一个时期的Q-KTD成功率。在所有参与者中，平均成功率从无迁移学习时的49.46%提高到有迁移学习时的51.82%。在表现出正迁移的参与者中，平均增益为7.34%，最大增益为18.75%。然而，21名参与者表现出负迁移，显示出显著的个体水平变异性。

结论：来自健康源的Q-KTD迁移学习提高了大多数中风急性期参与者第一个时期的运动想象BMI解码性能，支持了群体信息驱动的Q-KTD解码在中风中的离线可行性。这些早期的性能提升可能减少个体特定的校准负担，尽管显著的参与者间变异性和负迁移表明需要个体化的迁移选择或适应策略。

辅助技术意义：
- 基于EEG的脑机接口通过将运动想象相关的神经活动转化为外部设备的控制命令，可能为患有中风相关运动障碍的个体提供辅助技术。
- 从健康到中风的迁移学习可能改善早期BMI神经解码器的性能，并可能减少所需的个体特定校准量。
- 这些发现支持了Q-KTD用于中风急性期个体运动想象BMI神经解码的离线可行性。
- 显著的参与者间变异性和负迁移表明，为了可靠的中风后BMI实现，可能需要个体化的源模型选择或适应策略。
- 生理EEG特征，包括ERD/ERS和半球不对称性，可能为未来的迁移选择策略提供候选标记，尽管其预测价值需要直接验证。

## Abstract
PurposeEEG-based brain-machine interfaces (BMIs) may support assistive technologies for individuals with stroke-related motor impairment by translating neural activity into control commands for external devices. However, post-stroke neural reorganization and interindividual EEG variability challenge reliable decoding. This study characterized motor imagery EEG features in healthy and acute stroke participants and evaluated whether population-trained Q-learning Kernel Temporal Difference (Q-KTD) decoders could improve individual stroke decoding through transfer learning. These analyses assess the feasibility of healthy-to-stroke translation for EEG-based BMI neural decoding.

Materials and MethodsPublicly available motor imagery EEG datasets from healthy participants (n = 109) and individuals with acute stroke (n = 50) were analyzed using left- and right-hand motor imagery trials. The datasets were selected because of their relatively large sample sizes and comparable motor imagery tasks. EEG characterization included baseline and motor imagery-period band power, ERD/ERS, hemispheric asymmetry, and time-frequency representations. For Q-learning Kernel Temporal Difference (Q-KTD) decoding, filtered time-domain EEG from 0- 0.5 s after motor imagery onset was used as the neural-state input. A Q-KTD model trained on the healthy population was transferred to individual stroke participants, and repeated Monte Carlo simulations compared decoding performance with and without transfer learning across multiple learning epochs.

ResultsHealthy and acute stroke participants showed shared motor imagery-related EEG structure, including post-onset mu-band suppression, while the stroke group exhibited greater interparticipant variability, more diffuse time- frequency modulation, and altered hemispheric asymmetry. No channel-level healthy-stroke differences in windowed band power remained significant after false discovery rate correction. Healthy-source transfer learning improved first-epoch Q-KTD success rates in 29 of 50 stroke participants (58%). Across all participants, mean success rate increased from 49.46% without transfer learning to 51.82% with transfer learning. Among participants showing positive transfer, the mean gain was 7.34% and the maximum gain was 18.75%. However, 21 participants showed negative transfer, demonstrating substantial subject-level variability.

ConclusionHealthy-source Q-KTD transfer learning improved first-epoch motor imagery BMI decoding for a majority of acute stroke participants, supporting the offline feasibility of population-informed Q-KTD decoding in stroke. These early performance gains may reduce subject-specific calibration burden, although substantial interparticipant variability and negative transfer indicate the need for individualized transfer-selection or adaptation strategies.

Assistive Technology ImplicationsO_LIEEG-based brain-machine interfaces may support assistive technologies for individuals with stroke-related motor impairment by translating motor imagery-related neural activity into control commands for external devices.
C_LIO_LIHealthy-to-stroke transfer learning may improve early BMI neural-decoder performance and potentially reduce the amount of subject-specific calibration required.
C_LIO_LIThe findings support the offline feasibility of Q-KTD for motor imagery BMI neural decoding in individuals with acute stroke.
C_LIO_LISubstantial interparticipant variability and negative transfer suggest that individualized source-model selection or adaptation strategies may be needed for reliable post-stroke BMI implementation.
C_LIO_LIPhysiological EEG characteristics, including ERD/ERS and hemispheric asymmetry, may provide candidate markers for future transfer-selection strategies, although their predictive value requires direct validation.
C_LI