---
title: "🔬 电镜超分科研工作台 (Research Dashboard)"
---

# 🔬 电镜超分科研工作台 (Research Dashboard)

> [!tip]+ **工作流快速导航 (Quick Links)**
> - 📂 **课题主页**: [[20_Projects/电镜超分/项目总览|电镜超分项目总览]]
> - 📚 **文献库**: `10_Literature/` | 🧪 **实验记录**: `30_Experiments/` | 🧠 **知识库**: `40_Knowledge/`
> - 💻 **本地运行环境**: Conda 虚拟环境 `pytorch` (`D:\Anaconda\envs\pytorch`)
> - 🐙 **关联代码仓库**: [GitHub: Chisato-reco/chisato_reco](https://github.com/Chisato-reco/chisato_reco)
> - ☁️ **笔记同步仓库**: [GitHub: Chisato-reco/obsidian_chaofen](https://github.com/Chisato-reco/obsidian_chaofen)

---

## 📚 文献阅读状态看板 (Literature Tracker)

```dataview
TABLE 
  authors AS "作者", 
  year AS "年份", 
  status AS "阅读状态", 
  rating AS "推荐度",
  code_repo AS "开源代码"
FROM "10_Literature"
SORT year DESC
```

---

## 🧪 深度学习实验记录 (Conda `pytorch` Experiments)

```dataview
TABLE 
  date AS "实验日期",
  model_type AS "模型类型",
  dataset AS "数据集",
  status AS "状态",
  best_metric AS "最优指标"
FROM "30_Experiments"
SORT file.ctime DESC
LIMIT 10
```

---

## 🧠 核心概念与知识库 (Knowledge Base)

```dataview
LIST
FROM "40_Knowledge"
SORT file.name ASC
```

---

## ⚡ 常用快捷操作指南 (Cheat Sheet)
1. **从 Zotero 导入文献笔记**: 按快捷键 `Ctrl + P` 输入 `Zotero Integration: Create Literature Note`，选择论文即可自动抓取摘要、元数据与高亮批注。
2. **记录一次训练实验**: 使用快捷键 `Ctrl + P` 选择 `Templater: Open Insert Template modal`，插入 `Template - Experiment Log`。
3. **备份同步到 GitHub**: 点击左侧侧边栏 Git 图标或 `Ctrl + P` 选择 `Obsidian Git: Backup and sync`，仓库每 15 分钟会自动进行增量提交并同步至 GitHub。
