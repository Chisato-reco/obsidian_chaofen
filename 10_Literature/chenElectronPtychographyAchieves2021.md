---
title: "Electron ptychography achieves atomic-resolution limits set by lattice vibrations"
authors: "Zhen Chen, Yi Jiang, Yu-Tsun Shao, Megan E. Holtz, Michal Odstrčil, Manuel Guizar-Sicairos, Isabelle Hanke, Steffen Ganschow, Darrell G. Schlom, David A. Muller"
year: 2021
citekey: "chenElectronPtychographyAchieves2021"
cssclasses: [research-note]
itemType: "journalArticle"
publication: "Science"
status: 📥未读
rating: ⭐️⭐️⭐️
tags:
  - literature
  - 电镜超分
date_imported: "2026-11-22 21:37:42"
doi: "10.1126/science.abg2533"
url: "https://www.science.org/doi/10.1126/science.abg2533"
zotero_link: "zotero://select/library/items/J9RQSR3I"
code_repo: ""
---

# Electron ptychography achieves atomic-resolution limits set by lattice vibrations

[[10_Literature/文献目录|返回文献目录]] · [[20_Projects/电镜超分/项目总览|关联课题]]

**Science** · 2021 · [Zotero](zotero://select/library/items/J9RQSR3I) · [DOI](https://doi.org/10.1126/science.abg2533)

[PDF](zotero://select/library/items/XZH4L2G6)

> [!abstract]- 原文摘要
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

## 阅读总结

%% begin research-summary %%


### 问题与背景
- 这篇论文解决了什么核心问题？
    - 解决了较厚样品的二维投影多重散射失真，并且把分辨率提高到了物理意义的最高上界（热力学决定）
- 现有方法存在哪些不足？
    + 电子显微镜空间分辨率已达50pm以下，但实际情况下仅在部分有利条件下成立
    + 多重散射（Multiple scattering）使得电子束形状被改变，导致接收器面上变得非常复杂
    + 分子太多的时候有对比度依赖，阻碍通过相位对比成像进行结构测定
### 核心贡献
- 在厚样品中实现了仪器误差小于20pm级别精度的测量
- 能够在一次测量中以亚纳米级别精度定位所有嵌入原子
+ 在样品的二维投影领域达到了分辨率物理上界（热力学决定），sota。

### 方法与关键公式
- **网络架构概述**: 
- **关键技术细节与损失函数 (Loss Functions)**:

### 实验与证据
- **数据集 (Datasets)**: 
- **评价指标 (PSNR / SSIM / FRC 等)**:
- **核心对比结果**:

---

## 对课题的启发
> 思考：该论文提出的思路/网络模块/采样策略/退化模型，能否直接或改进后迁移到我们的电镜超分项目中？

+ 后续完善的地方：迭代耗时久，依靠算力大；依靠强大设备移植性差；对于z轴的深度分辨还是不够精密。

%% end research-summary %%

## 个人笔记

%% begin notes %%
### 英文翻译
+ Ptychography 叠层衍射成像
+ diffraction 衍射
<!-- 你在阅读过程中写的个人笔记可写在此区域，重新从 Zotero 导入批注时不会被覆盖 -->

%% end notes %%

## 原文批注



> [!quote]- 背景与概念 · 第 1 页
> One major obstacle is that multiple electron scattering is unavoidable in samples thicker than a monolayer
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=XE7Z5HM8)


> [!quote]- 背景与概念 · 第 1 页
> Nonlinear or even nonmonotonic contrast dependences on the sample thickness occur when imaging samples thicker than a few dozen atoms
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=28THKITN)


> [!warning]- 局限与疑问 · 第 1 页
> most of which are based on
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=TYU8YMRJ)


> [!warning]- 局限与疑问 · 第 1 页
> Bloch wave theory, by phasing different Bragg beams of crystalline samples (7, 8). Unfortunately, these approaches become extremely difficult to implement for general samples with large unit cells or aperiodic structures, because a large number of unknown structure factors needs to be determined.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=2F6RPSXG)


> [!warning]- 局限与疑问 · 第 1 页
> However, such super-resolution approaches can be applied reliably only to samples thinner than a few nanometers, and the resolution in thicker samples is not substantially different from that attained with conventional methods
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=IY7R7W34)


> [!quote]- 背景与概念 · 第 1 页
> For samples thicker than the probe’s depth of focus, multislice ptychography, using multiple slices to represent the sample, has been proposed (18). The structures of all slices can be retrieved separately.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=P6IU46BE)


> [!warning]- 局限与疑问 · 第 1 页
> however, only a few proof-of-principle multislice electron ptychography demonstrations (14, 22) have been reported and are limited in either resolution or stability.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=XUHKVN9A)


> [!example]- 实验与结果 · 第 1 页
> We demonstrate multislice electron ptychographic reconstructions experimentally, recovering a linear phase response versus thickness, and push the lateral resolution close to the intrinsic atomic size, limited by thermal fluctuations of the atoms themselves
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=6NFILG4L)


> [!quote]- 背景与概念 · 第 1 页
> For thick samples, however, portions of the sample at different depth positions are effectively illuminated with different wave functions as a result of beam spreading by diffraction.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=KVSN9D83)


> [!quote]- 背景与概念 · 第 1 页
> In this work, there is no a priori assumption about the sample structure, and reconstructions start from random initial phases for all slices. The specimen potential for each slice is separately recovered through the phase of the transmission function, as illustrated in Fig. 1C
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=XS38U77M)


> [!warning]- 局限与疑问 · 第 1 页
> We first compare the performance of multislice and single-slice electron ptychography on datasets simulated for crystalline PrScO3, the same system used for our experimental measurements.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1&annotation=594WRP3H)


> [!quote]- 背景与概念 · 第 2 页
> Multislice electron ptychography provides quantitative phase information, with the phase increasing linearly as more layers are added into the sample.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=2&annotation=SC8HESGQ)


> [!quote]- 背景与概念 · 第 2 页
> conventional methods such as scanning TEM (STEM) annular dark-field and annular brightfield imaging or high-resolution TEM (HRTEM) imaging always have a nonlinear or even nonmonotonic dependence on thickness
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=2&annotation=DWTAUBU2)


> [!note]- 方法与创新 · 第 4 页
> Thermal broadening factors of atoms can be calculated from Debye-Waller factors (DWFs) obtained from x-ray diffraction (XRD) measurements.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=4&annotation=9L6A3YJD)


> [!quote]- 背景与概念 · 第 5 页
> **批注**：这里是在说太厚的样本掺杂原子难以发现
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=5&annotation=N4KKWU8A)


> [!quote]- 背景与概念 · 第 5 页
> ![[99_Attachments/chenElectronPtychographyAchieves2021/image-5-x209-y217.png]]
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=5&annotation=VJLMM4IL)


> [!warning]- 局限与疑问 · 第 5 页
> Because conventional imaging methods are based on projections through the entire sample, single dopants embedded in a relatively thick matrix usually show little or no contrast (fig. S16). Only dopants with large atomic numbers in a light element matrix and a very thin sample may be detectable.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=5&annotation=IWF4WF48)


> [!warning]- 局限与疑问 · 第 5 页
> there is strong multiple electron scattering in crystalline samples, and the resultant rechanneling of the electron beam may lead to incorrect column locations for dopants via conventional optical sectioning methods
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=5&annotation=HPDREE55)


> [!example]- 实验与结果 · 第 5 页
> The recovered linear signal provided by our full inversion of electron multiple scattering via multislice electron ptychography addresses these deficiencies.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=5&annotation=BH7Y8F2Y)



### PDF 内嵌批注备查

以下摘录可能与 Zotero 批注重复，按需展开。

> [!quote]- 背景与概念 · 第 1 页
> One major obstacle is that multiple electron scattering is unavoidable in samples thicker than a monolayer,
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)


> [!quote]- 背景与概念 · 第 1 页
> Nonlinear or even nonmonotonic contrast dependences on the sample thickness occur when imaging samples thicker than a few dozen atoms,
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)


> [!warning]- 局限与疑问 · 第 1 页
> most of which are based on
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)


> [!warning]- 局限与疑问 · 第 1 页
> Bloch wave theory, by phasing different Bragg beams of crystalline samples (7 7, 8). Unfortunately, these approaches become extremely difficult to implement for general samples with large unit cells or aperiodic structures, because a large number of unknown structure factors needs to be determined.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)


> [!quote]- 背景与概念 · 第 1 页
> For thick samples, however, portions of the sample at different depth positions are effectively illuminated with different wave functions as a result of beam spreading by diffraction.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)


> [!quote]- 背景与概念 · 第 1 页
> In this work, there is no a priori assumption about the sample structure, and reconstructions start from random initial phases for all slices. The specimen potential for each slice is separately recovered through the phase of the transmission function, as illustrated in Fig. 1C
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)


> [!warning]- 局限与疑问 · 第 1 页
> We first compare the performance of multislice and single-slice electron ptychography on datasets simulated for crystalline PrScO3, the same system used for our experimental measurements.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=1)


> [!quote]- 背景与概念 · 第 2 页
> Multislice electron ptychography provides quantitative phase information, with the phase increasing linearly as more layers are added into the sample.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=2)


> [!quote]- 背景与概念 · 第 2 页
> conventional methods such as scanning TEM (STEM) annular dark-field and annular brightfield imaging or high-resolution TEM (HRTEM) imaging always have a nonlinear or even nonmonotonic dependence on thickness
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=2)


> [!note]- 方法与创新 · 第 4 页
> Thermal broadening factors of atoms can be calculated from Debye-Waller factors (DWFs) obtained from x-ray diffraction (XRD) measurements.
> [查看原文](zotero://open-pdf/library/items/XZH4L2G6?page=4)




%% Import Date: 2026-11-22T21:37:49.159+08:00 %%
