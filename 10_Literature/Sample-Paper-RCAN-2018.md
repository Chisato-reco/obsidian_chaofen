---
title: "Image Super-Resolution Using Very Deep Residual Channel Attention Networks (RCAN)"
authors: "Yulun Zhang, Kunpeng Li, Kai Li, Lichen Wang, Bineng Zhong, Yun Fu"
year: 2018
citekey: "zhang2018image"
itemType: "conferencePaper"
publication: "ECCV 2018"
status: 📖阅读中
rating: ⭐️⭐️⭐️⭐️⭐️
tags:
  - literature
  - 电镜超分
  - 超分辨率
  - 通道注意力
date_imported: "2026-11-06 21:50:00"
doi: "10.1007/978-3-030-01234-2_18"
url: "https://arxiv.org/abs/1807.02758"
zotero_link: "zotero://select/items/@zhang2018image"
code_repo: "https://github.com/yulunzhang/RCAN"
---

# Image Super-Resolution Using Very Deep Residual Channel Attention Networks (RCAN)

> [!abstract]+ **论文摘要 (Abstract)**
> 卷积神经网络在单图像超分辨率（SISR）领域取得了重大进展。然而，现有基于CNN的方法大多同等对待特征通道，缺乏自适应区分不同特征通道的能力。为了解决这一问题，本文提出了通道注意力机制（Channel Attention）和残差结构中的残差（Residual in Residual, RIR）网络架构RCAN，极大提升了超分辨率重建性能。

## 📌 元数据与链接
- **作者**: Yulun Zhang et al.
- **发表年份**: 2018 (ECCV)
- **开源代码**: [yulunzhang/RCAN](https://github.com/yulunzhang/RCAN)
- **对应 Zotero 条目**: [在 Zotero 中查看](zotero://select/items/@zhang2018image)

## 🎯 核心创新与电镜应用思考
- **核心机制**: 利用通道自适应注意力（Channel Attention）自适应加权重要特征，抑制无关背景噪声。
- **电镜超分启发**: 电镜图像中高频晶格/细胞器边界与低信噪比散斑噪声分布极不均匀，通道注意力机制能有效辅助网络将注意力集中于真实结构而非电镜噪声。
