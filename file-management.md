---
title: "文件管理"
layout: default
nav_order: 4
type: concept
confidence: high
updated: 2026-06-20
sources:
  - raw/articles/2026-06-20-technical-architecture.md
  - raw/articles/2026-06-20-crdt-engineering.md
  - raw/data/2026-06-20-pricing-comparison.md
  - raw/articles/2026-06-20-trillium-apple-onenote.md
see_also:
  - editing-experience
  - data-sovereignty
  - tool-comparison
---

# 笔记软件文件管理评价

## 文件格式：数据可移植性的根基

```
纯文本 ←─────────────────────────────→ 专有锁定
   .md      .sy JSON    SQLite    加密二进制   云端 DB
Obsidian   SiYuan     Trilium     Anytype    Notion
Logseq     Joplin     Bear        Standard   Roam
                           Notes      Tana
```

### 评估维度

| 工具 | 存储格式 | 可读性 | 版本控制 | 导出完整性 | 评分 |
|------|---------|--------|---------|-----------|------|
| **Obsidian** | .md 纯文本 | ⭐⭐⭐⭐⭐ | Git 完美 | ⭐⭐⭐⭐⭐ | **5.0** |
| **Logseq** | .md/.org | ⭐⭐⭐⭐⭐ | Git 完美 | ⭐⭐⭐⭐⭐ | **5.0** |
| **Joplin** | .md + SQLite | ⭐⭐⭐⭐ | Git (.md) | ⭐⭐⭐⭐ | **4.0** |
| **SiYuan** | .sy JSON + SQLite | ⭐⭐⭐ | SQLite 可重建 | ⭐⭐⭐ | **3.0** |
| **Trilium** | SQLite | ⭐⭐ | 无 | ⭐⭐⭐ | **2.5** |
| **Bear** | Core Data/SQLite | ⭐ | 无 | ⭐⭐⭐⭐ | **2.0** |
| **Anytype** | 加密 DAG | ⭐ | 无 | ⭐⭐⭐ | **2.0** |
| **Standard Notes** | 加密 JSON | ⭐ | 无 | ⭐⭐⭐ | **2.0** |
| **Notion** | 云端 Block DB | ⭐ | 无 | ⭐⭐⭐ | **1.5** |
| **Roam** | Datomic Datalog | ⭐ | 无 | ⭐ | **1.0** |
| **Tana** | 专有 Graph DB | ⭐ | 无 | ⭐ | **1.0** |
| **Craft** | Realm + PG | ⭐ | 无 | ⭐⭐⭐ | **1.5** |
| **Heptabase** | 云端对象 | ⭐ | 无 | ⭐ | **1.0** |
| **Capacities** | 云端对象 | ⭐ | 无 | ⭐⭐⭐ | **1.5** |
| **Apple Notes** | iCloud 内部 | ⭐ | 有限 | ⭐⭐⭐ | **1.5** |
| **OneNote** | OneDrive 内部 | ⭐ | 内建 | ⭐⭐⭐ | **1.5** |
| **Notability** | .note 专有 | ⭐ | 无 | ⭐⭐ | **1.0** |
| **GoodNotes** | 专有 + PDF | ⭐⭐ | 无 | ⭐⭐⭐ | **1.5** |
| **UpNote** | 内部 | ⭐ | 无 | ⭐⭐⭐ | **2.0** |

## 组织模型

| 模型 | 工具 | 评价 |
|------|------|------|
| **文件夹 + 标签** | Obsidian, Joplin, Apple Notes, UpNote | 经典、可预测、文件系统友好 |
| **纯标签** | Bear (#嵌套/标签) | 灵活但大型库可能迷失 |
| **笔记本→分区→页面** | OneNote, Evernote | 物理笔记本隐喻，直观但有层级限制 |
| **日记优先 Outliner** | Logseq, Roam | 以时间为轴，天然适合日志和会议记录 |
| **Typed Objects** | Capacities, Anytype, Tana (Supertags) | 现代化，结构化强，但导出丢语义 |
| **关系型数据库** | Notion (表格/看板/日历), SiYuan (属性视图) | 最强查询，但学习成本高 |
| **空间/画布** | Heptabase (白板+卡片), Milanote | 视觉思维首选，不适合纯文本 |
| **日历锚定** | NotePlan, Agenda, Amplenote | 时间线组织，任务管理一体化 |

## 搜索能力

| 工具 | 全文搜索 | 正则 | AI 语义 | OCR | 备注 |
|------|---------|------|---------|-----|------|
| **Obsidian** | ✅ | ✅ | ⚠️ 插件 | ❌ | 社区插件补全语义搜索 |
| **Notion** | ✅ | ❌ | ✅ 付费 | ❌ | AI 搜索仅 Business 计划 |
| **Logseq** | ✅ | ❌ | ❌ | ❌ | 块级搜索 + Datalog 查询 |
| **SiYuan** | ✅ FTS5 | ❌ | ❌ | ✅ Tesseract | 中文分词友好 |
| **Heptabase** | ✅ | ❌ | ✅ AI Chat | ❌ | AI 含全白板上下文 |
| **Tana** | ✅ | ❌ | ✅ Live Search | ❌ | 查询作为一等节点 |
| **OneNote** | ✅ | ❌ | ✅ Copilot | ✅ 图像/手写 | 手写 OCR 最强 |
| **Evernote v11** | ✅ | ❌ | ✅ AI | ✅ | AI 语义搜索 + OCR |
| **Apple Notes** | ✅ (Spotlight) | ❌ | ❌ | ✅ | 深度 iOS 集成 |
| **Reflect** | ✅ | ❌ | ✅ GPT-4o/Claude | ❌ | AI 原生搜索 |
| **Trilium** | ✅ | ✅ | ❌ | ❌ | 属性查询 + 全文搜索 |

## 导入/导出：迁移成本

### 导出质量排行

| 等级 | 工具 | 说明 |
|------|------|------|
| 🟢 **完美** | Obsidian, Logseq | 复制文件夹即可。全部链接和元数据保留 |
| 🟢 **优秀** | Bear, Joplin | 多格式导出，标签可能丢失 |
| 🟡 **良好** | SiYuan, Notion, Capacities | 可用但结构化信息降级 |
| 🟠 **较差** | Tana, Roam | 大量语义丢失或数据截断风险 |
| 🔴 **极差** | Heptabase, Anytype | 导出非常有限，迁移痛苦 |

### 导入质量排行

| 等级 | 工具 | 备注 |
|------|------|------|
| 🟢 **最强** | Obsidian (社区插件), Joplin | 支持最多格式 |
| 🟢 **强** | Notion, Logseq, SiYuan | Evernote/Notion/Html/Markdown |
| 🟡 **一般** | Craft, Bear | 有限格式 |
| 🔴 **弱** | Tana, Capacities, Heptabase | 主要通过 Markdown |

## 同步机制

| 类型 | 工具 | 可靠性 |
|------|------|--------|
| **CRDT 实时同步** | Obsidian Sync ($4/mo), Anytype (P2P), AppFlowy (Yrs) | ⭐⭐⭐⭐⭐ 无冲突 |
| **快照同步** | SiYuan (Dejavu AES-256) | ⭐⭐⭐⭐ |
| **文件级同步** | Obsidian/Logseq via Git/Syncthing/iCloud | ⭐⭐⭐ 有合并冲突风险 |
| **多云同步** | Joplin (7+ 后端可选) | ⭐⭐⭐⭐ 最灵活 |
| **云端原生同步** | Notion, Tana, Capacities, Heptabase | ⭐⭐⭐⭐ 但依赖供应商 |
| **平台绑定** | Apple Notes (iCloud), OneNote (OneDrive), Keep (Google) | ⭐⭐⭐⭐ 无法跨生态 |

## 附件处理

| 工具 | 附件模型 | 评价 |
|------|---------|------|
| **Obsidian** | 本地文件在 vault 文件夹 | 完全控制，任意文件类型 |
| **Notion** | 云端 CDN，5MB 免费限制 | 离线图片变空白 |
| **Logseq** | 本地 assets/ 文件夹 | PDF 内置批注 |
| **SiYuan** | 本地 data 文件夹 | PDF 批注 + OCR |
| **FlowUs** | **文件夹页面（内置网盘）** | 杀手级：文件夹上传/预览/下载，Office/PDF 在线预览 |
| **Heptabase** | 内置 PDF 批注 + Zotero | 学术工作流最强 |
| **OneNote** | 嵌入 PDF 打印输出 + 任意文件 | 企业友好 |
| **Wolai** | 文件上传/批量导入 | 预览功能需付费 |

## 备份策略

| 策略 | 工具 | 说明 |
|------|------|------|
| 🟢 **零成本自动备份** | Obsidian, Logseq | Git 推送即备份，纯文本自动版本化 |
| 🟢 **单文件备份** | Trilium (SQLite), SiYuan (快照) | 复制一个文件即完整备份 |
| 🟡 **导出即备份** | Joplin (JEX), Bear (多格式), Notion (Markdown/HTML) | 需手动执行 |
| 🔴 **依赖供应商** | Tana, Capacities, Heptabase, Reflect | 无自动化备份，完全依赖云服务持续运营 |

## 关键结论

1. **文件格式 = 数据寿命**: .md 纯文本可保存 20 年，专有格式的寿命取决于公司存续
2. **导出是唯一的保险**: 即使使用云端工具，定期全量导出到 Markdown 是最低风险的策略
3. **组织模型应匹配思维模式**: 文件夹思维 → Obsidian/Joplin；对象思维 → Capacities/Anytype；标签思维 → Bear；时间思维 → Logseq/Agenda
4. **同步机制影响体验**: CRDT > 快照 > 文件级 > DIY。若跨设备是刚需，优先选择 CRDT 同步方案
5. **搜索是使用频率最高的功能**: 即使组织得再好，最终都靠搜索找到笔记。评估工具的搜索质量比评估其组织模型更重要
6. **备份是最后防线**: Bending Spoons 对 Evernote 的做法证明——今天慷慨的免费层明天可能消失。永远确保你有本地备份
