---
title: "功能对比"
layout: default
nav_order: 8
type: concept
confidence: high
updated: 2026-06-20
sources:
  - raw/articles/2026-06-20-pkm-deep-dive.md
  - raw/articles/2026-06-20-ai-comparison.md
  - raw/articles/2026-06-20-technical-architecture.md
  - raw/data/2026-06-20-pricing-comparison.md
see_also:
  - overview
  - local-first-vs-cloud
  - ai-in-note-taking
---

# 笔记软件功能对比矩阵

## 核心功能对比

| 工具 | 双向链接 | 图谱 | 数据库/表格 | AI | 协作 | 离线 | 开源 |
|------|---------|------|------------|-----|------|------|------|
| **Obsidian** | ✅ | ✅ | ✅ Bases | ⚠️ 插件 | ❌ | ✅ | ❌ |
| **Notion** | ⚠️ 有限 | ❌ | ✅ 强 | ✅ 原生 | ✅ 强 | ⚠️ 弱 | ❌ |
| **Logseq** | ✅ | ✅ | ✅ DB版 | ⚠️ 有限 | ❌ | ✅ | ✅ AGPL |
| **Anytype** | ✅ | ✅ | ✅ 对象 | ❌ | ⚠️ 开发中 | ✅ | ✅ MPL |
| **Tana** | ✅ | ✅ 节点图 | ✅ Supertags | ✅ Agent | ❌ | ❌ | ❌ |
| **Capacities** | ✅ | ✅ | ✅ 对象 | ✅ Assistant | ❌ | ✅ | ❌ |
| **Heptabase** | ✅ | ⚠️ 白板 | ⚠️ 有限 | ✅ Tutor | ✅ 白板 | ⚠️ 部分 | ❌ |
| **SiYuan** | ✅ 块级 | ✅ | ✅ 属性 | ⚠️ API | ❌ | ✅ | ✅ AGPL |
| **AppFlowy** | ⚠️ 有限 | ❌ | ✅ 表 | ❌ | ⚠️ 计划 | ✅ | ✅ AGPL |
| **Joplin** | ⚠️ 有限 | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ AGPL |
| **Bear** | ⚠️ Wiki链接 | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| **Craft** | ⚠️ 有限 | ❌ | ✅ Collections | ✅ 多模型 | ✅ RT | ✅ | ❌ |
| **RemNote** | ✅ | ✅ | ❌ | ✅ 闪卡 | ❌ | ✅ | ❌ |
| **Amplenote** | ✅ | ❌ | ❌ | ✅ Agent | ❌ | ⚠️ 有限 | ❌ |
| **Reflect** | ✅ | ❌ | ❌ | ✅ 原生 | ❌ | ⚠️ 有限 | ❌ |
| **Mem.ai** | ✅ 自动 | ❌ | ❌ | ✅ 核心 | ❌ | ✅ 2.0 | ❌ |
| **Roam** | ✅ | ✅ | ❌ | ❌ | ❌ | ⚠️ 弱 | ❌ |
| **UpNote** | ⚠️ 有限 | ❌ | ❌ | ❌ | ❌ | ✅ | ❌ |
| **Standard Notes** | ❌ | ❌ | ❌ | ❌ | ❌ | ✅ | ✅ AGPL |

## 按使用场景推荐

| 场景 | 推荐 | 原因 |
|------|------|------|
| **个人知识管理 (PKM)** | Obsidian, Logseq | 本地文件、插件生态、数据所有权 |
| **团队协作** | Notion, Craft | 实时协作、权限管理、数据库 |
| **学术研究** | Heptabase, RemNote, Obsidian+Zotero | 文献管理、闪卡、白板思维 |
| **日记/大纲式笔记** | Logseq, Roam, Tana | 每日笔记优先、outliner、块引用 |
| **AI 原生笔记** | Tana, Notion, Reflect, Mem | 内置 AI Agent、自动关联、转录 |
| **极简书写** | Bear, UpNote, Apple Notes | 低摩擦、快速、专注 |
| **数据隐私至上** | Standard Notes, Anytype | E2EE、零知识架构 |
| **自托管/开源** | SiYuan, AppFlowy, Joplin, Logseq | 完全控制、Docker 部署 |
| **性价比** | UpNote ($39.99 终身), Logseq (免费) | 最低长期成本 |
| **Apple 生态** | Bear, Craft, NotePlan, Agenda | 原生 Apple 体验 |

## 学习曲线

```
简单 ──────────────────────────────────────────> 复杂
Apple Notes    Bear    UpNote    Craft    Notion    Obsidian    Logseq    Tana
(分钟)         (小时)   (小时)   (天)     (天)       (周)        (周)       (周+)
```
