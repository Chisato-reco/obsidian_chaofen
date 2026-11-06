# 🔬 电镜超分科研知识库 (Obsidian × Zotero × PyTorch)

本仓库是为**电镜超分辨率重建（Electron Microscopy Super-Resolution）**科研课题量身定制的现代化学术工作台。基于目前国际学术界主流的 **Obsidian + Zotero 7 / 6 + Dataview + Git** 工作流搭建，打通了「文献管理 ➔ 批注双向联动 ➔ 课题调研 ➔ 本地深度学习实验（Conda `pytorch`）➔ GitHub 自动化云端同步」的全生命周期闭环。

---

## 📁 1. 仓库目录结构规范

```text
obsidian_chaofen/
├── 00_Inbox/                  # 📥 收集箱：快速记录闪念、未分类的临时想法与临时文献
├── 10_Literature/             # 📚 文献库：由 Zotero 一键自动生成的论文精读笔记与批注
├── 20_Projects/               # 🎯 课题项目区
│   └── 电镜超分/              # 核心课题：开题规划、技术方案、网络架构设计、会议纪要
├── 30_Experiments/            # 🧪 实验记录：与本地 conda pytorch 环境联动的训练日志与指标对比
├── 40_Knowledge/              # 🧠 知识库：永久概念卡片（超分辨率、退化模型、FRC指标、频域损失等）
├── 90_Templates/              # 📝 模板区
│   ├── Template - Zotero Literature Note.md    # Zotero 自动化导入核心模板（含彩色高亮与图表提取）
│   ├── Template - Paper Reading Summary.md     # 论文三问与速读摘要模板
│   ├── Template - Experiment Log.md            # 深度学习实验与训练指标追踪模板
│   └── Template - Concept Note.md              # 核心知识点卡片模板
├── 99_Attachments/            # 🖼️ 附件库：从 PDF 提取的高清图表、训练曲线截图与模型结构图
├── Dashboard.md               # 📊 科研看板：集成 Dataview 的可视化文献与实验进度总控台
└── README.md                  # 📖 本使用说明文档
```

---

## ⚡ 2. Obsidian 与 Zotero 关联的核心配置与完整使用方法

仓库内已预装并深度配置了官方主流插件 **`Zotero Integration`**，实现了无需第三方中转服务的原生无缝交互。

### 2.1 前置准备（Zotero 端）
1. **安装并打开 Zotero**（推荐 Zotero 7 或 Zotero 6）。
2. **安装 Better BibTeX 插件（强烈推荐）**：
   - Better BibTeX 会为每篇文献自动生成标准 Citekey（例如 `zhang2018image`）。
   - 如果未安装 Better BibTeX，插件依然可以通过 Zotero 内置数据库正常抓取文献。
3. **在 Zotero 内置 PDF 阅读器中做划线批注**：
   - 模板已针对批注颜色分类进行了语义化映射，推荐采用如下科研划线习惯：
     - 🟡 **黄色（Yellow）**: 研究背景、核心问题、先验理论依据
     - 🟢 **绿色（Green）**: 本文创新方法、关键网络结构、核心公式
     - 🔵 **蓝色（Blue）**: 实验数据、Benchmark 对比指标（PSNR / SSIM 等）
     - 🔴 **红色（Red）**: 现有方法局限、本文缺陷、思考与质疑
     - 🖼️ **矩形框选（Area Highlight）**: 截取论文架构图、消融实验对比图、损失曲线

---

### 2.2 一键生成文献笔记（核心实操）

在精读完一篇文献并划好高亮后：
1. **打开 Obsidian** 并确保后台 **Zotero 处于运行状态**。
2. 按快捷键 **`Ctrl + P`**（Mac 上为 `Cmd + P`）打开命令面板。
3. 输入并选择：
   ```text
   Zotero Integration: Create Literature Note
   ```
   *(💡 小技巧：你可以在 Obsidian 设置 -> 快捷键 中，将该命令绑定为你习惯的快捷键，例如 `Alt + Z`)*
4. 在屏幕中央弹出的搜索框中，输入**论文题目、作者名或关键字**（支持实时模糊检索）。
5. 按 **Enter** 确认。
6. **自动完成**：
   - 插件会在 `10_Literature/` 目录下自动新建形如 `[Citekey].md` 的笔记。
   - 自动抓取论文标题、全部作者、发表年份、期刊/会议、DOI、在线链接与 Zotero 专属跳转链接。
   - 自动将论文中所有划线高亮按照颜色转化为带语义标签的 Callout 引用块，并标注原始页码与直接跳转回 PDF 对应位置的超链接。
   - 自动将论文中框选截取的图表以高清原图存入 `99_Attachments/` 并优雅嵌入笔记！

---

### 2.3 增量更新与个人思考保护机制（Persist）
- 很多文献需要反复多轮精读，后续可能在 Zotero 中补充了新的高亮。
- 模板中专门设置了保留区域：
  ```markdown
  {% persist "notes" %}
  <!-- 你在阅读过程中写的个人笔记可写在此区域，重新从 Zotero 导入批注时不会被覆盖 -->
  {% endpersist %}
  ```
- 你可以在该区域内自由撰写你的个人见解、公式推导与改动想法。后续在 Zotero 添加新高亮后，重新运行一次导入命令，插件会**智能更新元数据与高亮批注，同时完整保留你手写的所有个人笔记**！

---

### 2.4 在正文笔记中快速引用文献
在撰写项目调研方案、周报或知识点卡片时，如需引用文献：
1. 光标停留在需要引用的位置。
2. 按 `Ctrl + P` 输入 `Zotero Integration: Insert Markdown Citation` 或 `Insert Zotero Link`。
3. 搜索选中论文后，将自动插入规范的学术引用标记（如 `[@zhang2018image]`）或直达 Zotero 客户端的跳转超链接。

---

## 📊 3. 科研看板 (Dashboard.md) 与文献状态追踪

根目录下的 `Dashboard.md` 是你的文献与实验总控台，由 `Dataview` 实时驱动：
1. **文献状态看板**：
   - 每篇文献笔记的 Frontmatter 包含 `status` 属性（默认为 `📥未读`，精读时可改为 `📖阅读中`，精读完毕后改为 `✅已精读`）和 `rating` 评分。
   - `Dashboard.md` 会自动按年份与阅读状态聚合成清晰的学术跟踪表格。
2. **知识与实验看板**：
   - 自动聚合最近 10 次深度学习实验的训练效果、PSNR/SSIM 最佳指标与模型类型。

---

## 🧪 4. 联动本地 Conda `pytorch` 深度学习实验

为保证学术笔记与代码实践的一体化：
1. **环境定位**: 你的本地 Conda 环境位于 `D:\Anaconda\envs\pytorch`。
2. **实验记录创建**:
   - 在 `30_Experiments/` 下新建笔记，或使用快捷键呼出 `Templater` 插入 `Template - Experiment Log`。
   - 模板自动生成实验参数表、模型超参数配置、代码 Commit Hash 记录与训练命令示例。
   - 训练完成后的测试指标（如电镜超分核心的 PSNR、SSIM、FRC 截止频率）填入表格后，会自动同步呈现在 `Dashboard.md` 看板中。

---

## ☁️ 5. GitHub 自动备份与多端同步 (Chisato-reco)

仓库已集成 **`obsidian-git`** 插件，并已配置远程仓库为：
`https://github.com/Chisato-reco/obsidian_chaofen.git`

### 首次在 GitHub 上建立远程仓库并推送：
由于这是本地新建的知识库，请在 GitHub 上创建对应仓库后执行首次推送：

1. **登录 GitHub**：进入你的 GitHub 账号 [`Chisato-reco`](https://github.com/Chisato-reco)。
2. **新建仓库**：
   - 仓库名称填写：`obsidian_chaofen`
   - 设为 **Private**（私有）或 Public（公开）
   - **请勿**勾选 Initialize with README / .gitignore（本地已配置完整）。
3. **在终端执行首次推送**（在当前目录打开 PowerShell 或 VS Code 终端）：
   ```powershell
   git push -u origin main
   ```
4. **日常全自动同步**：
   - 插件已配置为**每 15 分钟自动 Commit 并推送**，退出或打开时自动拉取。
   - 你也可以随时在 Obsidian 左侧功能栏点击 Git 图标，或按 `Ctrl + P` 运行 `Obsidian Git: Backup and sync` 进行即时一键同步。

---

## 🚀 6. 预装插件清单与状态

| 插件名称 | 插件 ID | 作用说明 | 状态 |
| :--- | :--- | :--- | :--- |
| **Zotero Integration** | `zotero-integration` | 深度打通 Zotero 7/6，实现文献元数据、批注与图表一键提取 | ✅ 已就绪并配置模板 |
| **Dataview** | `dataview` | 动态查询与学术看板构建，自动化跟踪文献与实验状态 | ✅ 已就绪 |
| **Templater** | `templater-obsidian` | 强大的动态模板引擎，自动插入时间、标题与上下文变量 | ✅ 已就绪 |
| **Obsidian Git** | `obsidian-git` | 自动版本控制，静默备份至 GitHub `Chisato-reco` | ✅ 已就绪 |
