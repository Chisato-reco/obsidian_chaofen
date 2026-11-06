---
title: "<% tp.file.title %>"
authors: ""
year: <% tp.date.now("YYYY") %>
status: 📖阅读中
rating: ⭐️⭐️⭐️
tags:
  - literature
  - 电镜超分
created: <% tp.date.now("YYYY-MM-DD HH:mm:ss") %>
doi: ""
code_repo: ""
---

# <% tp.file.title %>

## 📌 基本信息
- **发表年份与期刊/会议**: 
- **论文链接**: 
- **开源代码**: 
- **相关课题**: [[20_Projects/电镜超分/项目总览]]

---

## 🎯 论文三问 (The Three Questions)
1. **这篇论文要解决什么核心问题？**
   - 
2. **作者提出了什么创新解决方案？核心方法是什么？**
   - 
3. **实验结果如何？相比 Baseline 有何优劣？**
   - 

---

## 🔬 方法解析 (Methodology)
### 网络架构 / 算法流程
```mermaid
graph LR
    Input[低分辨电镜图 LR] --> DegradationModel[退化感知模块]
    DegradationModel --> SRNetwork[超分辨率骨干网络]
    SRNetwork --> HighRes[超分辨重构图 SR]
```

### 关键数学公式 / 损失函数
$$ \mathcal{L}_{total} = \mathcal{L}_{rec} + \lambda_{adv} \mathcal{L}_{adv} + \lambda_{perc} \mathcal{L}_{perc} $$

---

## 📊 实验与指标分析
| 模型 | 数据集 | PSNR (dB) | SSIM | 备注 |
| :--- | :--- | :--- | :--- | :--- |
| Baseline | EM-Dataset | 28.50 | 0.821 | 原始基准 |
| 论文方法 | EM-Dataset | 31.20 | 0.895 | 本文方法 |

---

## 💡 对电镜超分项目的启发与思考
- 
