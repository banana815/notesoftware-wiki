---
title: "CRDT 在笔记软件中的工程实践 2025-2026"
source: "Multiple engineering sources (YAOS, Anytype, SwarmNote, Bobkonf Yjs workshop, Open WebUI)"
urls:
  - https://tech.anytype.io/any-sync/overview
type: articles
tags: [crdt, engineering, sync, p2p]
confidence: medium
quality_score: 3
credibility: high
---

# CRDT 在笔记软件中的工程实践

## CRDT 部署模式

### 1. 单体 Vault CRDT（YAOS / Obsidian）
- 整个 vault 使用单个 `Y.Doc`
- 每个 Markdown 文件有稳定 ID + `Y.Text`
- 部署在 Cloudflare Durable Objects（免费层）
- 离线编辑存储在 IndexedDB，重连时合并

### 2. 对象级 CRDT DAG（Anytype）
- 每个对象是 CRDT DAG，内容寻址变更节点
- 双层加密：结构层 + 数据层（AES-CFB）
- 通过拓扑排序计算当前状态
- P2P 发现用 mDNS，全局网络用协调节点
- 文件同步用 IPFS；对象同步用 IPLD

### 3. 文档级 CRDT（AppFlowy）
- Yrs（Rust Yjs port）为 CRDT 引擎
- RocksDB 存储 CRDT 状态
- 插件式持久化架构：`RocksdbDiskPlugin`（本地）+ `SyncPlugin`（WebSocket 云端）
- 云端是 trait-based 抽象（可替换实现）

### 4. 快照 + 增量（SiYuan Dejavu）
- AES-256 加密的内容寻址仓库快照
- 非 CRDT，而是 snapshot-based
- 支持 S3、WebDAV

### 5. 增量同步 + GossipSub（SwarmNote P2P）
- 全量同步（连接时 Req-Resp）
- 增量同步（GossipSub 实时 Yjs 更新）
- Lamport 时钟冲突解决

## CRDT vs OT 共识

- CRDT 被现代系统优先选择
- OT 引入新操作类型是 O(n²)；CRDT 是线性的
- OT 需要中央排序器；CRDT 本地优先 + 确定性合并

## 新兴模式

- **双缓冲暂存**：高频编辑的 staging 缓冲区
- **Checkpoint + Delta Journal**：替换全状态重写为以 state-vector 为锚的增量
- **Rolling Compaction**：阈值触发最旧半数更新合并为快照（Open WebUI 的 pycrdt）
- **Edge 平台 Durable Objects**：有状态同步房间（YAOS 用 Cloudflare）
