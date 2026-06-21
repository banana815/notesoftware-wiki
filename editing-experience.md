---
title: "编辑体验"
layout: default
nav_order: 3
type: concept
confidence: medium
updated: 2026-06-20
sources:
  - raw/articles/2026-06-20-pkm-deep-dive.md
  - raw/articles/2026-06-20-technical-architecture.md
  - raw/articles/2026-06-20-trillium-apple-onenote.md
  - raw/articles/2026-06-20-chinese-apps.md
see_also:
  - file-management
  - tool-comparison
  - local-first-vs-cloud
---

# 笔记软件编辑体验评价

## 编辑器范式分类

### Markdown 源码编辑
代表: **Obsidian**（可切换 Live Preview）, **Joplin**, **Bear**

- 优点: 键盘驱动、纯文本可移植、Git 友好
- 缺点: 排版不可见、表格和图片编辑不便、非技术用户有学习成本
- 评分最高场景: 技术写作、长文创作

### Block 编辑器
代表: **Notion**, **Craft**, **Wolai**, **FlowUs**, **AppFlowy**

- 优点: 拖拽灵活、多媒体嵌入自如、结构可视化、slash 命令快捷
- 缺点: 鼠标依赖、键盘流不够流畅、大文档性能可能下降
- 评分最高场景: 结构化文档、团队 Wiki、项目管理

### Outliner（大纲式）
代表: **Logseq**, **Roam Research**, **Workflowy**, **Dynalist**, **Tana**

- 优点: 层级清晰、块级引用精确、折叠/展开操作便捷、键盘流友好
- 缺点: 不适合长段落写作、视觉密度高、思维需要适应 bullet 习惯
- 评分最高场景: 日记、会议记录、研究笔记、头脑风暴

### WYSIWYG 富文本
代表: **Apple Notes**, **OneNote**, **Bear**, **Craft**, **SiYuan**, **Capacities**, **Heptabase**

- 优点: 所见即所得、零学习成本、排版效果即时可见
- 缺点: 底层格式不透明、Markdown 兼容性差异、跨工具粘贴格式漂移
- 评分最高场景: 日常笔记、快速记录、多媒体笔记

### 自由画布
代表: **OneNote**, **Heptabase**, **Milanote**, **Obsidian Canvas**

- 优点: 空间自由、视觉思维、适合大局观
- 缺点: 打印/导出困难、长文本编辑弱、搜索限制
- 评分最高场景: 头脑风暴、项目规划、创意设计

### 手写笔记
代表: **Notability**, **GoodNotes**, **OneNote (ink)**, **Apple Notes (Pencil)**

- 优点: 自然书写感、图表公式随手画、PDF 直接批注
- 缺点: 搜索依赖 OCR、难以全文检索、存储体积大
- 评分最高场景: 课堂笔记、文献批注、数学物理推导

## 编辑体验评分矩阵

评分标准: 5=卓越 4=优秀 3=良好 2=一般 1=差

| 工具 | 打字响应 | 格式化丰富度 | 快捷键 | 移动端编辑 | 块操作 | 综合 |
|------|---------|------------|--------|-----------|--------|------|
| **Obsidian** | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | **4.0** |
| **Notion** | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ | **3.8** |
| **Logseq** | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | **3.8** |
| **SiYuan** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | **3.8** |
| **Craft** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | **4.0** |
| **Bear** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐ | **3.3** |
| **Tana** | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ | **3.3** |
| **Capacities** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | **3.4** |
| **Heptabase** | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐ | **2.8** |
| **Anytype** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | **3.8** |
| **Roam** | ⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐ | ⭐⭐⭐⭐ | **2.5** |
| **Apple Notes** | ⭐⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐ | **3.3** |
| **OneNote** | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐ | **2.7** |
| **Trilium** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐ | ⭐⭐⭐ | **2.8** |
| **Notability** | N/A | ⭐⭐ | ⭐ | ⭐⭐⭐⭐⭐ | ⭐ | **2.3** |
| **GoodNotes** | N/A | ⭐⭐ | ⭐ | ⭐⭐⭐⭐ | ⭐ | **2.2** |
| **语雀** | ⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | ⭐⭐ | **2.7** |
| **Wolai** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐ | **3.8** |
| **FlowUs** | ⭐⭐⭐⭐ | ⭐⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐⭐⭐ | ⭐⭐⭐⭐ | **4.0** |
| **RemNote** | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐ | ⭐⭐⭐ | **2.7** |
| **Amplenote** | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | ⭐⭐⭐ | **3.0** |

## 按编辑范式排行

### 最快书写速度（打开即写）
1. **Apple Notes** — 原生、零摩擦
2. **Bear** — 极简 Markdown、Apple 原生
3. **UpNote** — 轻量实时渲染

### 最强结构化编辑
1. **Notion** — Block 拖拽 + 数据库内联编辑
2. **Tana** — Supertag 自动填充结构化字段
3. **SiYuan** — 块级 UUID 引用 + 属性视图

### 最佳键盘流
1. **Obsidian** — Vim 键位 + 全键盘操作
2. **Logseq** — Outliner 键盘驱动
3. **Wolai** — 中英文排版快捷键

### 最佳移动端编辑
1. **Apple Notes** — 原生 iOS/macOS 优化
2. **FlowUs** — 原生开发移动端，极速记录
3. **Craft** — Realm 本地 + 实时渲染
4. **Notability/GoodNotes** — Apple Pencil 体验最佳

### 最佳写作体验
1. **Bear** — 专注模式 + 精美的 Markdown 渲染
2. **Craft** — Block 编辑器 + 多模型 AI 行内辅助
3. **语雀** — 技术文档写作（代码/公式/流程图）

## 关键发现

1. **编辑体验不等于功能数量**: Bear 功能很少但编辑体验顶尖，Notion 功能极多但"迟缓"
2. **本地优先工具通常编辑更快**: Obsidian/SiYuan/Joplin 本地读写，延迟低；Notion/Roam/Tana 依赖网络
3. **移动端编辑是分水岭**: Apple Notes/FlowUs/Craft/Anytype 的移动端体验与桌面接近，其余大多有明显落差
4. **范式匹配 > 功能对比**: outline 思维者无法适应 Notion，block 思维者无法适应 Logseq
5. **AI 正改变编辑方式**: 语音录入+AI 转录+AI 结构化（Tana, Notion, OneNote）正在从"打字"转向"描述需求"
