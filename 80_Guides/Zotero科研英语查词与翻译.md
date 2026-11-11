# Zotero 科研英语查词与翻译

[[Dashboard|返回首页]] · [[80_Guides/科研知识库工作流与Obsidian必会操作|科研工作流]] · [[80_Guides/Obsidian与Zotero使用指南|Zotero 联动说明]]

## 本机已安装

**Translate for Zotero 2.4.8**，作者 windingwind，插件 ID 为 `zoteropdftranslate@euclpts.com`。它在 Zotero 的 PDF、EPUB 和网页阅读器中提供选词查词与选段翻译，也支持标题、摘要和批注翻译。

安装于 2026-11-11；当前 Zotero 为 10.0.8。安装包来自[作者的稳定版发行页](https://github.com/windingwind/zotero-pdf-translate/releases/tag/v2.4.8)，包内声明兼容 Zotero 7.9.9–10.9.9。已核对[发行附件提供的 SHA-256](https://github.com/windingwind/zotero-pdf-translate/releases/expanded_assets/v2.4.8)：

```text
8145e9972c507f6baee93b93d2c2e8e7fe24388c58f2cebe0a37e29db5de26e6
```

经 Zotero“工具 → 插件 → 从文件安装”完成安装，并已正常重启。插件状态为启用、未被用户禁用、未被判定不兼容；Better BibTeX 也保持启用。

## 已确认的默认配置

| 项目 | 当前值 | 用途 |
| --- | --- | --- |
| 单词词典 | Bing Dictionary（必应词典） | 查询单词释义，服务提供时显示音标和发音 |
| 文段翻译 | CNKI（知网翻译） | 辅助理解所选句子与短段落 |
| 原语言 | 英语 `en-US` | 插件默认值；另有自动检测选项 |
| 目标语言 | 简体中文 `zh-CN` | 已写入本机插件设置 |
| 选中文本自动翻译 | 默认开启 | 选词/选段后显示结果 |
| 单词使用词典 | 默认开启 | 单词和文段分别使用不同服务 |
| 自动翻译并写入批注 | 默认关闭 | 新建标注时不自动把译文写入批注 |
| 用译文替换原文加入笔记 | 默认关闭 | 保留原文与译文的区别 |

默认开关来自实际安装包的 `prefs.js`；持久化的词典、文段服务与目标语言已在本机配置中核对。可以在 Zotero“编辑 → 设置 → Translate / 翻译”中查看或调整；中文界面名称可能随插件翻译不同。

选词和文段翻译会把所选文字发送给所选词典/翻译服务，属于在线查询，不是离线词库。当前两项服务不需要你填写付费 API 密钥，也没有为你开通付费服务。免费接口的可用性可能改变；出错时在插件服务设置中切换其他可用引擎。

## 第一次使用：先查一个词

1. 打开 Zotero **内置阅读器**中的英文 PDF。浏览器、系统 PDF 软件中不会出现这个 Zotero 插件。
2. 双击一个普通单词，例如 `resolution`；或拖选一个单词。
3. 查看选区浮窗或右侧 Translate / 翻译区域中的词典结果。
4. 如果没有出现结果，先确认插件启用及“单词使用词典”“选区弹窗”“自动翻译所选文本”已开启；也可选中后按 `Ctrl+T` 手动触发。注意，在文献列表中这个快捷键处理的是标题翻译，使用前先进入 PDF。
5. 再拖选一个完整句子，查看文段翻译。单词与整句查询的结果形式不同，属于正常行为。
6. 遇到换行断句或跨栏选区，检查原文框中的文本顺序后再翻译；不要把错误提取的句子当作原句理解。

当前已验证：插件重启后仍启用，必应词典对 `resolution` 的在线请求返回 HTTP 200、英文音标和中文释义，Better BibTeX 的本地探测仍返回 `200 ready`。**尚未自动完成 PDF 内实际选词浮窗和知网整句翻译的端到端测试**；因此这两项以你阅读器内看到的实际结果为准。词典接口测试只发送了测试词，没有上传整篇 PDF。

## 科研阅读时怎么用

### 普通英语：查词典

先看词性、搭配和原句。像 `resolution` 同时有“解决、决议、分辨率”等含义，应结合成像上下文选择；不能把词典第一条释义直接写进论文总结。

### 专业术语：查短语，再核对定义

`electron ptychography`、`multiple scattering`、`point spread function` 等术语，应尽量连同修饰词一起查询。通用词典不保证收录所有电镜和计算成像术语；结合论文中的定义、权威教材或综述核对。译法不确定时保留英文，并标为“待核实”。

### 长难句：翻译辅助分析

先找句子的主干、转折和条件，再对照译文。特别核对 `may`、`only`、`under`、`assuming`、`limited by` 等限制条件，以及比较对象、否定词、单位与符号。保留英文原句和页码，译文不能代替原文证据。

## 把查到的词带入 Obsidian

无需把每个生词都做成一篇笔记。只把影响论文理解、与你课题相关或多次遇到的术语记下来。

在文献笔记的**个人笔记保留区**记录以下内容：

```markdown
### 本篇术语

| 英文词 / 短语 | 本文语境中的含义 | 原句 / 页码 | 我的理解或疑问 |
| --- | --- | --- | --- |
| 待填写 | 待核实 | 待填写 | 待填写 |
```

当一个术语需要进一步解释物理概念或数学关系时，在 `40_Knowledge` 建立知识卡片，用 `aliases` 保存英文全称、缩写和中文常用名，再从文献笔记链接过去。别名写到该概念卡片，不要批量加到不相关笔记。

**推荐每次阅读的收尾**：挑 1–3 个关键术语，写出语境义、来源页码与一条自己的解释；暂时解释不了就留下具体问题。译文和词典内容标明来源，个人理解单独写。

如果你选择把译文保存到 Zotero 批注的 comment，随后可通过 Zotero Integration 再导入 Obsidian；这是你主动保存后的导入流程，查词浮窗本身不会自动成为 Obsidian 知识卡片。

## 其他查词/翻译工具的取舍

| 方案 | 更适合什么 | 本次处理 |
| --- | --- | --- |
| Translate for Zotero | 单词词典、发音和选段翻译；已有稳定版可兼容当前 Zotero | 已安装 |
| WordPop | 需要离线英文释义；作者介绍使用 WordNet，并可添加自定义词表 | 仅调研，未安装，未在本机核验 |
| Z-Transplit | 更重视双语阅读、全文翻译与版式保持 | 仅调研，未安装；并非本次查词需求所必需 |

无需同时安装多个选词浮窗插件；重叠的自动查询可能让界面变乱。后续确实需要离线词库或全文双语阅读时，再单独配置。

## 来源

- [Translate for Zotero 作者文档：安装、使用、词典和服务设置](https://github.com/windingwind/zotero-pdf-translate)
- [稳定版 v2.4.8](https://github.com/windingwind/zotero-pdf-translate/releases/tag/v2.4.8)
- [Zotero 官方插件安装说明](https://www.zotero.org/support/plugins)
- [WordPop 作者在 Zotero 论坛的介绍](https://forums.zotero.org/discussion/134381/wordpop-free-offline-dictionary-plugin-for-the-pdf-reader-zotero-7-10)
- [Z-Transplit 作者文档](https://github.com/Liozhang/z-transplit)
