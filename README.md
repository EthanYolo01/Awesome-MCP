<div align="center">

# 🔌 Awesome MCP

**A carefully curated list of Model Context Protocol (MCP) resources — servers, clients, SDKs, tools and learning materials**

*Continuously collected · Manually verified · Opinionated curation*

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](CONTRIBUTING.md)
[![License: CC0-1.0](https://img.shields.io/badge/License-CC0_1.0-lightgrey.svg?style=flat-square)](https://creativecommons.org/publicdomain/zero/1.0/)
[![Last Updated](https://img.shields.io/badge/last%20updated-March%202026-blue?style=flat-square)](https://github.com/EthanYolo01/Awesome-MCP/commits/main)
[![Stars](https://img.shields.io/github/stars/EthanYolo01/Awesome-MCP?style=flat-square)](https://github.com/EthanYolo01/Awesome-MCP/stargazers)

> **Opinionated curation over exhaustive listing.**
> Every entry was reviewed and link-verified. We tell you *why* each resource matters and *when* to use it.

**MCP at a Glance (March 2026):** 🗂️ 17,967 GitHub repos &nbsp;·&nbsp; 🌐 1,200+ verified servers &nbsp;·&nbsp; 🔧 20+ MCP clients &nbsp;·&nbsp; 🏛️ Linux Foundation open standard

---

🌐 Language / 语言切换：**English** | [中文](README_CN.md)

</div>

---

## 📋 Table of Contents

- [🏁 What is MCP?](#-what-is-mcp)
- [⏳ Timeline](#-timeline)
- [🏠 Official Resources](#-official-resources)
- [🧠 Core Concepts Quick Reference](#-core-concepts-quick-reference)
- [📦 Official SDKs](#-official-sdks)
- [🖥️ MCP Clients](#️-mcp-clients)
- [🔧 Curated MCP Servers](#-curated-mcp-servers)
  - [🌐 Browser & Web Automation](#-browser--web-automation)
  - [📁 File System & Storage](#-file-system--storage)
  - [🗄️ Databases](#️-databases)
  - [💻 Developer Tools & Code](#-developer-tools--code)
  - [💬 Communication & Collaboration](#-communication--collaboration)
  - [☁️ Cloud & Infrastructure](#️-cloud--infrastructure)
  - [🔍 Search & Information Retrieval](#-search--information-retrieval)
  - [🤖 AI & Machine Learning](#-ai--machine-learning)
  - [📊 Data & Analytics](#-data--analytics)
  - [🏢 Productivity & Workflow](#-productivity--workflow)
  - [🔐 Security & Compliance](#-security--compliance)
  - [💰 Finance & Payments](#-finance--payments)
- [🛠️ Frameworks & Build Tools](#️-frameworks--build-tools)
- [🔍 Debugging & Testing Tools](#-debugging--testing-tools)
- [🔒 MCP Security](#-mcp-security)
- [📖 Tutorials, Blogs & Articles](#-tutorials-blogs--articles)
- [🎥 Videos & Talks](#-videos--talks)
- [🗺️ Server Directories & Discovery](#️-server-directories--discovery)
- [🗺️ Related Awesome Lists](#️-related-awesome-lists)

---

## 🏁 What is MCP?

**Model Context Protocol (MCP)** is an open standard that defines how AI applications (clients) communicate with external data sources and tools (servers).

**One-line summary:** MCP is the "USB port for AI" — different AI assistants can connect to thousands of tools and data sources through the same standard protocol, without rebuilding integrations for each AI.

**Three Core Primitives:**

| Primitive | Description | Typical Use |
|---|---|---|
| **Tools** | Functions the AI can call that perform actions and return results | Execute code, write files, make API calls |
| **Resources** | Data the AI can read, like files or API responses | Read databases, fetch file contents |
| **Prompts** | Reusable prompt templates provided by servers | Standardized task instructions, role templates |

**Architecture:**
```
MCP Client (Claude Desktop / Cursor / VS Code)
        ↕  JSON-RPC 2.0 (stdio / HTTP SSE / Streamable HTTP)
MCP Server (GitHub MCP / Playwright MCP / your own server...)
        ↕
External System (GitHub API / Browser / Database / Filesystem...)
```

**Why it matters:**
- **Model-agnostic:** The same MCP server works with Claude, GPT, Gemini, and local models
- **Client-agnostic:** The same server supports Claude Desktop, Cursor, VS Code, Cline and more
- **Secure isolation:** Servers run in separate processes with explicit access boundaries
- **Ecosystem scale:** 17,967 GitHub repos related to MCP (Python 6,013 + TypeScript 5,132 leading)

---

## ⏳ Timeline

```
Nov 2024   ──  Anthropic releases MCP alongside Claude Desktop
               First official reference servers: filesystem, git, memory, fetch, time
               TypeScript SDK and Python SDK launch simultaneously

Early 2025 ──  OpenAI adopts MCP (ChatGPT Connectors built on MCP)
               Google DeepMind follows; Gemini CLI adds native MCP support
               Cursor, Windsurf, VS Code (GitHub Copilot) all integrate MCP

Mid 2025   ──  Official MCP Registry launches
               Java, Kotlin (JetBrains), C# (Microsoft), Rust, Go official SDKs ship
               GitHub topic `mcp` surpasses 10,000 repositories

Dec 2025   ──  MCP donated to Linux Foundation / Agentic AI Foundation
               Becomes vendor-neutral open standard, no longer Anthropic-controlled
               1,200+ servers verified in official registry
               Protocol version: 2025-11-25 (current stable, date-versioned)

Early 2026 ──  Streamable HTTP transport replaces legacy HTTP+SSE as recommended remote transport
               Official Go SDK reaches stable release (co-maintained with Google)
               17,967 GitHub repositories tagged with the MCP topic
```

---

## 🏠 Official Resources

| Resource | Description |
|---|---|
| [modelcontextprotocol.io](https://modelcontextprotocol.io) | Official documentation site — concepts, tutorials, spec, SDK guides |
| [MCP Specification](https://modelcontextprotocol.io/specification/2025-11-25) | Full protocol specification (current version: 2025-11-25) |
| [modelcontextprotocol/servers](https://github.com/modelcontextprotocol/servers) | Official reference servers + community server index |
| [modelcontextprotocol/inspector](https://github.com/modelcontextprotocol/inspector) | Official debugging tool — visually test any MCP server |
| [MCP Official Registry](https://registry.modelcontextprotocol.io) | Official server registration and discovery service |
| [MCP GitHub Org](https://github.com/modelcontextprotocol) | All official repos (SDKs, spec, reference servers, tools) |
| [Official Example Server (hosted)](https://example-server.modelcontextprotocol.io/mcp) | Online demo server for testing client implementations |
| [MCP Community Forum](https://github.com/orgs/modelcontextprotocol/discussions) | Official discussions: questions, RFCs, architecture design |

**Official Reference Servers (educational use — not recommended for direct production use):**

| Server | Description |
|---|---|
| [filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | Secure file read/write with configurable access controls |
| [git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) | Read, search, and manipulate Git repositories |
| [memory](https://github.com/modelcontextprotocol/servers/tree/main/src/memory) | Knowledge graph-based persistent memory system |
| [fetch](https://github.com/modelcontextprotocol/servers/tree/main/src/fetch) | Web content fetching, converted to LLM-friendly format |
| [time](https://github.com/modelcontextprotocol/servers/tree/main/src/time) | Time and timezone conversion |
| [sequential-thinking](https://github.com/modelcontextprotocol/servers/tree/main/src/sequentialthinking) | Dynamic problem-solving through sequential thought chains |
| [everything](https://github.com/modelcontextprotocol/servers/tree/main/src/everything) | Comprehensive reference/test server covering all MCP capabilities |

---

## 🧠 Core Concepts Quick Reference

### Transport Types

| Transport | Best For | Notes |
|---|---|---|
| **stdio** | Local servers | Simplest; communicates via stdin/stdout; default for Claude Desktop and Cursor |
| **Streamable HTTP** | Remote servers | Added in spec 2025-11-25; replaces legacy HTTP+SSE; recommended for remote deployments |
| **HTTP+SSE** (legacy) | Remote servers | Legacy remote transport; kept for compatibility; new projects should use Streamable HTTP |

### Configuration Format

All major clients use the same JSON configuration format — only the file location differs:

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

**Config file locations by client:**

| Client | Config File Path |
|---|---|
| Claude Desktop (macOS) | `~/Library/Application Support/Claude/claude_desktop_config.json` |
| Claude Desktop (Windows) | `%APPDATA%\Claude\claude_desktop_config.json` |
| Cursor | Project-level `.cursor/mcp.json` or global `~/.cursor/mcp.json` |
| Windsurf | Settings → Cascade → Model Context Protocol Servers |
| VS Code | Workspace `.vscode/mcp.json` or user settings |
| Claude Code | `mcpServers` field in `~/.claude.json` |

---

## 📦 Official SDKs

Official SDKs are ranked by completeness, spec compliance, and maintenance commitment. Below are Tier 1 (full support):

| SDK | Language | GitHub | Maintainer | Notes |
|---|---|---|---|---|
| **TypeScript SDK** | TypeScript / Node.js / Deno / Bun | [typescript-sdk](https://github.com/modelcontextprotocol/typescript-sdk) | Anthropic | Reference implementation, most complete; supports Express, Hono, Node.js HTTP middleware |
| **Python SDK** | Python | [python-sdk](https://github.com/modelcontextprotocol/python-sdk) | Anthropic | Fully featured; pair with FastMCP to simplify development |
| **Kotlin SDK** | Kotlin Multiplatform (JVM/Native/JS/Wasm) | [kotlin-sdk](https://github.com/modelcontextprotocol/kotlin-sdk) | Anthropic × JetBrains | Coroutine-native API; all platform targets |
| **C# SDK** | .NET | [csharp-sdk](https://github.com/modelcontextprotocol/csharp-sdk) | Anthropic × Microsoft | First choice for .NET ecosystem |
| **Rust SDK** | Rust | [rust-sdk](https://github.com/modelcontextprotocol/rust-sdk) | Anthropic | Package name `rmcp`; full implementation of latest spec |
| **Go SDK** | Go | [go-sdk](https://github.com/modelcontextprotocol/go-sdk) | Anthropic × Google | Stable release late 2025; uses gopls JSON-RPC under the hood |
| **Java SDK** | Java | [java-sdk](https://github.com/modelcontextprotocol/java-sdk) | Anthropic | Spring Boot / Spring AI ecosystem integration |
| **PHP SDK** | PHP | [php-sdk](https://github.com/modelcontextprotocol/php-sdk) | Anthropic | PHP ecosystem support |

**Community SDKs (filling gaps official SDKs don't cover):**

| SDK | Language | GitHub | Why use it |
|---|---|---|---|
| [FastMCP](https://github.com/jlowin/fastmcp) | Python | [jlowin/fastmcp](https://github.com/jlowin/fastmcp) | Simplest Python MCP server builder; decorator syntax, minimal boilerplate |
| [mcp-go](https://github.com/mark3labs/mcp-go) | Go | [mark3labs/mcp-go](https://github.com/mark3labs/mcp-go) | Most-used Go community library before the official SDK; depended on by 400+ packages |
| [mcp-framework](https://github.com/QuantGeekDev/mcp-framework) | TypeScript | [QuantGeekDev/mcp-framework](https://github.com/QuantGeekDev/mcp-framework) | Production-grade TypeScript MCP server framework with CLI scaffolding |

---

## 🖥️ MCP Clients

One of MCP's core values: **configure a server once, use it across all clients.**

### Code Editors / IDEs

| Client | Platform | MCP Integration | Notes |
|---|---|---|---|
| [Claude Code](https://claude.ai/code) | macOS / Windows / Linux (terminal) | Native built-in | Anthropic official CLI; SWE-bench Verified 80.8%; most complete MCP support |
| [Cursor](https://cursor.sh) | macOS / Windows / Linux | Native built-in | Most popular AI code editor; simple MCP config; 20+ client install guide |
| [VS Code](https://code.visualstudio.com) | All platforms | GitHub Copilot Agent Mode | VS Code 1.109+ natively supports MCP via Copilot Agent mode |
| [Windsurf](https://codeium.com/windsurf) | macOS / Windows / Linux | Native (Cascade) | By Codeium; from $15/month; VS Code fork |
| [Cline](https://github.com/cline/cline) | VS Code extension | Native built-in | Open source, free; any LLM; human-in-the-loop approval per action |
| [Continue.dev](https://continue.dev) | VS Code / JetBrains | Native built-in | Open source AI coding assistant; local and cloud model support |
| [Zed](https://zed.dev) | macOS / Linux | Experimental | Rust-built, ultra-fast; uses ACP protocol (MCP-compatible) |

### Desktop Chat Clients

| Client | Platform | Notes |
|---|---|---|
| [Claude Desktop](https://claude.ai/download) | macOS / Windows | Official desktop app; most stable MCP client; free tier has usage limits |
| [LibreChat](https://github.com/danny-avila/LibreChat) | Self-hosted (Docker) | Open source multi-model chat client; supports multiple concurrent MCP server connections |
| [Witsy](https://github.com/nbonamy/witsy) | macOS | Lightweight AI assistant; keyboard shortcut activation; MCP support |
| [Enconvo](https://enconvo.com) | macOS | 150+ built-in tools + MCP support; workflow automation |

### Command Line & Automation

| Client | Notes |
|---|---|
| [Gemini CLI](https://github.com/google-gemini/gemini-cli) | Google official CLI; native MCP support; ideal for scripting and automation workflows |
| [Claude Code CLI](https://claude.ai/code) | Anthropic official CLI; Agent Teams supports multi-agent collaboration |
| [mcp-cli](https://github.com/chrishayuk/mcp-cli) | Lightweight CLI for direct interaction with any MCP server; essential for debugging and development |

### Workflow & No-Code Platforms

| Client | Notes |
|---|---|
| [n8n](https://n8n.io) | Open source workflow automation; 400+ integrations; full MCP support |
| [MindPal](https://mindpal.io) | No-code multi-agent workflow builder; built-in MCP server connections |

---

## 🔧 Curated MCP Servers

> **Key:** 🔵 = Official / enterprise-official &nbsp; ⭐ = Community top pick &nbsp; 🔒 = Requires API key &nbsp; 🆓 = Free / open source

### 🌐 Browser & Web Automation

The hottest MCP category — giving AI the real ability to browse the web.

| Server | GitHub | Description |
|---|---|---|
| ⭐ **Playwright MCP** | [microsoft/playwright-mcp](https://github.com/microsoft/playwright-mcp) | **Most widely used MCP server.** Full browser automation — screenshots, clicks, form filling, data extraction. Supports 20+ client install guides (Cursor, VS Code, Claude Desktop, Windsurf, Cline and more) |
| 🔵⭐ **Firecrawl MCP** | [mendableai/firecrawl-mcp-server](https://github.com/mendableai/firecrawl-mcp-server) | Converts any webpage to clean LLM-friendly Markdown; strips ads, nav bars, clutter. MCP wrapper for Firecrawl (85,000+ GitHub Stars). Has a free tier |
| 🔵 **Browserbase MCP** | [browserbase/mcp-server-browserbase](https://github.com/browserbase/mcp-server-browserbase) | Cloud-based headless browser operations (navigation, scraping, form submission); enterprise-grade reliability |
| 🆓 **Chrome DevTools MCP** | [ChromeDevTools/chrome-devtools-mcp](https://github.com/ChromeDevTools/chrome-devtools-mcp) | Connects to a running Chrome instance, controls it via DevTools Protocol; Apache 2.0; completely free |
| 🔵 **BrightData MCP** | [brightdata/mcp-server-brightdata](https://github.com/brightdata/mcp-server-brightdata) | Access public web data via BrightData proxy network; anti-bot handling; enterprise-grade data collection |
| ⭐ **Fetch MCP** | [zcaceres/fetch-mcp](https://github.com/zcaceres/fetch-mcp) | Lightweight web scraping that converts HTML to Markdown; no browser required; ideal for simple pages |

### 📁 File System & Storage

| Server | GitHub | Description |
|---|---|---|
| 🔵 **Filesystem MCP** | [modelcontextprotocol/servers/filesystem](https://github.com/modelcontextprotocol/servers/tree/main/src/filesystem) | Official reference implementation. Secure file read/write with configurable directory access controls. **Essential baseline server** |
| 🔵 **Box MCP** | [box/box-ai-agent-sdk](https://github.com/box/box-ai-agent-sdk) | Interact with Box enterprise content management; Box AI powered |
| ⭐ **Obsidian MCP** | [cyanheads/obsidian-mcp-server](https://github.com/cyanheads/obsidian-mcp-server) | Direct read/write to Obsidian vaults; knowledge base Q&A, note management |

### 🗄️ Databases

| Server | GitHub | Description |
|---|---|---|
| ⭐ **PostgreSQL MCP** | [crystaldba/postgres-mcp](https://github.com/crystaldba/postgres-mcp) | Read-only PostgreSQL access; natural language queries; schema exploration |
| 🔵 **MCP Toolbox for Databases** | [googleapis/genai-toolbox](https://github.com/googleapis/genai-toolbox) | Google-built; unified MCP interface for 10+ databases: AlloyDB / BigQuery / Bigtable / Cloud SQL / MySQL / Neo4j / PostgreSQL / Spanner and more |
| 🔵 **Cloudflare D1 MCP** | Cloudflare official | Natural language operations on Cloudflare D1 serverless SQLite databases |
| ⭐ **Chroma MCP** | [chroma-core/chroma-mcp](https://github.com/chroma-core/chroma-mcp) | Vector search, embedding storage, full-text retrieval; essential for RAG applications |
| 🔵 **Memgraph MCP** | Official | Graph database queries; knowledge graph operations |
| 🔵 **Couchbase MCP** | Official | Natural language interaction with Couchbase clusters |

### 💻 Developer Tools & Code

| Server | GitHub | Description |
|---|---|---|
| 🔵⭐ **GitHub MCP** | [github/github-mcp-server](https://github.com/github/github-mcp-server) | GitHub official MCP. Repo management, Issues, PR reviews, code search — all via conversation |
| 🔵 **Azure DevOps MCP** | [microsoft/azure-devops-mcp](https://github.com/microsoft/azure-devops-mcp) | Microsoft official; full Azure DevOps operations (Pipelines, Repos, Boards, Artifacts) |
| 🔵 **Azure MCP** | [azure/azure-mcp](https://github.com/azure/azure-mcp) | Microsoft official comprehensive Azure MCP: Storage, Cosmos DB, App Service, Monitor and 41+ tools |
| 🔵 **Cloudflare MCP** | [cloudflare/mcp-server-cloudflare](https://github.com/cloudflare/mcp-server-cloudflare) | Deploy and manage Cloudflare Workers / KV / R2 / D1 / AI Gateway |
| 🔵 **Buildkite MCP** | Official | AI interface for CI/CD pipelines, build data, and test results |
| 🔵 **JFrog MCP** | Official | JFrog Platform API: artifact management, build tracing, release lifecycle |
| ⭐ **Context7 MCP** | [upstash/context7](https://github.com/upstash/context7) | **Developer essential.** Automatically fetches the latest official docs for any library/framework and injects them into AI context — permanently solves AI hallucinating APIs. Supports 20+ clients, 20M+ monthly calls |
| ⭐ **Git MCP** | [modelcontextprotocol/servers/git](https://github.com/modelcontextprotocol/servers/tree/main/src/git) | Official Git tools; read history, search commits, manage branches |
| 🔵 **Sentry MCP** | [getsentry/sentry-mcp](https://github.com/getsentry/sentry-mcp) | Query Sentry errors, analyze stack traces, create issues — AI-assisted debugging |
| ⭐ **PAIML MCP Agent Toolkit** | [paiml/mcp-agent-toolkit](https://github.com/paiml/mcp-agent-toolkit) | Zero-config AI context generation; Rust/Deno/Python scaffolding; hybrid neuro-symbolic code analysis |

### 💬 Communication & Collaboration

| Server | GitHub | Description |
|---|---|---|
| 🔵 **Slack MCP** | [mcp.slack.com](https://mcp.slack.com) | Slack official MCP; send messages, manage channels, search workspace |
| 🔵 **Gmail MCP** | [gmail.mcp.claude.com](https://gmail.mcp.claude.com) | Google official Gmail MCP; read/write emails, search, manage labels |
| 🔵 **Google Calendar MCP** | [gcal.mcp.claude.com](https://gcal.mcp.claude.com) | Calendar management; create/update/delete events; check availability |
| 🔵 **Microsoft 365 MCP** | [microsoft/mcp](https://github.com/microsoft/mcp) | Microsoft official suite: email, calendar, Teams, SharePoint, M365 Copilot search |
| 🔵 **Linear MCP** | Linear official | Create and manage Linear issues; essential for engineering team project tracking |
| 🔵 **Notion MCP** | Notion official | Read/write Notion databases and pages; knowledge base management |
| 🔵 **Atlassian MCP** | Atlassian official | Jira Issues + Confluence docs; enterprise engineering workflow management |
| 🔵 **Dart MCP** | Official | Task, document, and project operations for Dart (AI-native project management tool) |

### ☁️ Cloud & Infrastructure

| Server | GitHub | Description |
|---|---|---|
| 🔵 **AWS MCP** | [awslabs/mcp](https://github.com/awslabs/mcp) | AWS official MCP server suite: EC2, S3, Lambda, DynamoDB, CloudWatch and more |
| 🔵 **Azure MCP** | [azure/azure-mcp](https://github.com/azure/azure-mcp) | See Developer Tools section above |
| 🔵 **Kubernetes MCP** | [metoro-io/metoro-mcp-server](https://github.com/metoro-io/metoro-mcp-server) | AI-driven Kubernetes cluster operations; query Pod, Deployment, Service status |
| 🔵 **Vercel MCP** | [vercel/mcp-adapter](https://github.com/vercel/mcp-adapter) | Deploy to Vercel; manage Deployments, Environment Variables |
| 🔵 **Algolia MCP** | Official | AI agent management and querying of Algolia search indexes |
| 🔵 **EdgeOne Pages MCP** | Tencent official | Deploy HTML content to EdgeOne Pages and get a publicly accessible URL |

### 🔍 Search & Information Retrieval

| Server | GitHub | Description |
|---|---|---|
| 🔵 **Brave Search MCP** | [brave/brave-search-mcp-server](https://github.com/brave/brave-search-mcp-server) | Brave official MCP; web and local search; privacy-first. Has a free tier |
| 🔵 **Kagi MCP** | [kagisearch/kagimcp](https://github.com/kagisearch/kagimcp) | Kagi Search API; high-quality, ad-free results |
| 🔵 **Meilisearch MCP** | [meilisearch/meilisearch-mcp](https://github.com/meilisearch/meilisearch-mcp) | Interact with Meilisearch full-text + semantic search engine |
| 🔵 **Tavily MCP** | Tavily official | Search API designed specifically for AI agents; structured data responses |
| ⭐ **Perplexity MCP** | Community-built | Deep web research via Perplexity API |

### 🤖 AI & Machine Learning

| Server | GitHub | Description |
|---|---|---|
| 🔵 **Microsoft Foundry MCP** | [microsoft/mcp](https://github.com/microsoft/mcp) | Unified access to Azure AI Foundry models, knowledge bases, and evaluation tools |
| 🔵 **AgentOps MCP** | Official | AI agent observability and tracing; debug agent behavior, view execution chains |
| 🔵 **RAGFlow MCP** | [infiniflow/ragflow](https://github.com/infiniflow/ragflow) | Open source RAG engine; combines RAG and agent capabilities; natural language document knowledge base queries |
| ⭐ **Memory MCP** | [JamesANZ/memory-mcp](https://github.com/JamesANZ/memory-mcp) | Knowledge graph-based persistent memory across conversations |

### 📊 Data & Analytics

| Server | GitHub | Description |
|---|---|---|
| 🔵 **BigQuery MCP** | Google official (via MCP Toolbox) | Natural language queries against Google BigQuery data warehouse |
| 🔵 **Dash0 MCP** | Official | Query OpenTelemetry resources, investigate production incidents, analyze Metrics/Logs/Traces |
| 🔵 **Comet Opik MCP** | Official | Natural language queries over LLM logs, traces, prompts and telemetry data |
| 🔵 **Keboola MCP** | Official | Build data workflows, integration pipelines, and analytics |
| 🔵 **Financial Datasets MCP** | Official | Stock market data API designed for AI agents |
| 🔵 **CoinGecko MCP** | Official | Crypto price and market data across 200+ blockchains and 8M+ tokens |

### 🏢 Productivity & Workflow

| Server | GitHub | Description |
|---|---|---|
| ⭐ **Composio MCP** | [composio/composio](https://github.com/composio/composio) | **One MCP connecting 1,000+ tools.** Salesforce, HubSpot, Trello, Asana, Google Drive and more; managed auth. 27,000+ GitHub Stars |
| 🔵 **PandaDoc MCP** | Official | AI-assisted document creation, sending, and management; contract workflow automation |
| 🔵 **PayPal MCP** | Official | PayPal official; payment operations, order management |
| 🔵 **Mercado Pago MCP** | Official | Mercado Pago official; payment integrations for Latin American markets |
| 🔵 **Adfin MCP** | Official | Unified payment platform: invoices, reconciliation, collections end-to-end |
| ⭐ **n8n MCP** | [n8n-io/n8n](https://n8n.io) | Create and manage n8n workflows via AI; perfect fusion of automation and AI |
| 🔵 **Chargebee MCP** | Official | Subscription billing management; SaaS financial operations |

### 🔐 Security & Compliance

| Server | GitHub | Description |
|---|---|---|
| 🔵 **BoostSecurity MCP** | Official | Prevents AI coding agents from introducing vulnerable dependencies, malware, or typosquatted packages |
| 🔵 **BrowserStack MCP** | Official | AI-driven browser compatibility testing, accessibility checks, debugging |
| 🔵 **Cycode MCP** | Official | SAST, SCA, secret scanning, IaC security checks; full DevSecOps coverage |

### 💰 Finance & Payments

| Server | GitHub | Description |
|---|---|---|
| 🔵 **Stripe MCP** | [stripe/agent-toolkit](https://github.com/stripe/agent-toolkit) | Stripe official; payments, subscriptions, invoices, refunds |
| 🔵 **Alby Bitcoin MCP** | Official | Connect Lightning Network Bitcoin wallet to agents; instant global payments |
| 🟢 **TWZRD Agent Intel** | [intel.twzrd.xyz](https://intel.twzrd.xyz) | Solana on-chain trust scoring for AI agents. Verify wallet reputation before x402 micropayments |

---

## 🛠️ Frameworks & Build Tools

### Frameworks for Building MCP Servers Quickly

| Framework | Language | GitHub | Description |
|---|---|---|---|
| ⭐ **FastMCP** | Python | [jlowin/fastmcp](https://github.com/jlowin/fastmcp) | **Most recommended Python framework.** Decorator syntax; write an MCP server in a few lines: `@mcp.tool()`, `@mcp.resource()`, `@mcp.prompt()` |
| ⭐ **MCP Framework** | TypeScript | [QuantGeekDev/mcp-framework](https://github.com/QuantGeekDev/mcp-framework) | TypeScript production framework; CLI scaffolding; convention over configuration |
| **rust-mcp-sdk** | Rust | [rust-mcp-stack/rust-mcp-sdk](https://github.com/rust-mcp-stack/rust-mcp-sdk) | High-performance async Rust toolkit; full implementation of the latest spec (2025-11-25) |
| **mcp-go** | Go | [mark3labs/mcp-go](https://github.com/mark3labs/mcp-go) | Most widely used community Go SDK before the official one shipped; 400+ dependents |

### Cross-Language Tools

| Tool | GitHub | Description |
|---|---|---|
| **AgentRPC** | [naptha/agentrpc](https://github.com/naptha/agentrpc) | Connect any function to MCP across languages and network boundaries; multi-language client support |
| **Composio** | [composio/composio](https://github.com/composio/composio) | Managed auth and context for 1,000+ tools; dual support for MCP and Agent frameworks |

### Deployment & Gateway

| Tool | Description |
|---|---|
| **MCP Gateway** | Proxy that exposes multiple MCP servers as a unified endpoint; authentication, rate limiting |
| **n8n MCP** | n8n works as both MCP client and server; visual workflows become MCP tools |

---

## 🔍 Debugging & Testing Tools

### Official Tools

| Tool | Link | Description |
|---|---|---|
| 🔵⭐ **MCP Inspector** | [modelcontextprotocol/inspector](https://github.com/modelcontextprotocol/inspector) | **Must-install debugging tool.** Visual UI + proxy server for testing any MCP server. Supports stdio / SSE / Streamable HTTP; built-in OAuth flow testing; exports Cursor/Claude Code config files. `npx @modelcontextprotocol/inspector your-server` |
| **MCP Inspector Online** | [mcp.ziziyi.com/inspector](https://mcp.ziziyi.com/inspector) | Browser-based Inspector; no install needed; great for quickly testing remote MCP servers |

**Inspector quick usage:**
```bash
# Test a local Node.js MCP server
npx @modelcontextprotocol/inspector node your-server.js

# Test a local Python MCP server
npx @modelcontextprotocol/inspector python your-server.py

# Connect to a remote SSE server
npx @modelcontextprotocol/inspector --transport sse https://your-remote-server.com/sse

# Docker (isolated environment)
docker run --rm -p 127.0.0.1:6274:6274 -p 127.0.0.1:6277:6277 \
  -e HOST=0.0.0.0 -e MCP_AUTO_OPEN_ENABLED=false \
  ghcr.io/modelcontextprotocol/inspector
```

> ⚠️ **Security warning:** Never use the `DANGEROUSLY_OMIT_AUTH` flag — this enables RCE risk (CVE-2025-49596). Inspector binds to localhost only by default; do not change this to a public interface.

### Testing Tools

| Tool | Description |
|---|---|
| **mcp-cli** | [chrishayuk/mcp-cli](https://github.com/chrishayuk/mcp-cli) — CLI for direct interaction with MCP servers; granular exploration of Tools/Resources/Prompts |
| **MCP Discovery** | Lightweight Rust CLI for discovering and exploring MCP server capabilities |
| **Tester MCP Client (Apify)** | Lightweight open source MCP client for functional smoke testing and quick sanity checks |

---

## 🔒 MCP Security

MCP gives AI broad tool-calling capabilities. Security cannot be an afterthought.

### Core Threat Model

| Threat | Description | Mitigation |
|---|---|---|
| **Prompt Injection** | Malicious content in tool responses injects instructions that alter AI behavior | Strictly validate tool return values; use BoostSecurity / mcp-scan |
| **Tool Poisoning** | Malicious MCP servers embed hidden instructions in tool descriptions | Only use servers from trusted sources; audit tool descriptions |
| **Cross-server Attacks** | Tool name conflicts across servers trigger unintended behavior | Clients use fully-qualified tool names; server namespace isolation |
| **Data Exfiltration** | Servers access data beyond what is strictly necessary | Least privilege principle; restrict directory and API scope |
| **Unauthenticated Access** | Remote MCP servers accessible without authentication | Enforce OAuth 2.0 or API keys; never expose stdio servers to the network |

### Security Tools

| Tool | GitHub | Description |
|---|---|---|
| **mcp-scan** | [invariantlabs-ai/mcp-scan](https://github.com/invariantlabs-ai/mcp-scan) | Open source MCP security scanner; detects prompt injection, tool poisoning, suspicious tool descriptions |
| **Intercept** | [policylayer/intercept](https://github.com/policylayer/intercept) | Open source control layer for MCP tool calls; drop-in proxy that enforces rate limits, spend caps, access controls, and argument restrictions via YAML policy files; sub-ms evaluation; audit logging |
| **BoostSecurity** | Official | Prevents AI coding agents from introducing vulnerable npm/pip packages; CI/CD integration |
| **Cycode** | Official | SAST + secret scanning + IaC security; catches security issues at development time |

### Security Best Practices

**Server side:**
- Always validate and sanitize tool parameters; never trust unvalidated data from the AI
- Implement least privilege: filesystem servers should only access the required directories
- Clearly document capability boundaries in tool descriptions; avoid ambiguity
- Remote servers must implement OAuth 2.0 authentication (required by MCP spec 2025-11-25)
- Log all tool calls for audit purposes

**Client / user side:**
- Only install MCP servers from trusted sources
- Review tool descriptions; be suspicious of unusually long descriptions (may contain hidden instructions)
- Use MCP Inspector to examine server behavior before connecting to production systems
- Never hardcode API keys in config files; use environment variables

**Further reading:**
- [Semgrep: A Security Engineer's Guide to MCP](https://semgrep.dev/blog/2025/a-security-engineers-guide-to-mcp/) — Most comprehensive MCP security audit guide
- [MCP Security Architecture](https://modelcontextprotocol.io/docs/concepts/security) — Official security documentation

---

## 📖 Tutorials, Blogs & Articles

### Official Documentation & Getting Started

- [MCP Official Docs](https://modelcontextprotocol.io/docs) — Authoritative reference from architecture concepts to SDK usage
- [MCP Quickstart](https://modelcontextprotocol.io/quickstart) — Build your first MCP server in 30 minutes
- [MCP Architecture Overview](https://modelcontextprotocol.io/docs/concepts/architecture) — Deep dive into the Client-Server architecture and three core primitives
- [**microsoft/mcp-for-beginners**](https://github.com/microsoft/mcp-for-beginners) ⭐ — Microsoft's MCP beginner course; C# / Java / TypeScript / Python / Rust multi-language examples; aligned with spec 2025-11-25

### In-Depth Technical Articles

- [10 Best MCP Servers for Developers (2026)](https://www.firecrawl.dev/blog/best-mcp-servers-for-developers) — Firecrawl; each server includes full config examples
- [Semgrep: A Security Engineer's Guide to MCP](https://semgrep.dev/blog/2025/a-security-engineers-guide-to-mcp/) — The most authoritative deep-dive on MCP security auditing
- [MCP Inspector: A Deep Dive](https://skywork.ai/skypage/en/A-Deep-Dive-into-the-MCP-Inspector) — Complete Inspector usage guide including CVE-2025-49596 explanation
- [GitHub Blog: 9 Open Source MCP Projects Worth Watching](https://github.blog/open-source/accelerate-developer-productivity-with-these-9-open-source-ai-and-mcp-projects/) — GitHub's curated picks from the MCP ecosystem
- [Official Go SDK Deep Dive](https://socket.dev/blog/official-go-sdk-for-mcp) — Architecture decisions behind the Go SDK
- [Context7: Solving AI Code Hallucination](https://dev.to/prithwish_nath/5-essential-mcp-servers-that-give-claude-cursor-real-superpowers-2025-nf6) — Real-world Context7 impact

### Learning Paths

**Beginners (understanding what MCP is):**
1. [Official MCP Introduction](https://modelcontextprotocol.io) → [Architecture Overview](https://modelcontextprotocol.io/docs/concepts/architecture)
2. Install [Claude Desktop](https://claude.ai/download) or [Cursor](https://cursor.sh)
3. Add your first MCP server (recommended: start with Playwright or filesystem)
4. Debug and verify with [MCP Inspector](https://github.com/modelcontextprotocol/inspector)

**Developers (building your own server):**
1. Python path: Official Python SDK + [FastMCP](https://github.com/jlowin/fastmcp)
2. TypeScript path: Official TypeScript SDK + [MCP Framework](https://github.com/QuantGeekDev/mcp-framework)
3. Reference [microsoft/mcp-for-beginners](https://github.com/microsoft/mcp-for-beginners) for multi-language examples
4. Test and debug with [MCP Inspector](https://github.com/modelcontextprotocol/inspector)

---

## 🎥 Videos & Talks

| Resource | Type | Description |
|---|---|---|
| [MCP Official Introduction Video](https://modelcontextprotocol.io) | Official | Protocol designers introduce MCP's design philosophy |
| [Anthropic MCP Launch Announcement](https://www.anthropic.com/news/model-context-protocol) | Announcement | Official statement from MCP's November 2024 launch |
| [GitHub Blog: Accelerating Developer Productivity with MCP](https://github.blog/open-source/accelerate-developer-productivity-with-these-9-open-source-ai-and-mcp-projects/) | Blog + Video | GitHub's perspective on the MCP ecosystem |
| [Lex Fridman #491: OpenClaw (deep MCP discussion)](https://www.youtube.com/watch?v=YFjfBk8HI5o) | Podcast | MCP's role in the agent ecosystem, grounded in OpenClaw practice |

---

## 🗺️ Server Directories & Discovery

Browse and search thousands of MCP servers on these platforms:

| Platform | Link | Description |
|---|---|---|
| 🔵 **MCP Official Registry** | [registry.modelcontextprotocol.io](https://registry.modelcontextprotocol.io) | Official registration and discovery; verified server list |
| ⭐ **mcp.so** | [mcp.so](https://mcp.so) | Community's largest MCP server directory; 13,000+ servers; searchable |
| ⭐ **PulseMCP** | [pulsemcp.com](https://pulsemcp.com) | Server + client dual directory; 531+ clients; continuously updated |
| **mcp-awesome.com** | [mcp-awesome.com](https://mcp-awesome.com) | 1,200+ quality-verified MCP servers with installation tutorials |
| **MCPIndex** | [mcpindex.net](https://mcpindex.net) | Multi-client installation config; one-click config generation for Cursor/Windsurf/Zed |
| **Glama MCP** | [glama.ai/mcp](https://glama.ai/mcp/clients) | Server and client directory maintained by Glama Chat (multimodal AI client) |

---

## 🗺️ Related Awesome Lists

| List | Scope |
|---|---|
| [punkpeye/awesome-mcp-servers](https://github.com/punkpeye/awesome-mcp-servers) | Most comprehensive English MCP server collection (with companion site glama.ai/mcp) |
| [wong2/awesome-mcp-servers](https://github.com/wong2/awesome-mcp-servers) | Another high-quality English server collection |
| [punkpeye/awesome-mcp-clients](https://github.com/punkpeye/awesome-mcp-clients) | Client-focused collection |
| [cyanheads/model-context-protocol-resources](https://github.com/cyanheads/model-context-protocol-resources) | Practice-oriented MCP learning resources with 8 handwritten server implementations |
| [microsoft/mcp-for-beginners](https://github.com/microsoft/mcp-for-beginners) | Microsoft's multi-language beginner course |
| [EthanYolo01/Awesome-OpenClaw](https://github.com/EthanYolo01/Awesome-OpenClaw) | OpenClaw AI Agent framework resources (sister list) |

---

## 🤝 Contributing

Contributions are welcome! This list prioritizes **verified links + opinionated curation** over exhaustive listing.

**Before submitting:**
1. Verify the link is real and working (visit it yourself)
2. Include a clear description (what, who, why it belongs here)
3. Check for duplicates first
4. Match the format of the existing section

**How to contribute:** Submit a Pull Request, or report broken links in Issues.

**Maintainer contact:** kalayolo86@gmail.com

---

<div align="center">

**Found this useful?** Give it a ⭐ and share it with your team.
**Something missing or a dead link?** [Open an issue](https://github.com/EthanYolo01/Awesome-MCP/issues) or submit a PR.

*Last updated: March 2026 · Maintained with ❤️ by the community*

🌐 Language / 语言切换：**English** | [中文](README_CN.md)

</div>
