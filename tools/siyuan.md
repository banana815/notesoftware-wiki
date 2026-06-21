---
title: "思源笔记 (SiYuan)"
layout: default
parent: "工具档案"
nav_order: 8
type: tool-profile
confidence: medium
updated: 2026-06-20
---

# 思源笔记 (SiYuan)

- **定位**: 功能最完整的开源自托管 PKM
- **许可**: AGPL-3.0
- **技术栈**: TypeScript + Go (内核)
- **GitHub**: 44,000+ Stars
- **平台**: macOS, Windows, Linux, iOS, Android, Docker

## 核心特性
- 块级引用（每个段落/标题/列表有 UUID）
- 内置数据库视图（表格、画廊、看板）— Attribute Views
- WYSIWYG Markdown 编辑器
- 间隔重复（FSRS）
- PDF 批注
- AI 集成（OpenAI API）
- Tesseract OCR
- REST API (200+ 端点)
- Web Clipper (Chrome/Edge)
- Docker 一键部署（200-400MB RAM）
- 快照同步（Dejavu 引擎，AES-256 加密）

## 优势
- 功能最完整的开源方案（内置数据库、闪卡、OCR、API）
- 块级架构允许精细引用
- Docker 部署简单
- 中文本地化最佳
- SQLite 可从 .sy JSON 完全重建

## 劣势
- .sy JSON 格式不如纯 Markdown 可移植
- 插件生态小（~100 vs Obsidian 的 2,500+）
- 国际文档弱（主要是中文）
- 非中文用户体验可能不佳

## 竞争定位
如果需要一个 Docker 自托管、功能完整的个人知识库，SiYuan 是最接近"开源 Obsidian + Notion 混合体"的方案。
