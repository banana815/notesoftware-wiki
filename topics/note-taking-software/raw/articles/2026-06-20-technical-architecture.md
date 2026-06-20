---
title: "笔记软件技术架构全景：CRDT、文件格式、同步机制"
source: "Multiple technical documentation and architecture analyses (Anytype, Logseq, AppFlowy, SiYuan, Joplin, Obsidian, Craft, Standard Notes)"
urls:
  - https://tech.anytype.io/any-sync/overview
  - https://deepwiki.com/logseq/logseq/1-overview
  - https://deepwiki.com/AppFlowy-IO/AppFlowy/2-architecture-overview
  - https://deepwiki.com/siyuan-note/siyuan/2.2-data-model-and-storage
  - https://deepwiki.com/laurent22/joplin
  - https://github.com/obsidianmd/obsidian-api
  - https://standardnotes.com/help/security/encryption
  - https://www.craft.do/blog/in-house-sync-protocol
type: articles
tags: [architecture, crdt, sync, file-format, encryption, local-first]
confidence: high
quality_score: 4
credibility: high
---

# 笔记软件技术架构全景

## 架构光谱：四种模式

### A. 纯本地优先（文件在磁盘）
- **Obsidian, Logseq (file mode), Joplin**: Markdown/Org 文件在文件系统。App 只是 shell，无网络也能完整工作。
- **Bear**: 本地 SQLite/Core Data，无服务端组件。

### B. 本地优先（加密对象存储）
- **Anytype**: 加密 DAG 对象存储，CRDT P2P 同步，满足 local-first 软件的 7 个理想。
- **Standard Notes**: 客户端加密先于传输，服务端是零知识中继。
- **SiYuan**: `.sy` JSON 文件 + SQLite 索引（可重建），Go 内核本地 HTTP 服务。

### C. 云端优先 + 离线支持
- **Notion**: 历史上纯云端（CouchDB），2024+ 离线模式是附加功能，数据主副本在服务端。
- **Tana, Capacities, Heptabase**: SaaS 云端优先，本地缓存提供有限离线弹性。
- **Craft**: Realm 本地持久化 + 自建 socket.io 同步协议 + PostgreSQL。

### D. 混合 / DIY
- **Obsidian/Logseq 同步**: 官方付费 CRDT 同步或 DIY (Git, Syncthing, iCloud, Dropbox)

## 文件格式

| 工具 | 格式 | 可移植性 |
|------|------|----------|
| **Obsidian** | Markdown (.md) | ✅ 纯文本 |
| **Logseq** | Markdown / Org-mode | ✅ 纯文本 |
| **Joplin** | Markdown + SQLite | ⚠️ .md 可读，元数据在 SQLite |
| **SiYuan** | .sy JSON AST + SQLite | ⚠️ .sy 是结构化 JSON |
| **Bear** | Core Data / SQLite | ❌ 专有，可导出 Markdown |
| **Anytype** | 加密 DAG 对象 | ❌ 内部二进制，可导出 Markdown/Protobuf |
| **Notion** | Block DB (CouchDB) | ❌ 云端托管，可导出 Markdown/HTML |
| **Roam** | Datomic Datalog | ❌ 导出 EDN/JSON 常丢数据 |
| **Tana** | Graph DB (专有) | ❌ JSON 导出丢语义 |

## 同步机制

| 机制 | 工具 | 说明 |
|------|------|------|
| **Yjs/Yrs CRDT** | Anytype, AppFlowy, Logseq (DB), Obsidian Sync, YAOS | 主导 CRDT 库，Yjs (JS) + Yrs (Rust port) |
| **Automerge CRDT** | Muddle | 备选库，较少 |
| **OT (Operational Transform)** | 旧方案 | 现代工具已转向 CRDT |
| **文件级同步** | Obsidian, Logseq, Joplin | Git, Syncthing, iCloud（有合并冲突风险） |
| **自建协议** | Craft (socket.io+PG), Notion (CouchDB) | 公司自建同步引擎 |
| **快照同步** | SiYuan (Dejavu) | AES-256 加密，内容寻址 |
| **P2P 加密** | Anytype (Any-Sync) | 无中心注册节点，用户控制密钥 |

## 加密与隐私

| 工具 | 加密方案 | 零知识 |
|------|---------|--------|
| **Standard Notes** | XChaCha20-Poly1305 + Argon2 层级密钥系统 | ✅ 最佳 |
| **Anytype** | AES-CFB + Ed25519 双层加密 | ✅ |
| **SiYuan** | AES-256（仅同步快照） | ⚠️ .sy 文件不加密 |
| **Joplin** | RSA E2EE（node-rsa） | ✅ |
| **Obsidian Sync** | E2E 加密 | ✅（付费同步） |
| **Notion** | TLS 传输 + 服务端加密 | ❌ 可读取内容 |
| **Tana, Roam, Capacities, Heptabase** | TLS 传输 | ❌ 无 E2EE |

## 开源格局

| 许可 | 工具 |
|------|------|
| **AGPL v3** | Logseq, AppFlowy, SiYuan, Joplin, Standard Notes |
| **MIT/MPL-2.0** | Anytype (Any-Sync MIT, core MPL-2.0) |
| **专有** | Obsidian, Heptabase, Tana, Capacities, Roam, Notion, Bear, Craft, Amplenote |
