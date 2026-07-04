---
title: Segmentation and classification of retinal pigment granules in fluorescence lifetime imaging microscopy (FLIM) data
title_zh: 荧光寿命成像显微镜(FLIM)数据中视网膜色素颗粒的分割与分类
authors: "Ali, M., Ahmad, H. A., Alderzy, H., Hammer, M., Heintzmann, R., Stranik, O."
date: 2026-07-03
pdf: "https://www.biorxiv.org/content/10.64898/2026.06.29.735375v1.full.pdf"
tags: ["query:fundus-mc"]
score: 8.0
evidence: 直接视网膜图像分析：与AMD相关的RPE颗粒分割分类
tldr: 视网膜色素上皮(RPE)颗粒的荧光特性改变与年龄相关性黄斑变性等疾病相关，但颗粒间视觉可分离性有限，精确分割和分类困难。本研究提出Classi4RPE算法，基于荧光寿命成像数据，采用种子分水岭分割，通过荧光寿命差异区分脂褐素(L)、黑色素脂褐素(ML)和黑色素(M)颗粒。结果显示L颗粒敏感度0.99、特异度0.93，ML颗粒敏感度0.90、特异度0.98。该方法超越了人类视觉限制，为RPE定量分析提供了鲁棒工具。
source: biorxiv
selection_source: fresh_fetch
motivation: 视网膜色素颗粒的精确分割和分类对理解AMD等疾病至关重要，但现有方法难以区分荧光特性相似的颗粒。
method: 基于FLIM数据，采用种子分水岭分割算法，利用荧光寿命差异识别L颗粒，并依据空间寿命分布区分ML与其他含黑色素颗粒。
result: L颗粒分割敏感度0.99、特异度0.93，ML颗粒敏感度0.90、特异度0.98，性能优于人工标注。
conclusion: Classi4RPE可超越人类视觉限制，为RPE颗粒的定量分析提供可靠工具。
---

## 摘要
由年龄相关性黄斑变性(AMD)等疾病引起的视网膜色素上皮细胞(RPE)荧光特性的改变，突显了在单颗粒水平对荧光RPE颗粒进行详细分析的必要性。由于这些颗粒的视觉可分离性有限，其精确分割和分类仍然具有挑战性。在本研究中，我们提出了Classi4RPE，这是一种基于荧光寿命成像数据（可提供独特对比度）的计算算法，旨在准确分割RPE颗粒并将其分为三类：脂褐素(L)、黑色素脂褐素(ML)和黑色素(M)。该方法在自定义Python框架中实现，采用种子分水岭分割来分离单个颗粒。脂褐素颗粒被识别为具有较长寿命的超荧光结构，而寿命较短的颗粒则根据其从中心到边缘的空间寿命分布进行进一步分析，从而将ML与其他富含黑色素的颗粒区分开来。与手动标注的金标准相比，我们的方法实现了高性能，L颗粒的平均灵敏度为0.99，ML颗粒为0.90，相应的特异性分别为0.93和0.98。这些结果表明Classi4RPE有潜力超越人类视觉限制，并为定量RPE分析提供强大的工具。

## Abstract
Alterations of fluorescence properties in retinal pigment epithelium (RPE) cells caused by diseases such as age-related macular degeneration (AMD) highlight the need for detailed analysis of the fluorescent RPE granules at the individual level. Precise segmentation and classification of these granules remain challenging due to their limited visual separability. In this study, we present Classi4RPE, a computational algorithm designed to accurately segment RPE granules and classify them into three categories -- lipofuscin (L), melanolipofuscin (ML), and melanin (M) -- based on fluorescence lifetime imaging data, which provide distinctive contrast. The method is implemented in a custom Python framework and employs seeded watershed segmentation to isolate individual granules. Lipofuscin granules are identified as hyperfluorescent structures with longer lifetimes, while granules with shorter lifetimes are further analyzed based on their spatial lifetime distribution from the center to edge, enabling discrimination of ML from other melanin-rich granules. Our approach achieves high performance, with mean sensitivities of 0.99 for L granules and 0.90 for ML granules, and corresponding specificities of 0.93 and 0.98, respectively, compared to manually annotated ground truth. These results demonstrate the potential of Classi4RPE to surpass human visual limitations and provide a robust tool for quantitative RPE analysis.

---

## 论文详细总结（自动生成）

### 1. 论文的核心问题与整体含义（研究动机和背景）
- **核心问题**：视网膜色素上皮（RPE）颗粒的荧光特性改变与年龄相关性黄斑变性（AMD）等疾病密切相关，但不同颗粒（脂褐素L、黑色素脂褐素ML、黑色素M）在常规可见光成像下视觉可分离性极差，导致精确分割和分类困难，阻碍了对RPE颗粒在疾病进程中变化的定量分析。
- **整体含义**：作者旨在利用荧光寿命成像显微镜（FLIM）提供额外对比度（不同颗粒具有不同的荧光寿命），开发一种能够超越人类视觉局限性的自动化算法，实现对RPE颗粒的实例级分割和亚型分类，为AMD等疾病的机制研究和临床诊断提供鲁棒的工具。

### 2. 论文提出的方法论：核心思想、关键技术细节
- **核心思想**：基于FLIM数据中颗粒的荧光寿命差异（L寿命长，M寿命短，ML呈现中心短寿命/外围长寿命的环状分布），设计两阶段分割+分类流水线。
- **关键技术细节**（算法流程）：
  1. **预分类掩膜生成**：将图像像素根据荧光寿命分为两组。通过高斯混合模型（GMM）拟合寿命直方图，以最低寿命簇（对应M）的均值+0.25倍标准差为阈值。寿命高于阈值的像素归入Mask A（预期仅含L成分），低于阈值的归入Mask B（含M和ML的中央M样核心）。
  2. **独立分割**：对两个掩膜分别应用**种子分水岭分割**（seeded watershed）。种子点通过高斯差分（DoG）滤波的局部最大值获得，并设置最小间距（Mask A: 3像素，Mask B: 7像素）以防止过分割。分割基于倒转强度图像进行，使用8连通邻域。
  3. **分类**：
     - Mask A中所有分割区域直接分类为L，并膨胀1像素以捕获完整边缘。
     - Mask B中每个分割区域先膨胀2像素（以包含ML外围的L荧光区域），然后提取径向荧光寿命分布，用二次函数拟合。计算边缘寿命与中心寿命之比R_τ。若R_τ < 1.15，分类为M；若R_τ ≥ 1.15，分类为ML。
  4. **图像融合**：将所有分类区域合并输出，不同颗粒类型用不同颜色（L红、ML蓝、M绿），边缘用白色高亮。

### 3. 实验设计：数据集、基准、对比方法
- **数据集**：使用7个FLIM数据集（来自人眼RPE冰冻切片，AMD供体，12μm厚，2光子激发960nm，荧光发射检测通道2（>550 nm）为主）。其中3个用于优化阈值参数，其余用于评估。
- **基准（Ground Truth）**：由人工在分割图像上手动标注颗粒坐标并分类，但仅标注可明确识别的颗粒，排除模糊无法判断的颗粒。
- **对比方法**：本文未与其他算法进行定量对比，但**定性讨论**了与传统分割工具（如ilastik）和通用神经网络分割方法（如Cellpose）相比的不足（需大量手动调整、难以处理高度可变的自发荧光模式）。也提到了与SIM（结构光照明显微镜）图像进行交叉验证，但SIM仅用于辅助验证颗粒类型，未用于定量评估。因此，**主要对比对象是人工标注的Ground Truth**。

### 4. 资源与算力
- 论文**未明确说明**使用的GPU型号、数量、训练时长等计算资源信息。算法在自定义Python框架中实现（无深度学习训练环节，主要依赖传统图像处理），推测在常规CPU上即可运行，无需大规模算力。

### 5. 实验数量与充分性
- **实验数量**：总共使用了7个数据集，但未列出每个数据集的详细图像数量。评估时计算了L和ML颗粒的灵敏度和特异性（均值、最小、最大值），但M颗粒因ground truth不确定性被排除。
- **充分性分析**：
  - **优点**：在不同数据集上均取得了稳定较高的性能（L灵敏度0.99，ML灵敏度0.90），且包含了与SIM图像的视觉对比，增强了结果的可信度。
  - **不足**：实验规模相对较小（仅7个数据集），且未进行细致的消融实验（如不同阈值、膨胀系数的影响）。同时，由于ground truth本身不完善，部分颗粒被排除，可能导致评估存在偏差。未与其他自动化方法进行公平的定量对比，使得算法相对优势难以量化。此外，只验证了AMD样本，对健康或其他疾病的泛化性未知。

### 6. 论文的主要结论与发现
- Classi4RPE能够有效分割和分类RPE颗粒，L颗粒的检测灵敏度达0.99、特异性0.93；ML颗粒灵敏度0.90、特异性0.98，均优于人工肉眼判断。
- 该算法能够捕获人眼难以分辨的细节（如ML颗粒的环状寿命分布），为量化RPE颗粒在AMD中的变化提供了可行工具。
- 分割精度受输入强度图像质量影响，过分割（将一个大颗粒分成多块）是主要误差来源，进而导致误分类（如将ML的部分辨识为L）。
- 区分M与ML仍然是难点，受限于阈值选择和ground truth的不确定性，因此未对M进行评估。

### 7. 优点
- **创新性**：巧妙利用FLIM提供的寿命空间分布（径向剖面），有效区分了视觉上相似的M与ML颗粒，超越了纯强度图像的限制。
- **实用性**：无需大量人工标注训练数据，仅基于传统图像处理方法（GMM、种子分水岭），计算效率高，易于推广。
- **性能优越**：在有限的数据集上对L和ML取得了接近完美的灵敏度和特异性，表明方法鲁棒。
- **可视化友好**：提供了Python GUI，便于用户交互调整参数和导出结果。

### 8. 不足与局限
- **实验局限性**：仅使用7个AMD样本数据集，缺乏健康对照或其他疾病样本的验证；未进行系统性消融实验优化所有参数（如阈值1.15）的泛化性。
- **评估偏差**：ground truth本身不完美，排除难以识别的M颗粒和模糊区域，导致评估可能高估了实际区分能力；未量化分割错误对分类的影响。
- **方法局限**：分割严重依赖强度图像，对于强度变异大的L颗粒和强度弱的M/ML颗粒易出现过分割或欠分割；寿命阈值的选择对预分类影响大，但缺乏自适应机制；M与ML的区分阈值1.15基于少量数据优化，可能不适用于不同成像条件或疾病阶段。
- **应用限制**：仅适用于2光子FLIM数据（960nm激发），且需要两个发射通道（>550nm为主）；未测试在单通道或不同成像协议下的表现。算法尚未扩展到3D分析，而RPE颗粒在组织切片中可能具有三维重叠。

（完）
