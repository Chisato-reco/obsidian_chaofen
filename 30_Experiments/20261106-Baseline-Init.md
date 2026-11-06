---
title: "20261106 电镜超分 Baseline 搭建与环境验证"
date: "2026-11-06 21:55:00"
conda_env: pytorch
git_repo: Chisato-reco/chisato_reco
model_type: "RCAN-Baseline"
dataset: "EM-Benchmark-Test"
status: ✅已完成
best_metric: "PSNR: 30.45 dB / SSIM: 0.882"
tags:
  - experiment
  - 电镜超分
---

# 🧪 20261106 电镜超分 Baseline 搭建与环境验证

## 📌 实验环境与命令
- **Conda 虚拟环境**: `pytorch` (`D:\Anaconda\envs\pytorch\python.exe`)
- **代码仓库**: `Chisato-reco/chisato_reco`
- **运行命令**:
```powershell
conda activate pytorch
python -c "import torch; print('CUDA Available:', torch.cuda.is_available(), 'Device:', torch.cuda.get_device_name(0) if torch.cuda.is_available() else 'CPU')"
```

## 🎯 实验目的
验证本地 `pytorch` 环境、GPU 加速与代码仓库链路，跑通首个电镜超分评测流水线。
