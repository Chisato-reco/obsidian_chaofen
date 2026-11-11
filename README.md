# 电镜超分科研知识库：Obsidian × Zotero

Zotero 保存文献、PDF 和阅读批注；Obsidian 保存论文总结、知识卡片和实验记录；GitHub 保存笔记版本。

**笔记仓库：[Chisato-reco/obsidian_chaofen](https://github.com/Chisato-reco/obsidian_chaofen)。**

## 1. 本次排查与修复（2026-11-11）

本机检查到 Obsidian 1.15.0、Zotero 10.0.8、Zotero Integration 3.2.1 和 Better BibTeX 9.0.77。

| 问题 | 检查结果与处理 |
| --- | --- |
| Zotero 在运行，但 Obsidian 无法连接 | Better BibTeX 已安装，但 `userDisabled=true`、`active=false`；其探测接口返回 404。正常退出 Zotero、备份插件状态、启用后重启，接口已返回 `200 ready`。 |
| Obsidian 插件无法正确加载 | 文件夹叫 `zotero-integration`，而 manifest ID 是 `obsidian-zotero-desktop-connector`；已统一为后者，并移除启用列表中的旧 ID。 |
| 自定义引用模板未生效 | 原引用格式为 `markdown`，插件只有在 `format=template` 时才使用自定义模板；已修正。 |
| 文献模板导入报错或元数据为空 | `date` 过滤器不存在，应使用 `format`；摘要、DOI、条目链接改为 `abstractNote`、`DOI`、`desktopURI`；修复重复嵌套的 PDF Markdown 链接，并对标题等 YAML 字段转义。 |
| 重复导入可能丢失个人总结 | 原模板只保护了一个空白笔记区。已给论文核心脉络和科研思考增加 `research-summary` 保留区，并仅在首次导入时生成提示。 |
| GitHub 不能正常同步 | `origin` 已关联上述仓库，但本地初始化历史与远端初始化历史不相连；已合并并保留双方历史，后续使用普通推送。 |

验证记录：Better BibTeX 探测返回 `200 ready`；JSON-RPC 返回 Zotero / Better BibTeX 版本；成功读取本机论文及 10 条批注，使用已安装插件的模板引擎验证元数据、批注渲染和重复导入保护。PDF Utility 1.0.15 已安装，并只读提取同一 PDF 的 10 条内嵌批注。自动化验证未操作交互式选文献窗口；完整日常导入步骤见第 4 节。

Better BibTeX 是这条 Zotero Integration 工作流的**必要依赖**；把 XPI 放进笔记附件目录不等于安装或启用。依据：[Zotero Integration 项目说明](https://github.com/community-archive/obsidian-zotero-integration)、[Better BibTeX 安装说明](https://retorque.re/zotero-better-bibtex/installation/)。

## 2. 常见联动方案怎么选

以下是常见方案的功能比较，不代表使用量排名；本仓库采用方案 A。

| 方案 | 适合用途 | 依赖与边界 |
| --- | --- | --- |
| **A. Zotero Integration + Better BibTeX** | 导入元数据、PDF 批注和图表，生成可定制的文献笔记 | 导入时运行 Zotero；需要 Better BibTeX。PDF 内嵌批注提取还可能需要 PDF Utility。适合本仓库现有模板。 |
| **B. Citations + 自动导出的 `.bib` / CSL-JSON** | 写作时检索引用、生成简洁的文献笔记 | 在 Zotero 中导出 Better BibLaTeX 或 Better CSL JSON，并勾选 Keep updated；Citations 读取该文件，已导出的引用数据可离线检索。完整 PDF 批注导入需另配流程。 |
| **C. ZotLit** | 在 Obsidian 内浏览文献库、阅读 PDF、处理批注和引用 | 按对应版本文档安装配套组件并核对 Zotero 兼容性；不要直接套用本仓库的 Nunjucks 模板。 |
| **D. Zotero 条目链接 + 手工笔记** | 依赖最少，只需跳回原文 | 复制已有笔记中的 `zotero://` 条目或批注链接，自己整理摘要和思考；无需自动导入插件。 |

方案参考：[Citations](https://github.com/hans/obsidian-citation-plugin)、[Better BibTeX 自动导出](https://retorque.re/zotero-better-bibtex/exporting/auto/)、[ZotLit 文档](https://zotlit.aidenlx.site/)。这些替代插件未在本次修复中额外安装。

## 3. 首次配置与换电脑恢复

### Zotero 端

1. 安装 Zotero，并使用 Zotero 自己的同步功能恢复文献库。
2. 从 [Better BibTeX 官方发行页](https://github.com/retorquere/zotero-better-bibtex/releases)下载兼容版本的 `.xpi`。
3. Zotero → 工具 → 插件 → 齿轮 → 从文件安装插件，选择 `.xpi`，完成安装并确认开关为启用。
4. 重启 Zotero，等待 Better BibTeX 初始化；确认文献有 Citation Key。
5. 建议使用并固定稳定的引用键。修改已使用的引用键会改变笔记文件名，需要同时修正文内引用和链接。

**不要把 Zotero 的数据库或整个数据目录放进 Git 仓库。** Zotero 同步管理文献元数据，PDF 使用 Zotero 文件同步或自己配置的附件同步；本仓库的 GitHub 同步负责 Obsidian 文件。

### Obsidian 端

1. 用 Obsidian 打开本仓库根目录，按需信任并启用社区插件。
2. 设置 → 社区插件 → 确认 **Zotero Integration** 已启用。
3. 插件真实 ID / 目录名必须都是 `obsidian-zotero-desktop-connector`。界面名称仍然是 Zotero Integration。
4. 在该插件设置中确认以下配置：

| 配置项 | 本仓库设置 |
| --- | --- |
| Database | `Zotero` |
| Import format 名称 | `Create Literature Note` |
| Output path | `10_Literature/{{citekey}}.md` |
| Template file | `90_Templates/Template - Zotero Literature Note.md` |
| Image output path | `99_Attachments/{{citekey}}/` |
| Image base name | `image`（插件会追加定位信息） |
| Citation format | `template` |
| Markdown 引用模板 | `[@{{citekey}}]` |
| Zotero 链接模板 | `[{{title}}]({{desktopURI}})` |

5. 如需提取 PDF 文件内的高亮、图表，在插件设置的 **PDF Utility** 区下载工具。工具是每台电脑独立安装的本地程序，不随 GitHub 同步。
6. 修复目录后，重新加载 Obsidian；若命令列表仍未出现，关闭并重新打开 Obsidian。

本地连接使用 `127.0.0.1:23119`，日常导入无需 Zotero Web API Key。

## 4. 推荐日常流程：收集 → 阅读 → 导入 → 关联

### 收集与阅读

1. 用 Zotero Connector 保存论文，核对标题、作者、年份、DOI 和附件。
2. 在 Zotero 内置 PDF 阅读器标注；PDF 应挂在文献父条目下。
3. 推荐颜色约定：黄色＝背景与概念，绿色＝方法与创新，蓝色＝实验结果，红色＝局限与疑问。
4. 用区域批注框选模型结构图等内容。导出图片依赖附件可访问及相关工具正常工作。

### 一键生成文献笔记

1. 保持 Zotero 运行，回到 Obsidian。
2. `Ctrl+P` → **Zotero Integration: Create Literature Note**。
3. 在 Zotero 的文献选择窗口输入标题、作者或关键词，选中文献**父条目**并确认；不要只选择孤立 PDF。
4. 插件生成 `10_Literature/<citekey>.md`，图片写入 `99_Attachments/<citekey>/`。
5. 检查标题、作者、年份、DOI、摘要及批注；点击“打开 Zotero 条目”和“查看原文”确认能定位。
6. 在论文核心脉络、科研思考或个人笔记保留区写总结，并从项目笔记建立 `[[10_Literature/<citekey>]]` 链接。

`10_Literature/Sample-Paper-RCAN-2018.md` 是预置示例，不是从本机 Zotero 实测导入的凭证。

### 更新批注与保护笔记

在 Zotero 新增、修改或删除批注后，对同一引用键再次运行导入命令。当前模板重新生成批注部分，保留指定的个人笔记区；它不是逐字合并所有手工修改，也不会把 Obsidian 编辑自动写回 Zotero。

生成的 Markdown 中有以下隐藏标记（源码模式可见）：

```markdown
%% begin research-summary %%
这里的论文分析与科研思考会被保留。
%% end research-summary %%

%% begin notes %%
这里的额外个人笔记会被保留。
%% end notes %%
```

不要删除这些标记或文末的 `%% Import Date: ... %%`。元数据、自动摘录和保留区外的手工修改可能被重新导入覆盖；`status`、`rating`、`code_repo` 等属性目前也会按模板重置。需要长期维护的阅读状态，可记录在独立项目/阅读跟踪笔记中。

已经导入、但没有 `research-summary` 标记的旧笔记：先备份，再把手写分析包在同名 begin/end 标记里，之后才重新导入。新增保护不会自动识别旧笔记中任意位置的手工内容。

### 在项目、周报与论文草稿中引用

- **链接文献笔记**：`[[10_Literature/zhang2018image]]`，用于 Obsidian 双链和知识关联。
- **Pandoc 引用**：`Ctrl+P` → **Zotero Integration: Insert Markdown Citation**，插入 `[@引用键]`。
- **跳回 Zotero**：`Ctrl+P` → **Zotero Integration: Insert Zotero Link**，插入可点击的条目链接。
- **正式论文排版**：`[@引用键]` 本身不会自动生成完整参考文献；用 Pandoc 配套文献库与 CSL 样式导出，或在 Word / LibreOffice 中使用 Zotero 官方引用插件。

## 5. 目录与科研看板

```text
00_Inbox/       临时记录与待整理信息
10_Literature/  文献笔记
20_Projects/    课题方案与会议记录
30_Experiments/ 实验日志
40_Knowledge/   概念卡片
90_Templates/   文献、实验与知识模板
99_Attachments/ 笔记图片与附件
Dashboard.md   Dataview 科研看板
```

从 [科研看板](Dashboard.md) 查看文献与实验；用 Templater 创建实验和概念笔记。**Zotero 文献模板由 Zotero Integration 渲染，不能用 Templater 直接运行。** 模板中的作者、年份、阅读状态等属性供 Dataview 查询。

## 6. GitHub 关联、备份与多设备

远程地址已设置为：

```text
https://github.com/Chisato-reco/obsidian_chaofen.git
```

Obsidian Git 当前配置为：每 **15 分钟自动提交**、每 **30 分钟自动推送**、启动时拉取、推送前拉取。电脑休眠、Obsidian 未打开、无网络或认证失败时不会完成云端同步；退出时并没有另设自动拉取。

首次启用同步，先确认 GitHub 认证可用，且本地与远端历史已合并。日常可以通过命令面板搜索 Git 的 Commit / Push / Pull / Backup 命令，名称以当前插件版本为准。换设备先拉取，编辑完再提交并推送，尽量避免两台设备同时修改同一篇笔记。

终端手动同步（在仓库目录运行）：

```powershell
git status
git pull --no-rebase origin main
# 检查待提交内容后再提交；已有提交可直接推送。
git push origin main
```

不要用 `push --force` 处理分叉。笔记和图片的 Git 同步不能代替 Zotero 的文献及 PDF 同步；`zotero://` 链接需要已安装的 Zotero 客户端。

## 7. 连接故障速查

按“应用 → 插件 → 本地接口 → 模板 → 同步”的顺序排查。

| 现象 | 优先检查 |
| --- | --- |
| 命令面板没有 Zotero Integration | 社区插件是否启用；manifest ID、目录名和启用列表是否一致；重新加载 Obsidian。 |
| 无法连接 Zotero / BBT 探测返回 404 | Zotero → 工具 → 插件，确认 Better BibTeX 已安装、兼容并启用；等待初始化后重试。 |
| 连接被拒绝 | Zotero 是否运行；默认端口是否为 23119；两端是否在同一台电脑。 |
| 搜索不到论文 | 搜索文献父条目；检查引用键、所属文献库、Better BibTeX 初始化状态。 |
| Error parsing template | 用插件的 Data explorer 核对实际字段；日期过滤器用 `format`；不要混用其他插件模板语法。 |
| 只有元数据，没有批注/图片 | 确认 PDF 可在本机打开，批注来源正确，PDF Utility 可用；区域截图至少需要一条实际区域批注。 |
| 标题含引号后属性损坏 | 用 `dump` 输出 YAML 兼容的 JSON 字符串，避免手工给原始标题套双引号。 |
| 重新导入总结丢失 | 手写内容是否位于 persist 标记内；先从 Git 历史恢复，避免继续覆盖。 |
| Git 推送失败 | 核对认证、网络和远端分叉；这是 GitHub 同步问题，与 Zotero 本地接口分别排查。 |

在 PowerShell 中探测 Better BibTeX（不弹出选文献窗口）：

```powershell
Invoke-RestMethod 'http://127.0.0.1:23119/better-bibtex/cayw?probe=true'
```

正常结果为 `ready`。部分 PowerShell 环境会受代理或 HTTP 连接兼容性影响；此时可用 `curl.exe --noproxy "*"` 访问同一地址复核，避免仅凭一次工具报错判断 Zotero 未运行。

## 8. 官方参考

- [Zotero Integration 项目与文档入口](https://github.com/community-archive/obsidian-zotero-integration)
- [Better BibTeX 安装](https://retorque.re/zotero-better-bibtex/installation/)
- [Better BibTeX 自动导出](https://retorque.re/zotero-better-bibtex/exporting/auto/)
- [Better BibTeX Cite As You Write](https://retorque.re/zotero-better-bibtex/citing/cayw/)
- [Citations 插件](https://github.com/hans/obsidian-citation-plugin)
- [ZotLit 文档](https://zotlit.aidenlx.site/)
- [PDF Utility 官方发行页](https://github.com/mgmeyers/pdfannots2json/releases)
- [Zotero 同步说明](https://www.zotero.org/support/sync)
