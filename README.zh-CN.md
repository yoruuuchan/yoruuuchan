# yoru

*[English](README.md)*

底子是拍片的——相机、穿越机、达芬奇。后来开始做 AI 产品、Agent 基础设施和各种必须经得住真实设备、真实工作流折腾的工具：手机、手表、Windows、创作流水线。比起 demo 漂不漂亮，我更在意它部署以后、遇到真实用户和边界情况以后还成不成立。

---

### 代表项目

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — 给独立创作者用的自托管执行台：项目、分镜、外拍、复盘、备份，以及通过 MCP 接入的 AI agent。

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — vivo WATCH GT 的健康数据官方不让导，就自己逆。手表 RPK → 手机 APK → 自建数据库 → MCP。

**[Listening Bridge](https://github.com/yoruuuchan/listening-bridge)** — 把 Android / Windows 当前播放会话交给 AI：正在听什么、同步歌词上下文，以及通过 MCP 提供明确的播放控制。

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — “是我这边的问题吗？”一个页面说清楚。状态 + 可达性探测，跑在 Cloudflare 上。[在线](https://is-ai-down.yoru-and-akari.dev)。

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — 整理并验证把自定义 MCP server 接进 ChatGPT 的可行路径，覆盖直连和 runtime / aggregation 两类架构。

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — 代理一挂，Claude Desktop 12 秒内直连了 25 次。这组防火墙规则让它 fail-closed，README 也记录了六种看上去对但实际没解决问题的做法。

### 创作系统

**[Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — Agent Skill：一句话创意 → 4K H.265，走 Blender + Resolve，并检查帧数、编码和校验和。

### 上游贡献

- **[Operit](https://github.com/AAswordman/Operit)** — Android AI agent · [20 个已合并 PR](https://github.com/AAswordman/Operit/pulls?q=is%3Apr+author%3Ayoruuuchan+is%3Amerged)：模型 / Provider 接入、Tool Call 与历史消息正确性、Compose / DSL 状态与时序、崩溃和 UX 修复
- **[gzh-design-skill](https://github.com/isjiamu/gzh-design-skill)** — 微信公众号编辑器复制链路修复（[#19](https://github.com/isjiamu/gzh-design-skill/pull/19)）
- **[OpenCLI](https://github.com/jackwener/OpenCLI)** — Codex Desktop CDP 适配（[#2281](https://github.com/jackwener/OpenCLI/pull/2281)）
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** — 浏览器启动与下载竞态修复（[#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5)、[#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6)）

---

yoruandakari@duck.com
