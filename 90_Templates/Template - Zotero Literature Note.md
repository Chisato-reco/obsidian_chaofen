---
title: {{title | dump | safe}}
authors: {{authors | default("") | dump | safe}}
year: {% if date %}{{date | format("YYYY")}}{% else %}null{% endif %}
citekey: {{citekey | dump | safe}}
cssclasses: [research-note]
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

[[10_Literature/文献目录|返回文献目录]] · [[20_Projects/电镜超分/项目总览|关联课题]]

**{{publicationTitle}}** · {% if date %}{{date | format("YYYY")}}{% endif %} · [Zotero]({{desktopURI}}){% if DOI %} · [DOI](https://doi.org/{{DOI}}){% endif %}

{{pdfZoteroLink}}

> [!abstract]- 原文摘要
> {{abstractNote | default("") | replace("\n", "\n> ")}}

## 阅读总结

{% persist "research-summary" %}
{% if isFirstImport %}
### 研究问题
- 要解决什么问题？已有方法的不足是什么？

### 方法与关键公式
- 核心思路、假设与创新：

### 实验与证据
- 数据集、评价方法、主要结果与局限：

### 对电镜超分的启发
- 能借鉴什么？适用条件是什么？下一步如何验证？
{% endif %}
{% endpersist %}

## 个人笔记

{% persist "notes" %}
{% if isFirstImport %}
<!-- 将自己的补充思考写在此保留区内。 -->
{% endif %}
{% endpersist %}

## 原文批注

{% macro renderAnnotation(annotation) -%}
{% if annotation.colorCategory == "Yellow" -%}
{% set kind = "quote" -%}{% set label = "背景与概念" -%}
{% elif annotation.colorCategory == "Green" -%}
{% set kind = "note" -%}{% set label = "方法与创新" -%}
{% elif annotation.colorCategory == "Blue" -%}
{% set kind = "example" -%}{% set label = "实验与结果" -%}
{% elif annotation.colorCategory == "Red" -%}
{% set kind = "warning" -%}{% set label = "局限与疑问" -%}
{% else -%}
{% set kind = "quote" -%}{% set label = "摘录" -%}
{% endif -%}
{% if annotation.annotatedText or annotation.comment or annotation.imageRelativePath -%}
> [!{{kind}}]- {{label}} · 第 {{annotation.pageLabel}} 页
{% if annotation.annotatedText -%}
> {{annotation.annotatedText | replace("\n", "\n> ")}}
{% endif -%}
{% if annotation.imageRelativePath -%}
> ![[{{annotation.imageRelativePath}}]]
{% endif -%}
{% if annotation.comment -%}
> **批注**：{{annotation.comment | replace("\n", "\n> ")}}
{% endif -%}
> [查看原文]({{annotation.desktopURI}})
{% endif -%}
{%- endmacro %}
{% for annotation in annotations -%}
{% if annotation.source != "pdf" %}
{{renderAnnotation(annotation)}}
{% endif -%}
{% endfor %}
{% set pdfAnnotations = annotations | filterby("source", "contains", "pdf") -%}
{% if pdfAnnotations.length %}
### PDF 内嵌批注备查

以下摘录可能与 Zotero 批注重复，按需展开。
{% for annotation in pdfAnnotations %}
{{renderAnnotation(annotation)}}
{% endfor -%}
{% endif %}
