---
title: "实验记录 - <% tp.date.now('YYYYMMDD') %>"
date: <% tp.date.now("YYYY-MM-DD HH:mm:ss") %>
conda_env: pytorch
git_repo: Chisato-reco/chisato_reco
model_type: "SRModel"
dataset: "EM_Dataset"
status: 🔄进行中
best_metric: ""
tags:
  - experiment
  - 电镜超分
---

# 🧪 实验记录: <% tp.file.title %>

## 📌 实验环境与运行配置
- **Conda 虚拟环境**: `pytorch` (`D:\Anaconda\envs\pytorch\python.exe`)
- **代码仓库**: `Chisato-reco/chisato_reco`
- **Git Commit / 分支**: `main` (`commit hash`)
- **GPU 设备**: CUDA:0
- **运行命令 (Terminal / Conda Command)**:
```powershell
# 切换至项目根目录并启动训练
conda activate pytorch
python train.py --config configs/em_sr_baseline.yaml --epoch 100 --batch-size 16 --lr 1e-4
```

---

## 🎯 实验动机与假设 (Hypothesis)
- **本次实验的核心目的**: 
- **主要改动 (Diff / Changes)**: 

---

## ⚙️ 关键超参数 (Hyperparameters)
| 参数名 | 取值 | 说明 |
| :--- | :--- | :--- |
| Learning Rate | 1e-4 | 初始学习率 (Cosine Annealing) |
| Batch Size | 16 | 批处理大小 |
| Optimizer | AdamW | 权重衰减 1e-2 |
| Loss Functions | L1 + Perceptual | 像素损失 + 感知损失 |

---

## 📈 实验结果与评测 (Results & Metrics)
| 实验方案 / 轮次 | PSNR (dB) ↑ | SSIM ↑ | FRC 截止频段 | 耗时 / Epoch |
| :--- | :--- | :--- | :--- | :--- |
| Baseline | 28.32 | 0.812 | 0.35 | 45s |
| 本次实验 (Exp-1) | **30.15** | **0.874** | **0.42** | 52s |

### 训练曲线与效果对比
> 可将训练曲线截图或重构超分效果对比图放入此处：
> `![[99_Attachments/]]`

---

## 🔍 结果归因与下一步计划 (Insights & Next Steps)
- **结论**: 
- **遗留问题**: 
- **下一步实验计划**: 
