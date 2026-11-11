---
title: {{title | dump | safe}}
authors: {{authors | default("") | dump | safe}}
year: {% if date %}{{date | format("YYYY")}}{% else %}null{% endif %}
citekey: {{citekey | dump | safe}}
itemType: {{itemType | dump | safe}}
publication: {{publicationTitle | default("") | dump | safe}}
status: 📥未读
rating: ⭐️⭐️⭐️
tags:
  - literature
  - 电镜超分
date_imported: "{{importDate | format("YYYY-MM-DD HH:mm:ss")}}"
doi: {{DOI | default("") | dump | safe}}
url: {{url | default("") | dump | safe}}
zotero_link: {{desktopURI | default("") | dump | safe}}
code_repo: ""
---

# {{title}}

> [!abstract]+ **论文摘要 (Abstract)**
> {{abstractNote | default("") | replace("\n", "\n> ")}}

## 📌 元数据与链接 (Metadata)
- **作者 (Authors)**: {{authors}}
- **发表年份 (Year)**: {% if date %}{{date | format("YYYY")}}{% endif %}
- **发表期刊/会议 (Publication)**: *{{publicationTitle}}*
- **DOI**: {% if DOI %}[{{DOI}}](https://doi.org/{{DOI}}){% endif %}
- **Zotero 条目**: [打开 Zotero 条目]({{desktopURI}})
- **PDF 文件**: {{pdfZoteroLink}}
- **开源代码 (Code)**: 

---

## 🎯 论文核心脉络 (Executive Summary)

{% persist "research-summary" %}
{% if isFirstImport %}

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

{% endif %}
{% endpersist %}

---

## 📝 批注与高亮摘录 (Extracted Annotations)

{% persist "notes" %}
{% if isFirstImport %}
<!-- 你在阅读过程中写的个人笔记可写在此区域，重新从 Zotero 导入批注时不会被覆盖 -->
{% endif %}
{% endpersist %}

{% for annotation in annotations -%}
{%- if annotation.annotatedText -%}
{%- if annotation.colorCategory == "Yellow" -%}
> [!quote]+ 🟡 重点概念 / 理论依据 (p. {{annotation.pageLabel}})
> {{annotation.annotatedText}}
{%- if annotation.comment %}
>> ✍️ **批注**: {{annotation.comment}}
{%- endif %}
[查看原文]({{annotation.desktopURI}})
{%- elif annotation.colorCategory == "Green" -%}
> [!note]+ 🟢 创新方法 / 核心架构 (p. {{annotation.pageLabel}})
> {{annotation.annotatedText}}
{%- if annotation.comment %}
>> ✍️ **批注**: {{annotation.comment}}
{%- endif %}
[查看原文]({{annotation.desktopURI}})
{%- elif annotation.colorCategory == "Blue" -%}
> [!example]+ 🔵 实验数据 / 基准结果 (p. {{annotation.pageLabel}})
> {{annotation.annotatedText}}
{%- if annotation.comment %}
>> ✍️ **批注**: {{annotation.comment}}
{%- endif %}
[查看原文]({{annotation.desktopURI}})
{%- elif annotation.colorCategory == "Red" -%}
> [!warning]+ 🔴 局限性 / 缺点批评 (p. {{annotation.pageLabel}})
> {{annotation.annotatedText}}
{%- if annotation.comment %}
>> ✍️ **批注**: {{annotation.comment}}
{%- endif %}
[查看原文]({{annotation.desktopURI}})
{%- else -%}
> [!quote] 📝 批注高亮 (p. {{annotation.pageLabel}})
> {{annotation.annotatedText}}
{%- if annotation.comment %}
>> ✍️ **批注**: {{annotation.comment}}
{%- endif %}
[查看原文]({{annotation.desktopURI}})
{%- endif %}
{%- endif %}

{%- if annotation.imageRelativePath %}
> [!image]+ 🖼️ 提取图表 (p. {{annotation.pageLabel}})
> ![[{{annotation.imageRelativePath}}]]
{%- if annotation.comment %}
>> ✍️ **图表批注**: {{annotation.comment}}
{%- endif %}
[在 PDF 中定位]({{annotation.desktopURI}})
{%- endif %}

{% endfor -%}
