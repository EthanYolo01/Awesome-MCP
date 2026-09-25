<div align="center">

# 🔌 Awesome MCP 中文资源大合集

**精选 Model Context Protocol (MCP) 优质资源 —— 服务器、客户端、SDK、工具与学习资料**

*持续收集 · 人工验证 · 精选干货*

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-欢迎提交-brightgreen.svg?style=flat-square)](CONTRIBUTING.md)
[![License: CC0-1.0](https://img.shields.io/badge/许可证-CC0_1.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/publicdomain/zero/1.0/)
[![最近更新](https://img.shields.io/badge/最近更新-2026年3月-blue?style=flat-square)](https://github.com/EthanYolo01/Awesome-MCP/commits/main)

> **有观点的精选，不是无脑堆砌。**
> 每一条资源都经过人工审核和链接验证。我们告诉你每个资源*为什么*值得关注，以及*什么时候*该用它。

**MCP 现状（2026 年 3 月）：** GitHub 话题下 🗂️ 17,967 个相关仓库 &nbsp;·&nbsp; 🌐 1,200+ 已验证服务器 &nbsp;·&nbsp; 🔧 20+ 支持 MCP 的客户端 &nbsp;·&nbsp; 🏛️ Linux 基金会旗下开放协议

---

🌐 语言切换 / Language：**中文** | [English](README.md)

</div>

---

## 📋 目录

- [🏁 MCP 是什么？](#-mcp-是什么)
- [⏳ 发展历程](#-发展历程)
- [🏠 官方资源](#-官方资源)
- [🧠 核心概念速查](#-核心概念速查)
- [📦 官方 SDK](#-官方-sdk)
- [🖥️ MCP 客户端](#️-mcp-客户端)
- [🔧 MCP 服务器精选](#-mcp-服务器精选)
  - [🌐 浏览器与网页自动化](#-浏览器与网页自动化)
  - [📁 文件系统与存储](#-文件系统与存储)
  - [🗄️ 数据库](#️-数据库)
  - [💻 开发者工具与代码](#-开发者工具与代码)
  - [💬 通讯与协作](#-通讯与协作)
  - [☁️ 云服务与基础设施](#️-云服务与基础设施)
  - [🔍 搜索与信息检索](#-搜索与信息检索)
  - [🤖 AI 与机器学习](#-ai-与机器学习)
  - [📊 数据与分析](#-数据与分析)
  - [🏢 效率与生产力](#-效率与生产力)
  - [🔐 安全与合规](#-安全与合规)
  - [💰 金融与支付](#-金融与支付)
- [🛠️ 开发框架与构建工具](#️-开发框架与构建工具)
- [🔍 调试与测试工具](#-调试与测试工具)
- [🔒 MCP 安全专题](#-mcp-安全专题)
- [📖 教程、博客与文章](#-教程博客与文章)
- [🎥 视频与演讲](#-视频与演讲)
- [🗺️ 服务器目录与发现平台](#️-服务器目录与发现平台)
- [🗺️ 相关 Awesome 列表](#️-相关-awesome-列表)

---

## 🏁 MCP 是什么？

**Model Context Protocol（模型上下文协议，MCP）** 是一个开放标准协议，定义了 AI 应用（客户端）与外部数据源、工具（服务器）之间的通信方式。

**一句话理解：** MCP 是 AI 的「USB 接口」——不同的 AI 助手可以通过同一套标准协议，连接到数千个工具和数据源，无需为每个 AI 重复开发集成。

**三大核心原语（Primitives）：**

| 原语 | 说明 | 典型用途 |
|---|---|---|
| **Tools（工具）** | AI 可以调用的函数，能执行操作并返回结果 | 执行代码、写文件、发请求 |
| **Resources（资源）** | AI 可以读取的数据，类似文件或 API 响应 | 读取数据库、获取文件内容 |
| **Prompts（提示词模板）** | 可复用的提示词模板，由服务器提供 | 标准化任务指令、角色扮演模板 |

**架构关系：**
```
MCP 客户端（Claude Desktop / Cursor / VS Code）
        ↕  JSON-RPC 2.0（stdio / HTTP SSE / Streamable HTTP）
MCP 服务器（GitHub MCP / Playwright MCP / 你自己的服务器...）
        ↕
  外部系统（GitHub API / 浏览器 / 数据库 / 文件系统...）
```

**为什么重要：**
- **模型无关：** 同一个 MCP 服务器可同时服务 Claude、GPT、Gemini、本地模型
- **客户端无关：** 同一个 MCP 服务器支持 Claude Desktop、Cursor、VS Code、Cline 等所有客户端
- **安全隔离：** 服务器在独立进程中运行，精确控制 AI 的访问边界
- **生态规模：** GitHub 上已有 17,967 个相关仓库（Python 6,013 + TypeScript 5,132 为主）

---

## ⏳ 发展历程

```
2024年11月  ──  Anthropic 发布 MCP，随 Claude Desktop 同步推出
                首批官方参考服务器：filesystem、git、memory、fetch、time
                TypeScript SDK 和 Python SDK 首发

2025年初    ──  OpenAI 宣布采纳 MCP（ChatGPT Connectors 基于 MCP 构建）
                Google DeepMind 跟进，Gemini CLI 原生支持 MCP
                Cursor、Windsurf、VS Code（GitHub Copilot）相继集成

2025年中    ──  MCP 官方注册中心（Registry）上线
                Java、Kotlin（JetBrains）、C#（Microsoft）、Rust、Go 官方 SDK 相继发布
                GitHub topic `mcp` 下仓库突破 10,000 个

2025年12月  ──  MCP 协议捐献给 Linux 基金会旗下 Agentic AI Foundation
                成为厂商中立的开放标准，不再由 Anthropic 单独控制
                1,200+ 服务器在官方注册中心通过验证
                协议版本：2025-11-25（当前稳定版，日期格式版本号）

2026年初    ──  Streamable HTTP 传输方式取代旧版 HTTP+SSE，成为远程部署推荐方案
                官方 Go SDK 发布稳定版（与 Google 合作维护）
                17,967 个 GitHub 仓库与 MCP topic 相关
```

---

## 🏠 官方资源

| 资源 | 说明 |
|---|---|
| [modelcontextprotocol.io](https://modelcontextprotocol.io) | 官方文档网站 — 概念、教程、规范、SDK 指南 |
| [MCP 规范文档](https://modelcontextprotocol.io/specification/2025-11-25) | 完整协议规范（当前版本：2025-11-25） |
| [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | 官方参考服务器仓库 + 社区服务器索引 |
| [modelcontextprotocol/inspector](https://github.com/modelcontextprotocol/inspector) | 官方调试工具 — 可视化测试任意 MCP 服务器 |
| [MCP 官方注册中心](https://registry.modelcontextprotocol.io) | 官方发布的服务器注册与发现服务 |
| [MCP GitHub 组织](https://github.com/modelcontextprotocol) | 所有官方仓库（SDK、规范、参考服务器、工具） |
| [官方示例服务器（托管版）](https://example-server.modelcontextprotocol.io/mcp) | 在线可访问的演示服务器，用于测试客户端实现 |
| [MCP 社区论坛](https://github.com/orgs/modelcontextprotocol/discussions) | 官方讨论区，问题、RFC、架构设计 |

**官方参考服务器（教学用途，不建议直接用于生产）：**

| 服务器 | 功能说明 |
|---|---|
| [filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | 安全的文件读写，支持可配置的访问控制 |
| [git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) | 读取、搜索、操作 Git 仓库 |
| [memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) | 基于知识图谱的持久化记忆系统 |
| [fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) | 网页内容抓取，转换为 LLM 友好的格式 |
| [time](https://github.com/modelcontextprotocol/servers/tree/main/src/time) | 时间与时区转换 |
| [sequential-thinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) | 通过序列化思维链进行动态问题求解 |
| [everything](https://github.com/modelcontextprotocol/servers/tree/main/src/everything) | 包含全部 MCP 功能的综合参考/测试服务器 |

---

## 🧠 核心概念速查

### 传输方式（Transport）

| 传输方式 | 适用场景 | 说明 |
|---|---|---|
| **stdio** | 本地服务器 | 最简单，通过标准输入输出通信；Claude Desktop / Cursor 默认使用 |
| **Streamable HTTP** | 远程服务器 | 2025-11-25 规范新增，取代旧 HTTP+SSE，推荐远程部署方案 |
| **HTTP+SSE**（旧） | 远程服务器 | 旧版远程方案，兼容性保留，新项目建议用 Streamable HTTP |

### 配置文件格式

所有主流客户端使用同一种 JSON 配置格式，只是文件位置不同：

```json
{
  "mcpServers": {
    "github": {
      "command": "npx",
      "args": ["-y", "@modelcontextprotocol/server-github"],
      "env": {
        "GITHUB_PERSONAL_ACCESS_TOKEN": "your_token_here"
      }
    },
    "playwright": {
      "command": "npx",
      "args": ["@playwright/mcp@latest"]
    }
  }
}
```

**各客户端配置文件位置：**

| 客户端 | 配置文件路径 |
|---|---|
| Claude Desktop (macOS) | `~/Library/Application Support/Claude/claude_desktop_config.json` |
| Claude Desktop (Windows) | `%APPDATA%\Claude\claude_desktop_config.json` |
| Cursor | 项目根目录 `.cursor/mcp.json` 或全局 `~/.cursor/mcp.json` |
| Windsurf | 设置 → Cascade → Model Context Protocol Servers |
| VS Code | 工作区 `.vscode/mcp.json` 或用户设置 |
| Claude Code | `~/.claude.json` 中的 `mcpServers` 字段 |

---

## 📦 官方 SDK

官方 SDK 按功能完整度、协议支持和维护承诺分为三个等级。以下为 Tier 1（完整支持）：

| SDK | 语言 | GitHub | 维护方 | 备注 |
|---|---|---|---|---|
| **TypeScript SDK** | TypeScript / Node.js / Deno / Bun | [typescript-sdk](https://github.com/modelcontextprotocol/typescript-sdk) | Anthropic | 参考实现，功能最完整；支持 Express、Hono、Node.js HTTP 中间件 |
| **Python SDK** | Python | [python-sdk](https://github.com/modelcontextprotocol/python-sdk) | Anthropic | 功能完整；推荐搭配 FastMCP 简化开发 |
| **Kotlin SDK** | Kotlin Multiplatform (JVM/Native/JS/Wasm) | [kotlin-sdk](https://github.com/modelcontextprotocol/kotlin-sdk) | Anthropic × JetBrains | 支持协程原生 API，覆盖全平台目标 |
| **C# SDK** | .NET | [csharp-sdk](https://github.com/modelcontextprotocol/csharp-sdk) | Anthropic × Microsoft | .NET 生态首选 |
| **Rust SDK** | Rust | [rust-sdk](https://github.com/modelcontextprotocol/rust-sdk) | Anthropic | 包名 `rmcp`，完整实现最新规范 |
| **Go SDK** | Go | [go-sdk](https://github.com/modelcontextprotocol/go-sdk) | Anthropic × Google | 2025 年底稳定发布；底层使用 gopls 的 JSON-RPC 实现 |
| **Java SDK** | Java | [java-sdk](https://github.com/modelcontextprotocol/java-sdk) | Anthropic | Spring Boot / Spring AI 生态集成 |
| **PHP SDK** | PHP | [php-sdk](https://github.com/modelcontextprotocol/php-sdk) | Anthropic | PHP 生态支持 |

**社区 SDK（补充官方不足的场景）：**

| SDK | 语言 | GitHub | 特点 |
|---|---|---|---|
| [FastMCP](https://github.com/jlowin/fastmcp) | Python | [jlowin/fastmcp](https://github.com/jlowin/fastmcp) | 最简洁的 Python MCP 服务器构建方式；装饰器语法，极少样板代码 |
| [mcp-go](https://github.com/mark3labs/mcp-go) | Go | [mark3labs/mcp-go](https://github.com/mark3labs/mcp-go) | 官方 Go SDK 发布前最广泛使用的社区库，被 400+ 包依赖 |
| [mcp-framework](https://github.com/QuantGeekDev/mcp-framework) | TypeScript | [QuantGeekDev/mcp-framework](https://github.com/QuantGeekDev/mcp-framework) | 面向生产的 TypeScript MCP 服务器框架，带 CLI |

---

## 🖥️ MCP 客户端

MCP 的核心价值之一：**服务器配置一次，所有客户端通用**。

### 代码编辑器 / IDE

| 客户端 | 平台 | MCP 集成方式 | 说明 |
|---|---|---|---|
| [Claude Code](https://claude.ai/code) | macOS / Windows / Linux（终端） | 原生内置 | Anthropic 官方 CLI；SWE-bench Verified 80.8%；最完整的 MCP 支持 |
| [Cursor](https://cursor.sh) | macOS / Windows / Linux | 原生内置 | 最流行的 AI 代码编辑器；MCP 配置简单；支持 20+ 客户端安装 |
| [VS Code](https://code.visualstudio.com) | 全平台 | GitHub Copilot Agent Mode | VS Code 1.109+ 通过 Copilot Agent 模式原生支持 MCP |
| [Windsurf](https://codeium.com/windsurf) | macOS / Windows / Linux | 原生内置（Cascade） | Codeium 出品；$15/月起；VS Code fork |
| [Cline](https://github.com/cline/cline) | VS Code 插件 | 原生内置 | 开源、免费；支持任意 LLM；Human-in-the-loop 审批每个操作 |
| [Continue.dev](https://continue.dev) | VS Code / JetBrains | 原生内置 | 开源 AI 编码助手；支持本地和云端模型 |
| [Zed](https://zed.dev) | macOS / Linux | 实验性支持 | Rust 编写，极速；采用 ACP 协议（MCP 兼容） |

### 桌面对话客户端

| 客户端 | 平台 | 说明 |
|---|---|---|
| [Claude Desktop](https://claude.ai/download) | macOS / Windows | 官方桌面 App；最稳定的 MCP 客户端；免费版有使用限制 |
| [LibreChat](https://github.com/danny-avila/LibreChat) | 自托管（Docker） | 开源多模型对话客户端；支持多 MCP 服务器并发连接 |
| [Witsy](https://github.com/nbonamy/witsy) | macOS | 轻量 AI 助手；键盘快捷键召唤；MCP 支持 |
| [Enconvo](https://enconvo.com) | macOS | 150+ 内置工具 + MCP 支持；工作流自动化 |

### 命令行与自动化

| 客户端 | 说明 |
|---|---|
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | Google 官方 CLI；原生 MCP 支持；适合脚本和自动化工作流 |
| [Claude Code CLI](https://claude.ai/code) | Anthropic 官方 CLI；Agent Teams 支持多 Agent 协作 |
| [mcp-cli](https://github.com/chrishayuk/mcp-cli) | 轻量级 CLI，直接与任意 MCP 服务器交互；调试和开发必备 |

### 工作流与无代码平台

| 客户端 | 说明 |
|---|---|
| [n8n](https://n8n.io) | 开源工作流自动化平台；400+ 集成；完整 MCP 支持 |
| [MindPal](https://mindpal.io) | 无代码构建多 Agent 工作流；内置 MCP 服务器连接 |

---

## 🔧 MCP 服务器精选

> **标注说明：** 🔵 = 官方/企业官方提供 &nbsp; ⭐ = 社区高星推荐 &nbsp; 🔒 = 需要 API Key &nbsp; 🆓 = 完全免费/开源

### 🌐 浏览器与网页自动化

这是 MCP 生态最热门的分类，让 AI 真正获得「浏览网页」的能力。

| 服务器 | GitHub | 说明 |
|---|---|---|
| ⭐ **Playwright MCP** | [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) | **使用最广泛的 MCP 服务器**。全功能浏览器自动化——截图、点击、填表、提取数据。支持 20+ 客户端安装（Cursor、VS Code、Claude Desktop、Windsurf、Cline 等） |
| 🔵⭐ **Firecrawl MCP** | [mendableai/firecrawl-mcp-server](https://github.com/mendableai/firecrawl-mcp-server) | 将任意网页转换为 LLM 友好的干净 Markdown；去除广告、导航栏、杂乱标签。85,000+ GitHub Stars 的 Firecrawl 的 MCP 封装。有免费额度 |
| 🔵 **Browserbase MCP** | [browserbase/mcp-server-browserbase](https://github.com/browserbase/mcp-server-browserbase) | 云端无头浏览器操作（导航、数据抓取、表单填写）；企业级稳定性 |
| 🆓 **Chrome DevTools MCP** | [ChromeDevTools/chrome-devtools-mcp](https://github.com/ChromeDevTools/chrome-devtools-mcp) | 连接正在运行的 Chrome 实例，通过 DevTools Protocol 控制浏览器；Apache 2.0；完全免费 |
| 🔵 **BrightData MCP** | [brightdata/mcp-server](https://github.com/brightdata/mcp-server-brightdata) | 通过 BrightData 代理网络访问公网数据；反爬虫处理；企业级数据采集 |
| ⭐ **Fetch MCP** | [zcaceres/fetch-mcp](https://github.com/zcaceres/fetch-mcp) | 轻量级网页抓取，将 HTML 转换为 Markdown；无需浏览器；适合简单页面 |

### 📁 文件系统与存储

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **Filesystem MCP** | [modelcontextprotocol/servers/filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | 官方参考实现。安全的文件读写，支持可配置的目录访问控制。**必装基础服务器** |
| 🔵 **Box MCP** | [box/box-ai-agent-sdk](https://github.com/box/box-ai-agent-sdk) | 与 Box 企业内容管理平台交互；Box AI 加持 |
| 🔵 **AWS S3 MCP** | 见 AWS 官方文档 | 通过 Azure MCP Server 或独立服务器访问 S3 存储桶 |
| ⭐ **Obsidian MCP** | [cyanheads/obsidian-mcp-server](https://github.com/cyanheads/obsidian-mcp-server) | 直接读写 Obsidian Vault；知识库问答、笔记管理 |

### 🗄️ 数据库

| 服务器 | GitHub | 说明 |
|---|---|---|
| ⭐ **PostgreSQL MCP** | [crystaldba/postgres-mcp](https://github.com/crystaldba/postgres-mcp) | 只读 PostgreSQL 访问，自然语言查询数据；schema 探索 |
| 🔵 **MCP Toolbox for Databases** | [googleapis/genai-toolbox](https://github.com/googleapis/genai-toolbox) | Google 出品，支持 AlloyDB / BigQuery / Bigtable / Cloud SQL / MySQL / Neo4j / PostgreSQL / Spanner 等 10+ 数据库的统一 MCP 接口 |
| 🔵 **Cloudflare D1 MCP** | Cloudflare 官方 MCP 服务器 | 通过自然语言操作 Cloudflare D1 Serverless SQLite 数据库 |
| ⭐ **Chroma MCP** | [chroma-core/chroma-mcp](https://github.com/chroma-core/chroma-mcp) | 向量搜索、嵌入存储、全文检索；RAG 应用必备 |
| 🔵 **Memgraph MCP** | 官方提供 | 图数据库查询；知识图谱操作 |
| 🔵 **Couchbase MCP** | 官方提供 | 使用自然语言与 Couchbase 集群交互 |

### 💻 开发者工具与代码

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵⭐ **GitHub MCP** | [github/github-mcp-server](https://github.com/github/github-mcp-server) | GitHub 官方 MCP。仓库管理、Issues、PR 审查、代码搜索——全部通过对话操作 |
| 🔵 **Azure DevOps MCP** | [microsoft/azure-devops-mcp](https://github.com/microsoft/azure-devops-mcp) | 微软官方；完整的 Azure DevOps 操作（Pipeline、Repos、Boards、Artifacts） |
| 🔵 **Azure MCP** | [azure/azure-mcp](https://github.com/azure/azure-mcp) | 微软官方综合 Azure 服务 MCP：Azure Storage、Cosmos DB、App Service、Monitor 等 41 个工具 |
| 🔵 **Cloudflare MCP** | [cloudflare/mcp-server-cloudflare](https://github.com/cloudflare/mcp-server-cloudflare) | 部署和管理 Cloudflare Workers / KV / R2 / D1 / AI Gateway |
| 🔵 **Buildkite MCP** | 官方提供 | CI/CD 管道、构建数据、测试结果的 AI 操作接口 |
| 🔵 **JFrog MCP** | 官方提供 | JFrog 平台 API：制品库管理、构建追踪、发布生命周期管理 |
| ⭐ **Context7 MCP** | [upstash/context7](https://github.com/upstash/context7) | **开发者必备**。自动为任意库/框架抓取最新官方文档，注入 AI 上下文，彻底解决 AI 幻造 API 问题。支持 20+ 客户端，20M+ 月调用 |
| ⭐ **Git MCP** | [modelcontextprotocol/servers/git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) | 官方 Git 工具；读取历史、搜索提交、操作分支 |
| 🔵 **Sentry MCP** | [getsentry/sentry-mcp](https://github.com/getsentry/sentry-mcp) | 查询 Sentry 错误、分析 Stack Trace、创建 Issue——AI 辅助 Debug |
| ⭐ **PAIML MCP Agent Toolkit** | [paiml/mcp-agent-toolkit](https://github.com/paiml/mcp-agent-toolkit) | 零配置 AI 上下文生成；Rust/Deno/Python 项目脚手架；混合神经符号代码分析 |

### 💬 通讯与协作

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **Slack MCP** | [slack/slack-mcp-server](https://mcp.slack.com) | Slack 官方 MCP；消息发送、频道管理、搜索 Slack 工作区 |
| 🔵 **Gmail MCP** | [google/gmail-mcp](https://gmail.mcp.claude.com) | Google 官方 Gmail MCP；读写邮件、搜索、管理标签 |
| 🔵 **Google Calendar MCP** | [google/gcal-mcp](https://gcal.mcp.claude.com) | 日历管理、创建/更新/删除事件、检查空闲时间 |
| 🔵 **Microsoft 365 MCP** | [microsoft/mcp](https://github.com/microsoft/mcp) | 微软官方套件：邮件、日历、Teams、SharePoint、M365 Copilot 搜索 |
| 🔵 **Linear MCP** | Linear 官方提供 | 创建和管理 Linear Issues；工程团队项目追踪必备 |
| 🔵 **Notion MCP** | Notion 官方提供 | 读写 Notion 数据库和页面；知识库管理 |
| 🔵 **Atlassian MCP** | Atlassian 官方提供 | Jira Issues + Confluence 文档；企业研发流程管理 |
| 🔵 **Dart MCP** | 官方提供 | Dart（AI 原生项目管理工具）的任务、文档、项目操作 |

### ☁️ 云服务与基础设施

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **AWS MCP** | [awslabs/mcp](https://github.com/awslabs/mcp) | AWS 官方 MCP 服务器套件：EC2、S3、Lambda、DynamoDB、CloudWatch 等 |
| 🔵 **Azure MCP** | [azure/azure-mcp](https://github.com/azure/azure-mcp) | 见上方开发者工具部分 |
| 🔵 **Kubernetes MCP** | [metoro-io/metoro-mcp-server](https://github.com/metoro-io/metoro-mcp-server) | AI 操作 Kubernetes 集群；查询 Pod、Deployment、Service 状态 |
| 🔵 **Vercel MCP** | [vercel/mcp-adapter](https://github.com/vercel/mcp-adapter) | 部署应用到 Vercel；管理 Deployment、Environment Variables |
| 🔵 **Algolia MCP** | 官方提供 | AI Agent 管理和查询 Algolia 搜索索引 |
| 🔵 **EdgeOne Pages MCP** | Tencent 官方 | 将 HTML 内容部署到 EdgeOne Pages，获取公开访问 URL |

### 🔍 搜索与信息检索

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **Brave Search MCP** | [brave/brave-search-mcp-server](https://github.com/brave/brave-search-mcp-server) | Brave 官方 MCP；网页和本地搜索；隐私优先。有免费额度 |
| 🔵 **Kagi MCP** | [kagisearch/kagi-mcp](https://github.com/kagisearch/kagimcp) | Kagi 搜索 API；高质量、无广告结果 |
| 🔵 **Meilisearch MCP** | [meilisearch/meilisearch-mcp](https://github.com/meilisearch/meilisearch-mcp) | 与 Meilisearch 全文搜索+语义搜索引擎交互 |
| 🔵 **Tavily MCP** | Tavily 官方 | 专为 AI Agent 设计的搜索 API；结构化数据返回 |
| ⭐ **Perplexity MCP** | 社区构建 | 通过 Perplexity API 进行深度网络研究 |

### 🤖 AI 与机器学习

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **Microsoft Foundry MCP** | [microsoft/mcp](https://github.com/microsoft/mcp) | Azure AI Foundry 的模型、知识库、评估工具统一访问接口 |
| 🔵 **AgentOps MCP** | 官方提供 | AI Agent 的可观测性与追踪；调试 Agent 行为、查看执行链路 |
| 🔵 **RAGFlow MCP** | [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | 开源 RAG 引擎；结合 RAG 和 Agent 能力；自然语言查询文档知识库 |
| ⭐ **Memory MCP** | [JamesANZ/memory-mcp](https://github.com/JamesANZ/memory-mcp) | 基于知识图谱的跨对话持久化记忆 |
| 🔵 **Chroma MCP** | 见数据库部分 | 向量数据库 + 语义搜索 |

### 📊 数据与分析

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **BigQuery MCP** | Google 官方（通过 MCP Toolbox） | 自然语言查询 Google BigQuery 数据仓库 |
| 🔵 **Dash0 MCP** | 官方提供 | 查询 OpenTelemetry 资源、调查生产事故、分析 Metrics/Logs/Traces |
| 🔵 **Comet Opik MCP** | 官方提供 | 自然语言查询 LLM 日志、Trace、Prompt 和遥测数据 |
| 🔵 **Keboola MCP** | 官方提供 | 构建数据工作流、集成管道和分析 |
| 🔵 **Financial Datasets MCP** | 官方提供 | 面向 AI Agent 的股票市场数据 API |
| 🔵 **CoinGecko MCP** | 官方提供 | 200+ 区块链网络、800 万+ Token 的加密货币价格和市场数据 |

### 🏢 效率与生产力

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **API.market MCP Gateway** | [客户端元数据与文档](https://github.com/Noveum/api-market-agent-integrations) | 闭源托管 API 市场网关，端点为 https://api.market/api/mcp/gateway；提供五个工具，用于 API 发现、调用、用量查询和订阅管理；通过 Streamable HTTP 连接，支持 OAuth 或 API 密钥；免费额度和付费方案因 API 而异 |
| ⭐ **Composio MCP** | [composio/composio](https://github.com/composio/composio) | **一个 MCP 连接 1,000+ 工具**；Salesforce、HubSpot、Trello、Asana、Google Drive 等；托管认证管理。27,000+ GitHub Stars |
| 🔵 **PandaDoc MCP** | 官方提供 | AI 辅助文档创建、发送和管理；合同工作流自动化 |
| 🔵 **PayPal MCP** | 官方提供 | PayPal 官方；支付操作、订单管理 |
| 🔵 **Mercado Pago MCP** | 官方提供 | Mercado Pago 官方；拉美市场支付集成 |
| 🔵 **Adfin MCP** | 官方提供 | 统一支付平台：发票、对账、收款全流程 |
| ⭐ **n8n MCP** | [n8n-io/n8n](https://github.com/n8n-io/n8n-mcp) | 通过 AI 创建和管理 n8n 工作流；自动化与 AI 的完美结合 |
| 🔵 **Chargebee MCP** | 官方提供 | 订阅计费管理；SaaS 财务运营 |

### 🔐 安全与合规

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **BoostSecurity MCP** | 官方提供 | 防止 AI 编码 Agent 引入有漏洞的依赖、恶意软件或拼写劫持包 |
| 🔵 **BrowserStack MCP** | 官方提供 | 通过 AI 进行浏览器兼容性测试、可访问性检查、Debug |
| 🔵 **Cycode MCP** | 官方提供 | SAST、SCA、密钥扫描、IaC 安全检查；DevSecOps 全链路 |

### 💰 金融与支付

| 服务器 | GitHub | 说明 |
|---|---|---|
| 🔵 **Stripe MCP** | [stripe/agent-toolkit](https://github.com/stripe/agent-toolkit) | Stripe 官方；支付、订阅、发票、退款操作 |
| 🔵 **PayPal MCP** | 官方提供 | 见上方效率与生产力部分 |
| 🔵 **Alby Bitcoin MCP** | 官方提供 | 将闪电网络比特币钱包连接到 Agent；全球即时支付 |

---

## 🛠️ 开发框架与构建工具

### 快速构建 MCP 服务器的框架

| 框架 | 语言 | GitHub | 说明 |
|---|---|---|---|
| ⭐ **FastMCP** | Python | [jlowin/fastmcp](https://github.com/jlowin/fastmcp) | **最受推荐的 Python 框架**。装饰器语法，几行代码写出 MCP 服务器：`@mcp.tool()`, `@mcp.resource()`, `@mcp.prompt()` |
| ⭐ **MCP Framework** | TypeScript | [QuantGeekDev/mcp-framework](https://github.com/QuantGeekDev/mcp-framework) | TypeScript 生产框架；带 CLI 脚手架；约定优于配置 |
| **rust-mcp-sdk** | Rust | [rust-mcp-stack/rust-mcp-sdk](https://github.com/rust-mcp-stack/rust-mcp-sdk) | 高性能异步 Rust 工具包；完整实现最新规范（2025-11-25） |
| **mcp-go** | Go | [mark3labs/mcp-go](https://github.com/mark3labs/mcp-go) | 官方 Go SDK 发布前最广泛使用的社区 Go SDK，400+ 包依赖 |

### 跨语言工具

| 工具 | GitHub | 说明 |
|---|---|---|
| **AgentRPC** | [naptha/agentrpc](https://github.com/naptha/agentrpc) | 跨语言、跨网络边界连接任意函数到 MCP；支持多语言客户端调用 |
| **Composio** | [composio/composio](https://github.com/composio/composio) | 1,000+ 工具的托管认证和上下文管理；MCP + Agent 框架双支持 |

### 部署与网关

| 工具 | GitHub | 说明 |
|---|---|---|
| 🔵 **MCP Gateway** | 多家厂商提供 | 作为代理将多个 MCP 服务器暴露为统一端点；身份验证、速率限制 |
| **n8n MCP** | [n8n-io/n8n](https://n8n.io) | n8n 同时支持作为 MCP 客户端和服务器使用；可视化工作流即 MCP 工具 |

---

## 🔍 调试与测试工具

### 官方工具

| 工具 | 链接 | 说明 |
|---|---|---|
| 🔵⭐ **MCP Inspector** | [modelcontextprotocol/inspector](https://github.com/modelcontextprotocol/inspector) | **必装调试工具**。可视化 UI + 代理服务器，测试任意 MCP 服务器。支持 stdio / SSE / Streamable HTTP；内置 OAuth 流程测试；导出 Cursor/Claude Code 配置文件。`npx @modelcontextprotocol/inspector your-server` |
| **MCP Inspector Online** | [mcp.ziziyi.com/inspector](https://mcp.ziziyi.com/inspector) | 浏览器版 Inspector，无需安装，适合快速测试远程 MCP 服务器 |

**Inspector 快速使用：**
```bash
# 测试本地 Node.js MCP 服务器
npx @modelcontextprotocol/inspector node your-server.js

# 测试本地 Python MCP 服务器
npx @modelcontextprotocol/inspector python your-server.py

# 连接远程 SSE 服务器
npx @modelcontextprotocol/inspector --transport sse https://your-remote-server.com/sse

# Docker 运行（隔离环境）
docker run --rm -p 127.0.0.1:6274:6274 -p 127.0.0.1:6277:6277 \
  -e HOST=0.0.0.0 -e MCP_AUTO_OPEN_ENABLED=false \
  ghcr.io/modelcontextprotocol/inspector
```

> ⚠️ **安全警告：** 不要使用 `DANGEROUSLY_OMIT_AUTH` 标志，这会导致 RCE 风险（CVE-2025-49596）。Inspector 默认只绑定 localhost，请勿修改为公网绑定。

### 测试相关工具

| 工具 | 说明 |
|---|---|
| **mcp-cli** | [chrishayuk/mcp-cli](https://github.com/chrishayuk/mcp-cli) — 命令行直接与 MCP 服务器交互；细粒度探索 Tools/Resources/Prompts |
| **MCP Discovery** | Rust 编写的轻量级 CLI，用于发现和探索 MCP 服务器能力 |
| **Tester MCP Client（Apify）** | 轻量级开源 MCP 客户端，用于功能冒烟测试和快速完整性检查 |

---

## 🔒 MCP 安全专题

MCP 赋予 AI 广泛的工具调用能力，安全问题不容忽视。

### 核心威胁模型

| 威胁 | 说明 | 缓解措施 |
|---|---|---|
| **提示注入（Prompt Injection）** | 恶意内容通过工具返回值注入指令，改变 AI 行为 | 严格校验工具返回内容；使用 BoostSecurity / mcp-scan |
| **工具中毒（Tool Poisoning）** | 恶意 MCP 服务器在工具描述中嵌入隐藏指令 | 只使用可信来源的服务器；审查工具描述 |
| **跨服务器攻击** | 一台服务器的工具命名与另一台冲突，触发非预期行为 | 客户端使用完全限定工具名；服务器命名空间隔离 |
| **数据泄露** | 服务器读取超出必要范围的数据 | 最小权限原则；只给服务器访问所需目录/API Scope |
| **未认证访问** | 远程 MCP 服务器无认证即可访问 | 强制 OAuth 2.0 或 API Key；不暴露 stdio 服务器到网络 |

### 安全工具

| 工具 | GitHub | 说明 |
|---|---|---|
| **mcp-scan** | [invariantlabs-ai/mcp-scan](https://github.com/invariantlabs-ai/mcp-scan) | 开源 MCP 安全扫描工具；检测提示注入、工具中毒、可疑工具描述 |
| **Intercept** | [policylayer/intercept](https://github.com/policylayer/intercept) | 开源 MCP 工具调用控制层；通过 YAML 策略文件实现速率限制、消费上限、访问控制和参数限制；亚毫秒级评估；审计日志 |
| **BoostSecurity** | 官方提供 | 防止 AI 编码 Agent 引入有漏洞的 npm/pip 包；CI/CD 集成 |
| **Cycode** | 官方提供 | SAST + 密钥扫描 + IaC 安全；开发阶段即捕获安全问题 |

### 安全最佳实践

**服务器端：**
- 永远验证并清理工具参数；不要信任 AI 传入的未经验证的数据
- 实施最小权限：文件系统服务器只允许访问必要目录
- 在工具描述中清晰说明能力边界，避免歧义
- 远程服务器必须实现 OAuth 2.0 认证（MCP 2025-11-25 规范要求）
- 记录所有工具调用日志，便于审计

**客户端/用户端：**
- 只安装来自可信来源的 MCP 服务器
- 审查工具描述，特别注意异常长的描述（可能含隐藏指令）
- 使用 MCP Inspector 在连接生产系统前先检查服务器行为
- 不要在配置文件中硬编码 API Key，使用环境变量

**深度阅读：**
- [Semgrep 安全工程师 MCP 指南](https://semgrep.dev/blog/2025/a-security-engineers-guide-to-mcp/) — 最全面的 MCP 安全审计实践
- [MCP 安全架构概述](https://modelcontextprotocol.io/docs/concepts/security) — 官方安全文档

---

## 📖 教程、博客与文章

### 官方文档与入门

- [MCP 官方文档](https://modelcontextprotocol.io/docs) — 从架构概念到 SDK 使用的权威参考
- [MCP 快速上手](https://modelcontextprotocol.io/quickstart) — 30 分钟内构建你的第一个 MCP 服务器
- [MCP 架构概述](https://modelcontextprotocol.io/docs/concepts/architecture) — 深入理解 Client-Server 架构和三大原语
- [**microsoft/mcp-for-beginners**](https://github.com/microsoft/mcp-for-beginners) ⭐ — 微软出品的 MCP 入门课程；C# / Java / TypeScript / Python / Rust 多语言示例；对齐最新规范 2025-11-25

### 深度技术文章

- [2025 年 MCP 现状报告](https://github.com/punkpeye/awesome-mcp-servers) — punkpeye 维护，深度生态分析
- [10 个最佳开发者 MCP 服务器（2026）](https://www.firecrawl.dev/blog/best-mcp-servers-for-developers) — Firecrawl 出品，每个服务器含完整配置示例
- [Semgrep：安全工程师的 MCP 指南](https://semgrep.dev/blog/2025/a-security-engineers-guide-to-mcp/) — MCP 安全审计最权威的深度文章
- [MCP Inspector 深度解析](https://skywork.ai/skypage/en/A-Deep-Dive-into-the-MCP-Inspector) — Inspector 使用全指南，含 CVE-2025-49596 说明
- [GitHub Blog：9 个值得关注的 MCP 开源项目](https://github.blog/open-source/accelerate-developer-productivity-with-these-9-open-source-ai-and-mcp-projects/) — GitHub 官方选出的生态明星项目
- [官方 Go SDK 深度介绍](https://socket.dev/blog/official-go-sdk-for-mcp) — Go SDK 架构设计决策详解
- [Context7：彻底解决 AI 代码幻觉](https://dev.to/prithwish_nath/5-essential-mcp-servers-that-give-claude-cursor-real-superpowers-2025-nf6) — Context7 实战效果展示

### 学习路径

**初学者（了解 MCP 是什么）：**
1. [MCP 官方介绍视频](https://modelcontextprotocol.io) → [架构概述](https://modelcontextprotocol.io/docs/concepts/architecture)
2. 安装 [Claude Desktop](https://claude.ai/download) 或 [Cursor](https://cursor.sh)
3. 添加第一个 MCP 服务器（推荐从 Playwright 或 filesystem 开始）
4. 用 [MCP Inspector](https://github.com/modelcontextprotocol/inspector) 调试和验证

**开发者（构建自己的服务器）：**
1. Python 路线：官方 Python SDK + [FastMCP](https://github.com/jlowin/fastmcp)
2. TypeScript 路线：官方 TypeScript SDK + [MCP Framework](https://github.com/QuantGeekDev/mcp-framework)
3. 参考 [microsoft/mcp-for-beginners](https://github.com/microsoft/mcp-for-beginners) 多语言示例
4. 使用 [MCP Inspector](https://github.com/modelcontextprotocol/inspector) 测试和调试

---

## 🎥 视频与演讲

| 资源 | 类型 | 说明 |
|---|---|---|
| [MCP 官方介绍视频](https://modelcontextprotocol.io) | 官方 | 协议设计者介绍 MCP 的设计理念 |
| [Anthropic MCP 发布公告](https://www.anthropic.com/news/model-context-protocol) | 公告 | 2024 年 11 月 MCP 首次发布时的官方说明 |
| [GitHub Blog：MCP 生态加速视频](https://github.blog/open-source/accelerate-developer-productivity-with-these-9-open-source-ai-and-mcp-projects/) | 博客 + 视频 | GitHub 视角的 MCP 生态解读 |
| [Lex Fridman #491：OpenClaw（含 MCP 深度讨论）](https://www.youtube.com/watch?v=YFjfBk8HI5o) | 播客 | MCP 在 Agent 生态中的角色，结合 OpenClaw 实践 |

---

## 🗺️ 服务器目录与发现平台

在这些平台可以发现和搜索数千个 MCP 服务器：

| 平台 | 链接 | 说明 |
|---|---|---|
| 🔵 **MCP 官方注册中心** | [registry.modelcontextprotocol.io](https://registry.modelcontextprotocol.io) | 官方注册和发现服务；经过验证的服务器列表 |
| ⭐ **mcp.so** | [mcp.so](https://mcp.so) | 社区最大的 MCP 服务器目录；13,000+ 服务器；可搜索 |
| ⭐ **PulseMCP** | [pulsemcp.com](https://pulsemcp.com) | 服务器 + 客户端双目录；531+ 客户端；持续更新 |
| **mcp-awesome.com** | [mcp-awesome.com](https://mcp-awesome.com) | 1,200+ 经质量验证的 MCP 服务器；含安装教程 |
| **MCPIndex** | [mcpindex.net](https://mcpindex.net) | 多客户端安装配置对照；Cursor/Windsurf/Zed 配置一键生成 |
| **Glama MCP** | [glama.ai/mcp](https://glama.ai/mcp/clients) | Glama Chat（多模态 AI 客户端）维护的服务器和客户端目录 |

---

## 🗺️ 相关 Awesome 列表

| 列表 | 侧重 |
|---|---|
| [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | 最全面的英文 MCP 服务器合集（有配套网站 glama.ai/mcp） |
| [wong2/awesome-mcp-servers](https://github.com/wong2/awesome-mcp-servers) | 另一个高质量英文服务器合集 |
| [punkpeye/awesome-mcp-clients](https://github.com/punkpeye/awesome-mcp-clients) | 专注客户端的合集 |
| [cyanheads/model-context-protocol-resources](https://github.com/cyanheads/model-context-protocol-resources) | 实践导向的 MCP 学习资源，含 8 个手写服务器实现 |
| [microsoft/mcp-for-beginners](https://github.com/microsoft/mcp-for-beginners) | 微软出品，多语言入门课程 |
| [EthanYolo01/Awesome-OpenClaw](https://github.com/EthanYolo01/Awesome-OpenClaw) | OpenClaw AI Agent 框架资源合集（与本列表同系列） |

---

## 🤝 如何贡献

欢迎贡献！本列表追求**有效性验证 + 有观点的精选**，不是无脑堆砌。

**提交前请确认：**
1. 链接真实有效（亲自访问并确认）
2. 资源有明确说明（是什么、面向谁、为什么值得收录）
3. 没有重复条目（先搜索再提交）
4. 遵循现有章节的格式

**贡献方式：** 提交 Pull Request，或在 Issues 中报告失效链接。

**联系维护者：** kalayolo86@gmail.com

---

<div align="center">

**觉得有用？** 给个 ⭐ 并分享给你的团队。
**发现遗漏或死链？** [提 Issue](https://github.com/EthanYolo01/Awesome-MCP/issues) 或提交 PR。

*最后更新：2026 年 3 月 · 由社区用 ❤️ 维护*

🌐 语言切换 / Language：**中文** | [English](README.md)

</div>
