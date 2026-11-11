---
title: "Electron ptychography achieves atomic-resolution limits set by lattice vibrations"
authors: "Zhen Chen, Yi Jiang, Yu-Tsun Shao, Megan E. Holtz, Michal Odstrčil, Manuel Guizar-Sicairos, Isabelle Hanke, Steffen Ganschow, Darrell G. Schlom, David A. Muller"
year: 2021
citekey: "chenElectronPtychographyAchieves2021"
itemType: "journalArticle"
publication: "Science"
status: 📥未读
rating: ⭐️⭐️⭐️
tags:
  - literature
  - 电镜超分
date_imported: "2026-11-11 19:16:10"
doi: "10.1126/science.abg2533"
url: "https://www.science.org/doi/10.1126/science.abg2533"
zotero_link: "zotero://select/library/items/J9RQSR3I"
code_repo: ""
---

# Electron ptychography achieves atomic-resolution limits set by lattice vibrations

> [!abstract]+ **论文摘要 (Abstract)**
> Locating atoms with higher precision
>             
>               Two major problems that limit the resolution and interpretation of electron microscopy images are lens aberrations and multiple scattering. Chen
>               et al.
>               overcame these issues with ptychography, a technique that uses coherent scattering and multiple overlapping illumination spots to reconstruct an image from far-field diffraction patterns. This method works at a resolution that is limited, not by optics, but rather by the scattering strength of the sample, so it can work better with thicker samples. The authors achieved ultimate lateral resolution better than the thermal vibration of atoms in a PrScO
>               3
>               sample and showed that it is theoretically possible to identify single dopant atoms.
>             
>             
>               Science
>               , abg2533, this issue p.
>               826
>             
>           , 
>             Electron ptychography can reach atomic resolution that is only limited by lattice vibrations.
>           , 
>             Transmission electron microscopes use electrons with wavelengths of a few picometers, potentially capable of imaging individual atoms in solids at a resolution ultimately set by the intrinsic size of an atom. However, owing to lens aberrations and multiple scattering of electrons in the sample, the image resolution is reduced by a factor of 3 to 10. By inversely solving the multiple scattering problem and overcoming the electron-probe aberrations using electron ptychography, we demonstrate an instrumental blurring of less than 20 picometers and a linear phase response in thick samples. The measured widths of atomic columns are limited by thermal fluctuations of the atoms. Our method is also capable of locating embedded atomic dopant atoms in all three dimensions with subnanometer precision from only a single projection measurement.

## 📌 元数据与链接 (Metadata)
- **作者 (Authors)**: Zhen Chen, Yi Jiang, Yu-Tsun Shao, Megan E. Holtz, Michal Odstrčil, Manuel Guizar-Sicairos, Isabelle Hanke, Steffen Ganschow, Darrell G. Schlom, David A. Muller
- **发表年份 (Year)**: 2021
- **发表期刊/会议 (Publication)**: *Science*
- **DOI**: [10.1126/science.abg2533](https://doi.org/10.1126/science.abg2533)
- **Zotero 条目**: [打开 Zotero 条目](zotero://select/library/items/J9RQSR3I)
- **PDF 文件**: [PDF](zotero://select/library/items/XZH4L2G6)
- **开源代码 (Code)**: 

---

## 🎯 论文核心脉络 (Executive Summary)

%% begin research-summary %%


### 1. 研究背景与核心痛点 (Background & Problem)
- 这篇论文要解决的核心问题是什么？（例如：电镜低信噪比、电子束辐照损伤导致的分辨率限制等）
- 现有方法（SOTA）存在哪些不足？

### 2. 核心贡献与创新点 (Core Contributions)
- 
- 
- 

### 3. 方法与架构设计 (Methodology & Architecture)
- **网络架构概述**: 
- **关键技术细节与损失函数 (Loss Functions)**:

### 4. 实验设置与评价指标 (Experiments & Benchmark)
- **数据集 (Datasets)**: 
- **评价指标 (PSNR / SSIM / FRC 等)**:
- **核心对比结果**:

---

## 💡 对当前科研（电镜超分）的启发与思考 (Implications)
> 思考：该论文提出的思路/网络模块/采样策略/退化模型，能否直接或改进后迁移到我们的电镜超分项目中？

- **可借鉴之处**: 
- **潜在风险与电镜场景的差异**: 
- **后续尝试实验计划**: 


%% end research-summary %%

---

## 📝 批注与高亮摘录 (Extracted Annotations)

%% begin notes %%

<!-- 你在阅读过程中写的个人笔记可写在此区域，重新从 Zotero 导入批注时不会被覆盖 -->

%% end notes %%






> [!quote]+ 🟡 重点概念 / 理论依据 (p. 1)
> One major obstacle is that multiple electron scattering is unavoidable in samples thicker than a monolayer
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=XE7Z5HM8)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 1)
> Nonlinear or even nonmonotonic contrast dependences on the sample thickness occur when imaging samples thicker than a few dozen atoms
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=28THKITN)







> [!warning]+ 🔴 局限性 / 缺点批评 (p. 1)
> most of which are based on
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=TYU8YMRJ)







> [!warning]+ 🔴 局限性 / 缺点批评 (p. 1)
> Bloch wave theory, by phasing different Bragg beams of crystalline samples (7, 8). Unfortunately, these approaches become extremely difficult to implement for general samples with large unit cells or aperiodic structures, because a large number of unknown structure factors needs to be determined.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=2F6RPSXG)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 1)
> For thick samples, however, portions of the sample at different depth positions are effectively illuminated with different wave functions as a result of beam spreading by diffraction.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=KVSN9D83)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 1)
> In this work, there is no a priori assumption about the sample structure, and reconstructions start from random initial phases for all slices. The specimen potential for each slice is separately recovered through the phase of the transmission function, as illustrated in Fig. 1C
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=XS38U77M)







> [!warning]+ 🔴 局限性 / 缺点批评 (p. 1)
> We first compare the performance of multislice and single-slice electron ptychography on datasets simulated for crystalline PrScO3, the same system used for our experimental measurements.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=594WRP3H)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 2)
> Multislice electron ptychography provides quantitative phase information, with the phase increasing linearly as more layers are added into the sample.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=2&annotation=SC8HESGQ)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 2)
> conventional methods such as scanning TEM (STEM) annular dark-field and annular brightfield imaging or high-resolution TEM (HRTEM) imaging always have a nonlinear or even nonmonotonic dependence on thickness
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=2&annotation=DWTAUBU2)







> [!note]+ 🟢 创新方法 / 核心架构 (p. 4)
> Thermal broadening factors of atoms can be calculated from Debye-Waller factors (DWFs) obtained from x-ray diffraction (XRD) measurements.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=4&annotation=9L6A3YJD)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 1)
> One major obstacle is that multiple electron scattering is unavoidable in samples thicker than a monolayer,
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 1)
> Nonlinear or even nonmonotonic contrast dependences on the sample thickness occur when imaging samples thicker than a few dozen atoms,
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)







> [!warning]+ 🔴 局限性 / 缺点批评 (p. 1)
> most of which are based on
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)







> [!warning]+ 🔴 局限性 / 缺点批评 (p. 1)
> Bloch wave theory, by phasing different Bragg beams of crystalline samples (7 7, 8). Unfortunately, these approaches become extremely difficult to implement for general samples with large unit cells or aperiodic structures, because a large number of unknown structure factors needs to be determined.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 1)
> For thick samples, however, portions of the sample at different depth positions are effectively illuminated with different wave functions as a result of beam spreading by diffraction.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 1)
> In this work, there is no a priori assumption about the sample structure, and reconstructions start from random initial phases for all slices. The specimen potential for each slice is separately recovered through the phase of the transmission function, as illustrated in Fig. 1C
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)







> [!warning]+ 🔴 局限性 / 缺点批评 (p. 1)
> We first compare the performance of multislice and single-slice electron ptychography on datasets simulated for crystalline PrScO3, the same system used for our experimental measurements.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 2)
> Multislice electron ptychography provides quantitative phase information, with the phase increasing linearly as more layers are added into the sample.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=2)







> [!quote]+ 🟡 重点概念 / 理论依据 (p. 2)
> conventional methods such as scanning TEM (STEM) annular dark-field and annular brightfield imaging or high-resolution TEM (HRTEM) imaging always have a nonlinear or even nonmonotonic dependence on thickness
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=2)







> [!note]+ 🟢 创新方法 / 核心架构 (p. 4)
> Thermal broadening factors of atoms can be calculated from Debye-Waller factors (DWFs) obtained from x-ray diffraction (XRD) measurements.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=4)





%% Import Date: 2026-11-11T19:18:20.068+08:00 %%
