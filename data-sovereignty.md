---
title: "数据主权"
layout: default
nav_order: 11
type: concept
confidence: high
updated: 2026-06-20
sources:
  - raw/articles/2026-06-20-evernote-decline.md
  - raw/articles/2026-06-20-roam-decline.md
  - raw/articles/2026-06-20-pkm-fatigue.md
  - raw/articles/2026-06-20-notion-offline-limitations.md
see_also:
  - overview
  - local-first-vs-cloud
  - tool-comparison
---

# 数据主权与锁定风险

## 两种锁定

### 格式锁定
- **高危** (专有格式): Roam (Datomic), Tana (Graph DB), Notion (Block DB), Evernote, Bear (Core Data), Craft (Realm)
- **中危** (结构化开放格式): SiYuan (.sy JSON), Anytype (加密 DAG)
- **低危** (纯文本): Obsidian (.md), Logseq (.md/.org), Joplin (.md)

### 供应商锁定
- 云端工具的用户数据完全依赖供应商的持续运营和定价策略
- Bending Spoons 收购 Evernote 后: 免费层从可用降至 50 条笔记，付费翻倍
- Roam Research: 产品停滞 4 年+，但迁移成本极高
- Notion: AI 功能从 $8-10/mo 独立附加变为 $20/用户/mo Business 独家

## 警示案例

### Evernote (2012-2026)
- 从笔记领导者到"收割"目标
- 产品膨胀 → 核心腐烂 → 隐私丑闻 → 被收购 → 激进提价
- 免费用户一夜之间只能存 50 条笔记

### Roam Research (2020-2024)
- 创造双向链接范式，但被所有竞争者复制并超越
- 产品 4 年未更新 → 用户被困在专有 Datomic 格式中
- JSON 导出 bug：静默截断数据，时间戳格式损坏

## 出口策略评估

| 工具 | 导出质量 | 迁移难度 |
|------|---------|---------|
| **Obsidian** | ⭐⭐⭐⭐⭐ 完美 | 文件夹复制即可 |
| **Logseq** | ⭐⭐⭐⭐⭐ 完美 | 文件夹复制即可 |
| **Joplin** | ⭐⭐⭐⭐ 良好 | Markdown 完整，元数据需处理 |
| **Bear** | ⭐⭐⭐⭐ 良好 | 多格式导出，但丢标签结构 |
| **SiYuan** | ⭐⭐⭐ 中等 | .sy JSON 可解析，不如纯 Markdown |
| **Notion** | ⭐⭐⭐ 中等 | Markdown/HTML 导出，数据库关系丢 |
| **Capacities** | ⭐⭐⭐ 中等 | Markdown 导出，对象类型语义丢 |
| **Tana** | ⭐⭐ 较差 | JSON 导出丢 Supertag 语义 |
| **Roam** | ⭐ 很差 | EDN/JSON bug 多，数据可能丢失 |
| **Heptabase** | ⭐ 很差 | 导出非常有限 |

## 减轻锁定风险

1. **优先选择开放格式** — Markdown/纯文本永远优于专有格式
2. **定期导出** — 即使格式不完美，有备份 > 无备份
3. **分开关键数据** — 核心笔记存 Obsidian/Logseq，协作内容放 Notion/云端
4. **警惕被收购的工具** — 免费层和定价随时可能剧变
5. **评估开源替代** — Logseq, SiYuan, AppFlowy, Joplin 的 AGPL 保证你永远有办法访问数据
