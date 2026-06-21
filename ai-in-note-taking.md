---
title: "AI 支持"
layout: default
nav_order: 10
type: concept
confidence: high
updated: 2026-06-20
sources:
  - raw/articles/2026-06-20-ai-deep-research.md
  - raw/articles/2026-06-20-ai-comparison.md
  - raw/articles/2026-06-20-notion-platform-pivot.md
see_also:
  - unique-features
  - tool-comparison
  - data-sovereignty
  - overview
---

# AI 在笔记软件中的应用 2026

## AI 架构模式

### 模式 1: 云端全托管 AI
- **代表**: Notion, Tana, Capacities, Reflect, Mem.ai, Evernote v11
- **特点**: AI 深度集成，零配置，服务端索引和推理
- **隐私代价**: 供应商可读取笔记内容用于推理

### 模式 2: 本地 Embedding + 云端 LLM（Hybrid RAG）
- **代表**: Obsidian (Smart Connections + Copilot), Khoj, Heptabase
- **特点**: 文档和嵌入向量留在本地，仅发送检索片段给云端 LLM
- **隐私**: 原始文件不离设备，仅极少量上下文上传

### 模式 3: 100% 本地 AI
- **代表**: Obsidian (Ollama/LM Studio 方案), Open Notebook
- **特点**: 模型在本地运行，零网络传输
- **硬件需求**: 8B 模型 16GB RAM，32B+ 模型需 RTX 4090+ 或 Apple Silicon 64GB+

### 模式 4: BYOK（自带 API Key）
- **代表**: Craft, SiYuan, Obsidian 多数插件
- **特点**: 用户自己管理 API 密钥，选择模型和成本
- **灵活性**: 最高，但需自行评估隐私政策

---

## AI 能力层级 2026

```
Level 0: 无 AI ────────── Bear, UpNote, Standard Notes, Joplin
Level 1: AI 写作辅助 ──── Apple Notes, OneNote (基础), Logseq (插件)
Level 2: AI 搜索/问答 ─── Capacities, Reflect, Craft, NotebookLM
Level 3: AI 自动结构化 ── Tana, RemNote, Capacities
Level 4: AI Tutor/教学 ── Heptabase, RemNote
Level 5: AI Agent 24/7 ── Notion Custom Agents, Tana Custom Agents
```

---

## 各工具 AI 能力详析

### Notion — 最激进的全栈 AI 平台

| 能力 | 详情 |
|------|------|
| **Personal Agent** | 每个用户独立 Agent，24/7 自主运行（最长 20 分钟连续任务） |
| **Custom Agents** | 2026.2 上线，100 万+ 已创建。定时/触发器执行，跨 workspace 共享 |
| **多模型** | GPT-5/5.5, Claude Sonnet 4, Claude Opus 4.6, Kimi K2.6 |
| **External Agents API** | Alpha。Claude/Cursor/Codex/自建 Agent 可直接接入 Notion |
| **Workers** | Beta。托管代码运行时，自定义 Agent 工具逻辑 |
| **Agent SDK** | Alpha。在 Notion 外部嵌入 Agent（CRM、Teams、Discord） |
| **AI Connectors** | Slack/Google Drive/GitHub/Linear/Jira/Figma/Amplitude/Stripe... |
| **MCP** | 深度支持，npm `notion-mcp-server` 自动优化 context tokens |
| **定价** | Business $20/seat/mo 含 AI。Custom Agents $10/1K credits/mo |

**评价**: Notion 已不是"笔记+AI"，而是"以 AI Agent 为核心的工作流基础设施"。月处理 4500 万+ AI 查询，82% Fortune 500 已激活 AI。AI 贡献 ~50% 近期收入增长。

### Tana — AI 与笔记结构最深的融合

| 能力 | 详情 |
|------|------|
| **AI Tag Autofill** | 从标题/内容自动填充 Supertag 字段（优先级、负责人、分类等） |
| **Voice Agent** | 2026.5 上线。自然语言创建 Agent，"Hey Tana" 语音唤醒，7 种声音风格 |
| **Live Meeting Digest** | 实时会议转录 + 截图 + AI 子区，会议结束即出结构化文档 |
| **AI Command Nodes** | AI 操作作为一等节点，与其他节点同等可引用和查询 |
| **Custom Agents** | 自然语言描述即创建（"每天早上 8 点扫描昨天 #meeting-notes 并朗读摘要"） |
| **工作流自动化** | AI 可在 Supertag 上构建和编辑工作流 |
| **内联 AI** | 编辑器原生支持音频/视频播放 + AI 处理 |

**评价**: Tana 的 AI 不是侧边栏插件，而是 Supertag 结构的原生扩展。AI 理解你的内容本体论（Person/Meeting/Book 等类型定义），因此自动填充和结构化质量最高。

### Obsidian — 最灵活的社区 AI 生态

| 能力 | 详情 |
|------|------|
| **Smart Connections** | 本地 Embedding + RAG，78 万+ 下载量。100% 本地嵌入，零 API Key |
| **Copilot** | Vault QA 模式。语义搜索 + LLM 问答。支持 Ollama/LM Studio |
| **Copilot Personal** | Agent 模式。17 个工具（搜索/读写/网络/PDF），多提供商，Pro $4.99/mo |
| **LLMSider** | 100+ 内置工具 + MCP。自主工具调用循环。开源 |
| **Lumina** | RAG + MCP + Agent，零配置本地索引，watch 模式实时同步 |
| **Companion** | 幽灵文本自动补全，Ollama 支持 |
| **Text Generator** | 模板驱动的 AI 生成，开源 |
| **Obsidian Skills** | 2026.5 Kepano 开源。AI Agent（Claude Code/Codex）学会 Obsidian 语法和结构 |
| **MCP** | Obsidian MCP 插件 Pro 用户首季 34% 采用率 |

**隐私方案**: Smart Connections（本地嵌入）+ Copilot（Ollama 本地模型）+ 排除敏感文件夹 = 100% 本地，零云端传输，严格 GDPR 合规。

**评价**: Obsidian 的 AI 策略是"不内置，但让社区做得最好"。用户可在 $0/mo（本地）到 ~$15/mo（Copilot Plus）之间自由选择。核心优势：无论用哪个 AI 方案，数据都是本地 Markdown 文件。

### Heptabase — 最专注学习的 AI Tutor

| 能力 | 详情 |
|------|------|
| **AI Tutor** | 2026.3.31 上线。结构化个性化教学系统。~20+ 次迭代至 v1.98（6 月） |
| **Research with Citations** | 从用户提供的来源研究主题，输出可信引用 |
| **Course Generation** | 自动构建课程大纲和内容，创建"课程白板"填充卡片和 artifacts |
| **Diff-based Editing** | AI 直接编辑卡片和日志，展示 diff 视图供确认 |
| **Tag Database Editing** | AI Agent 创建/修改属性、视图、筛选、分组 |
| **Goal Discovery** | AI 读取近期白板，发现用户思维中已经形成的学习方向 |
| **Context-aware** | 读取全白板上下文，理解多种内容类型 |
| **自建 Embedding 模型** | 隐私优先 embedding 模型本地运行，AI 建议关联卡片 |
| **Models** | GPT-5.4-mini, Claude Opus 4.6, Claude Sonnet 4.6, Gemini Pro 3.1 |
| **MCP** | Heptabase MCP 连接 ChatGPT/Claude |
| **定价** | Pro $8.99/mo（有限额度）, Premium $17.99/mo（无限），Premium+（重度 AI） |

**评价**: Heptabase 的 AI Tutor 不是"聊天机器人"，而是**教学系统**。它创建课程、编辑内容、发现学习方向——是 AI 在教育/研究领域最深度的应用。

### Capacities — 与对象模型对齐的 AI Assistant

| 能力 | 详情 |
|------|------|
| **AI Assistant** | 上下文感知聊天（理解 Typed Objects、反向链接、知识图谱） |
| **属性自动填充** | AI 自动填充对象属性（Pro 功能） |
| **图片分析/OCR** | 2026 逐步推出 |
| **MCP Chat Connectors** | Beta。ChatGPT/Claude/Cursor/Le Chat 可搜索/读取/写入 Capacities |
| **AI 2.0 计划** | 多模型提供商（含欧洲托管方案）、Agent 聊天、媒体理解（音视频转录） |
| **定价** | AI 仅限 Pro $9.99-11.99/mo |

**评价**: Capacities 的 AI 理念是"辅助知识工作，而非自动化"。哲学上与 Tana/Notion 的"AI Agent"方向形成鲜明对比。

### RemNote — 唯一 AI + SRS 深度融合

| 能力 | 详情 |
|------|------|
| **AI 闪卡生成** | PDF/笔记 → 自动生成闪卡，卡片链接回源材料 |
| **AI Tutor** | "Learn PDF" 模式，AI 引导阅读并提问 |
| **AI 答案评估** | 复习时 AI 评估你的输入，反馈正确性和遗漏 |
| **内联闪卡** | `==` 在任意 bullet 创建闪卡，AI 可选生成答案面 |
| **SRS** | SM-2 + FSRS-4.5，与 Anki 同等调度算法 |
| **定价** | Free（100 AI credits/mo）, Pro $8/mo, **Pro+AI $18/mo**（2 万 credits） |

**评价**: 如果学习/记忆是核心需求，RemNote 是唯一将 SRS 与 AI 在笔记环境中深度整合的工具。

### 其他值得关注

| 工具 | AI 能力 | 特点 |
|------|---------|------|
| **Reflect** | GPT-4o/Claude Sonnet 内联，自定义 AI Prompts | 最简洁的 AI 笔记 |
| **Mem.ai** | AI Thought Partner，自动浮现关联记忆 | AI 驱动的回忆 |
| **Craft** | Llama 3.2/GPT-4o/DeepSeek/自定义 API Key 多模型 | 最灵活的模型选择 |
| **Amplenote** | Ample Agent Pro (2026.4) | 任务优先级 AI |
| **Evernote v11** | AI Assistant (ChatGPT), Semantic Search, AI Meeting Notes | 免费层含 AI（意外） |
| **NotebookLM** | Source-grounded RAG, Audio Overview 播客 | 免费且质量高 |
| **Khoj** | 自托管 RAG 第二大脑, Docker, AGPL-3.0 | 开源 NotebookLM |
| **Open Notebook** | MIT 开源, 18+ AI 提供商, 100% 本地选项 | 真正私有的 NotebookLM |
| **SiYuan** | OpenAI API 集成, Tesseract OCR | 通过 API Key |
| **Logseq** | Ollama + API 插件, 图谱 + 反向链接上下文 | 社区驱动 |
| **Apple Notes** | iOS 26+ AI 转录/摘要；iOS 27 Siri AI 集成 | 平台内置 |

---

## AI 隐私分级

| 等级 | 描述 | 代表工具 |
|------|------|---------|
| 🟢 **零泄露** | 100% 本地，无网络传输 | Obsidian + Ollama, Open Notebook (本地) |
| 🟢 **最小泄露** | 文档和嵌入向量本地，仅检索片段上传 | Obsidian + Smart Connections + 云端 LLM, Khoj, LocalDocs |
| 🟡 **加密可控** | 上传但用户管理 API Key | Craft, SiYuan, Obsidian + BYOK 插件 |
| 🟠 **服务端处理** | 笔记内容上传服务端进行推理 | Capacities, Heptabase, RemNote, Reflect |
| 🔴 **全托管** | AI 拥有广泛访问权限，自动索引和分析 | Notion, Tana, Mem.ai, Evernote |

---

## AI 成本对比

| 路径 | 月成本 | 工具 |
|------|--------|------|
| **完全免费** | $0 | Obsidian + Smart Connections + Ollama, Logseq + Ollama, Open Notebook |
| **BYOK（轻量使用）** | ~$2-5 | Obsidian 插件 + 自己的 API Key, Craft (自带) |
| **BYOK（重度使用）** | ~$10-20 | Obsidian + GPT-4o/Claude API Key |
| **内置 AI（入门）** | $5-10/mo | Capacities Pro, Heptabase Pro (有限额), Amplenote Pro |
| **内置 AI（无限）** | $10-18/mo | Heptabase Premium, RemNote Pro+AI, Tana Pro |
| **企业 AI** | $20/seat/mo+ | Notion Business + Custom Agents, Notion Enterprise |

---

## 关键结论

1. **AI Agent 是新主战场**: Notion Custom Agents 和 Tana Custom Agents 代表了 AI 的最高集成度——不是侧边栏聊天，而是 24/7 自主执行任务的基础设施
2. **隐私是 AI 采纳的核心约束**: 零泄露方案（本地 LLM）和最小泄露方案（Hybrid RAG）正在成熟，为隐私敏感用户提供了可行路径
3. **MCP 正在标准化 AI-KB 集成**: Notion、Obsidian、Heptabase 均已支持 MCP，降低了 AI 与知识库之间的集成成本
4. **AI Tutor 是教育/研究的新范式**: Heptabase 和 RemNote 证明 AI 可以不只是回答问题，而是主动教学、创建课程、发现学习方向
5. **社区路线 vs 内置路线并存**: Obsidian 证明社区 AI 生态可以做得比内置方案更好，同时保留数据主权
6. **成本跨度极大**: 从 $0（本地 LLM）到 $20+/seat/mo（企业 AI），用户有前所未有的选择空间
