<div align="center">

# YORU

[English](README.md) · [中文](README.zh-CN.md)

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&duration=2800&pause=800&color=5F86FF&center=true&vCenter=true&width=800&lines=AI+application+builder;Agent+tools+%C3%97+MCP+%C3%97+creator+systems;Turning+%22can+AI+do+this%3F%22+into+working+software)](https://git.io/typing-svg)

**产品 × 工程 × 视觉创作 × AI**

![AI Applications](https://img.shields.io/badge/AI_APPLICATIONS-5F86FF?style=for-the-badge)
![Agent Infrastructure](https://img.shields.io/badge/AGENT_INFRASTRUCTURE-5EEAD4?style=for-the-badge&labelColor=111827)
![MCP](https://img.shields.io/badge/MCP-897CD3?style=for-the-badge)
![Creator Tools](https://img.shields.io/badge/CREATOR_TOOLS-52B6D9?style=for-the-badge)
![Visual Systems](https://img.shields.io/badge/VISUAL_SYSTEMS-FF6B78?style=for-the-badge)

</div>

---

我在做 **AI 应用、Agent 基础设施和创作者工具**。很多项目都从一个很具体的麻烦，或者一句「这玩意能不能真的做出来？」开始；一旦决定做，就尽量把它推进到真实环境能跑，而不是停在 demo。

我尤其喜欢那些落在 **产品、工程、视觉表达、桌面软件、MCP 和自托管系统** 交界处的问题。

## 项目

### AI 应用

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — 给单个创作者使用的自托管执行台：从灵感收集、项目拆解、分镜、外拍执行，到复盘、备份，以及给 AI Agent 使用的 append-only MCP 通道。  
`Python` · `FastAPI` · `React` · `SQLite` · `Docker` · `MCP`

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — 把自己 vivo 手机和手表已经采集到的健康数据送进自己控制的数据库，再通过 MCP 提供给 AI 助手使用的一套自托管桥接系统。  
`Android` · `BlueOS` · `Cloudflare` · `Health Data` · `MCP`

**[LyricLens](https://github.com/yoruuuchan/LyricLens)** — 一个多 Host 的歌词语言学习系统：BetterNCM 插件、独立 Windows 桌面端和移动 Review PWA，共同把实时歌词变成 AI 辅助学习卡片。  
`Tauri` · `Rust` · `JavaScript` · `LLM`

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — 一个轻量的公开 AI 服务状态聚合页。  
`TypeScript` · `Cloudflare`

### AI 基础设施与集成

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — 给 Codex、Claude Code 等工程 Agent 使用的 Skill，把「自定义 MCP 接进 ChatGPT」这件事固定成一条可复用的工程路径：Remote MCP、OAuth 2.1、HTTPS 暴露，以及真实 tool call 验收。  
`Agent Skill` · `MCP` · `OAuth 2.1` · `Cloudflare`

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — Windows 上的 fail-closed 防火墙保护层：当代理或 TUN 路径消失时，阻止 Claude 回落到物理网卡直接访问公网，并提供自检与显式验证。  
`PowerShell` · `Windows Firewall` · `MSIX` · `Networking`

### 创作系统与 Agent Skills

**[Create Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — 一套端到端 3D 视频制作 Agent Skill：从创意或视觉参考出发，推进到风格锁定、分镜、AI 参考图、Blender 制作、可恢复渲染、Resolve 剪辑和最终媒体校验。  
`Agent Skill` · `Blender` · `DaVinci Resolve` · `Video Pipeline`

**[AI Application Showcase Video](https://github.com/yoruuuchan/ai-application-showcase-video)** — 把零散 AI 项目材料整理成事实约束下的对外视频策划包：事实表、缺失信息、60 秒脚本、分镜、拍摄清单、后期 brief、平台文案和审核记录。  
`Agent Skill` · `Content Workflow` · `Validation`

**[Visual Skill Library](https://github.com/yoruuuchan/visual-skill-library)** — 我自己的视觉 AI Skill、工作流与设计系统收藏库，同时保留来源、License 和 source-fidelity 等整理信息。  
`Visual AI` · `Editorial` · `Data Visualization` · `Design Systems`

## 开源贡献

给自己每天在用的工具，往上游提的修复。

- **[OpenCLI](https://github.com/jackwener/OpenCLI)** · 把任意网站变成 AI Agent 可用的 CLI — [#2281](https://github.com/jackwener/OpenCLI/pull/2281) Codex 适配器：优先选择主渲染进程而不是 avatar-overlay 的 CDP target，并改为跟踪最新一条 assistant 消息，附回归测试 · *审核中*
- **[Operit](https://github.com/AAswordman/Operit)** · Android 上的 AI Agent 应用 — [#974](https://github.com/AAswordman/Operit/pull/974) 修复代码编辑器在 HONOR ROM 上快速滑动即崩溃的问题（`OverScroller` 在非主线程步进，撞上了要求 Looper 的 `Choreographer` 调用）· *已合并*
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** · Kimi Slides 的 Agent Skill — [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6) Windows 上自动拉起调试用 Chrome，agent-browser 起不来浏览器时导出仍能跑通 · *已合并* · [#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5) 修复 Chrome 在扫描途中重命名下载文件导致的 `FileNotFoundError` 竞态 · *已合并*

---

## 我偏好的工程方式

- **真实环境验收优先于 demo 成功。** 测试通过只是前置条件，不等于完成。
- **显式失败优先于静默 fallback。** 出问题就应该明确告诉我坏在哪里、为什么坏。
- **在值得的地方保留所有权和控制权。** 自托管、local-first 和清晰的数据边界，不是为了仪式感，而是为了让系统更容易理解、验证和信任。

---

## Toolbox

<p>
  <img src="https://img.shields.io/badge/TypeScript-3186FF?style=flat-square&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-5F86FF?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Rust-2C3440?style=flat-square&logo=rust&logoColor=white" />
  <img src="https://img.shields.io/badge/React-52B6D9?style=flat-square&logo=react&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-45C496?style=flat-square&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/Tauri-897CD3?style=flat-square&logo=tauri&logoColor=white" />
  <img src="https://img.shields.io/badge/Cloudflare-F0A000?style=flat-square&logo=cloudflare&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-3C90FF?style=flat-square&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-74A7D8?style=flat-square&logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/MCP-9898DC?style=flat-square" />
</p>

---

## 联系

📮 [1587761204@qq.com](mailto:1587761204@qq.com)  
欢迎聊 AI 产品、Agent 工具、创作者工作流，或者这一页上的任何东西。

---

<div align="center">

### 把奇怪的念头做成真的。

`AI applications` · `agent infrastructure` · `creator systems` · `self-hosted software` · `visual experiments`

</div>
