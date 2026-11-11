---
title: 科研首页
aliases: [首页, 科研工作台]
cssclasses: [research-home]
---

# 科研首页

电镜超分 · 从阅读走向实验

> [!tip] 当前课题
> [[20_Projects/电镜超分/项目总览|电镜超分辨率重建]] — 研究目标、技术路线与下一步任务。

## 快速入口

| 阅读与积累 | 研究与实践 |
| --- | --- |
| [[10_Literature/文献目录|文献阅读]] | [[20_Projects/项目目录|课题项目]] |
| [[40_Knowledge/知识目录|概念与方法]] | [[30_Experiments/实验目录|实验记录]] |
| [[00_Inbox/收集箱|临时收集]] | [[90_Templates/模板索引|新建笔记]] |

## 下一步做什么

![[20_Projects/电镜超分/项目总览#4. 近期任务清单 (TODO)]]

## 最近阅读

[[10_Literature/chenElectronPtychographyAchieves2021|Chen 等 · 2021 · 电子叠层成像与原子分辨率]]

~~~dataview
TABLE WITHOUT ID link(file.path, default(title, file.name)) AS "文献", year AS "年份", status AS "状态"
FROM "10_Literature"
WHERE citekey
SORT file.mtime DESC
LIMIT 5
~~~

## 阅读到实验

收集论文 → 在 Zotero 批注 → 导入文献笔记 → 写下自己的理解 → 关联课题与实验。

[[80_Guides/Obsidian与Zotero使用指南|联动使用指南]] · [[80_Guides/笔记整理约定|整理约定]] · [[95_Examples/示例索引|示例区]]
