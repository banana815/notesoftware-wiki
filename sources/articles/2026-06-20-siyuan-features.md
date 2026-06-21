---
layout: default
nav_exclude: true
title: "思源笔记 (SiYuan)：开源自托管 PKM 的完整方案"
source: "dev.to, GitHub, deepwiki.com"
urls:
  - https://dev.to/selfhostingsh/siyuan-vs-obsidian-which-to-self-host-11mk
  - https://deepwiki.com/siyuan-note/siyuan/2.2-data-model-and-storage
type: articles
tags: [siyuan, open-source, self-hosted, chinese-market]
confidence: high
quality_score: 4
credibility: high
---

# 思源笔记 (SiYuan)

## 技术架构

- 完全开源（AGPL-3.0），TypeScript + Go
- **双存储**: `.sy` JSON 文件（AST，可读）+ SQLite 数据库（FTS5 全文搜索索引，可重建）
- **块级引用**: 每个段落/标题/列表都有 UUID，可单独引用
- Go 内核运行本地 HTTP 服务（端口 6806），Electron/React 前端

## 核心功能

- WYSIWYG Markdown 编辑器
- 内置数据库视图（表格、画廊、看板）— Attribute Views
- PDF 批注
- 间隔重复（FSRS 算法）
- AI 集成（OpenAI API）
- Tesseract OCR
- REST API (200+ 端点)
- Web Clipper (Chrome/Edge)
- Docker 部署（单容器，200-400MB RAM）
- 快照同步（Dejavu 引擎，AES-256 加密）

## 社区与状态

- 44,000+ GitHub Stars
- 2026 年活跃开发（v3.5.3, Jan 2026）
- 中国国内市场主要玩家
- 中文支持最佳

## 与 Obsidian 对比

| 维度 | SiYuan | Obsidian |
|------|--------|----------|
| 许可 | AGPL-3.0 开源 | 专有 |
| 文件格式 | .sy JSON | .md 纯文本 |
| 数据库 | 内置 SQLite + 属性视图 | Bases (YAML GUI) |
| 块级引用 | UUID 原生 | 块引用（Markdown 扩展） |
| 同步 | Dejavu 快照 | 付费 CRDT Sync |
| 自托管 | Docker 一键 | Headless client (2026) |
| 插件 | ~100 | 2,500+ |
| 可移植性 | .sy JSON 格式 | 纯文本 .md |

## 劣势

- `.sy` JSON 格式不如纯 Markdown 可移植
- 插件生态远小于 Obsidian
- 非中文用户文档较弱
