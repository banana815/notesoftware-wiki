---
title: "Trilium / Apple Notes / OneNote 深度分析 2026"
source: "XDA Developers, 9to5Mac, Windows Report, MacRumors, dev.to"
urls:
  - https://www.xda-developers.com/self-hosted-notes-app-make-me-ditch-google-keep/
  - https://www.xda-developers.com/trilium-next-notion-alternative/
  - https://dev.to/selfhostingsh/trilium-vs-siyuan-which-to-self-host-5gg7
  - https://9to5mac.com/2026/06/10/heres-everything-new-for-apple-notes-in-ios-27/
  - https://windowsreport.com/copilot-in-onenote-now-understands-images-tables-note-tags-to-offer-better-response/
type: articles
tags: [trilium, apple-notes, onenote, self-hosted, enterprise]
confidence: medium
quality_score: 4
credibility: high
---

# Trilium / Apple Notes / OneNote

## TriliumNext (Trilium Notes 社区版)

原项目停止维护，社区 fork 为 TriliumNext，是目前活跃开发版本。

### 编辑体验
- 富文本 WYSIWYG + Markdown 混合编辑
- 内置代码片段（语法高亮）、表格、图片
- **层级树 + 笔记克隆**：同一笔记可存在于多个位置（类似符号链接），修改一处，所有位置同步更新
- 此克隆功能是 Trilium 的杀手级特性

### 文件管理
- 单 SQLite 数据库（加密），备份即复制 DB 文件
- 自托管同步：单 Docker 容器，~100-300MB RAM
- 完整修订历史（一键快照、任意版本回滚）
- 内置 JS 脚本引擎（ETAPI）：自动化笔记创建、自定义端点
- 关系图（类似 Obsidian Graph View）
- 公开笔记分享
- 导出：Markdown、HTML、单文件备份

### 劣势
- 无原生移动端（仅 Web/PWA，编辑体验不佳）
- 单用户设计（无团队协作）
- SQLite 存储（非 Markdown 文件在磁盘）
- 社区较小（~27K stars vs Obsidian 的庞大生态）
- UI 偏功能实用型（非 Notion 式精美）

## Apple Notes (iOS 26-27, 2025-2026)

### 2025-2026 重大更新
- **iOS 26**: Liquid Glass UI 重新设计、自适应工具栏（18 个按钮）、音频录制+实时转录、电话录音自动保存到 Notes、**Markdown 导入/导出**、3D 数学图表（iPad）、Notes 登陆 Apple Watch
- **iOS 26.4** (rumored): Gemini 驱动的 Siri AI 集成，可语音创建/总结笔记
- **iOS 27** (Fall 2026): 分隔线、Siri "Add to Note"、Markdown 粘贴自动转换为富文本、"Copy as Markdown"选项、Image Playground 升级（照片级 AI 图像生成+SynthID 水印）、Markup 工具扩展

### 编辑体验
- 原生 iOS/macOS WYSIWYG，极速且流畅
- Apple Pencil 手写支持（Reed Pen 书法工具）
- 内联绘图、文档扫描、表格
- 标签和智能文件夹
- Quick Notes（从任意 app 滑动呼出）

### 文件管理
- iCloud 同步（原生、自动）
- 文件夹 + 标签组织
- Spotlight 集成搜索
- 版本历史（macOS）
- Markdown 导入/导出（iOS 26+ 新增）

### 定位
免费的 Apple 生态内置工具。2025-2026 的更新使其从一个"备忘录"升级为有竞争力的全功能笔记工具。但仅限于 Apple 生态。

## Microsoft OneNote (2025-2026)

### AI 升级
- **Copilot Chat 面板** (Dec 2025): AI 摘要/任务列表/改写直接在侧栏显示
- **Copilot Notebooks**: 与 OneNote 深度同步，三栏布局（参考 | Copilot Pages | Chat），自动生成概览页
- **AI 理解图像/表格/手写** (April 2026): 不再限于纯文本，可分析页面上的所有元素
- iPhone 端 AI 笔记生成：录音+拍照+打字 → AI 自动合成为结构化笔记

### 编辑体验
- **自由画布**: 点击页面任意位置开始输入，无限空间排版
- **墨迹/手写**（无可匹敌的 ink 体验）
- 数学助手、录音同步笔记
- 笔记本 → 分区 → 页面三级结构

### 文件管理
- OneDrive 同步
- 内建版本历史
- Rich 附件支持（PDF 打印输出、音频、嵌入文件）
- 企业治理：Purview 敏感度标签 (Jan 2026)、DLP 策略
- 图像 OCR + 手写搜索
- 跨平台：Windows, Mac, iOS, Android, Web

### 劣势
- 无双向链接、无图谱视图
- 无 Markdown 原生支持
- Copilot AI 需要付费 Microsoft 365 Copilot 许可（April 2026 取消免费 Copilot Chat）
- 数据库结构化不如 Notion
