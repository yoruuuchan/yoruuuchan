# yoru

*[English](README.md)*

底子是拍片的——相机、穿越机、达芬奇。后来开始做 AI 产品、Agent 基础设施和各种必须经得住真实设备、真实工作流折腾的工具：手机、手表、Windows、创作流水线。比起 demo 漂不漂亮，我更在意它部署以后、遇到真实用户和边界情况以后还成不成立。

---

### 代表项目

**[芦苇](https://github.com/yoruuuchan/wechat-md-studio)** — 人和 AI 围绕同一篇公众号文章协作的排版工作台。227 套主题跑在同一套语义 AST 上，3 套自己写的，224 套移植过来并保留作者与 License。Markdown 是唯一的内容源，AI 可以通过 MCP 起稿，但拿不走这份文档。[在线](https://wechat.yoru-and-akari.dev)。

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — 代理一挂，Claude Desktop 12 秒内直连了 25 次。这组防火墙规则让它 fail-closed，README 也记录了六种看上去对但实际没解决问题的做法。

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — vivo WATCH GT 的健康数据官方不让导，就自己逆。手表 RPK → 手机 APK → 自建数据库 → MCP。

**[Listening Bridge](https://github.com/yoruuuchan/listening-bridge)** — 把 Android / Windows 当前播放会话交给 AI：正在听什么、同步歌词上下文，以及通过 MCP 提供明确的播放控制。

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — 给独立创作者用的自托管执行台：项目、分镜、外拍、复盘、备份，以及通过 MCP 接入的 AI agent。

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — “是我这边的问题吗？”一个页面说清楚。状态 + 可达性探测，跑在 Cloudflare 上。[在线](https://is-ai-down.yoru-and-akari.dev)。

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — 整理并验证把自定义 MCP server 接进 ChatGPT 的可行路径，覆盖直连和 runtime / aggregation 两类架构。

### 创作系统

**[Yoru Design Systems](https://github.com/yoruuuchan/yoru-design-systems)** — 九套各自独立的设计系统，每一套都是可安装的 Agent Skill：设计指南、CSS tokens、组件和样张卡，覆盖网页、视频、幻灯片与长内容。

**[Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — Agent Skill：一句话创意 → 4K H.265，走 Blender + Resolve，并检查帧数、编码和校验和。

### 上游贡献

自己仓库以外的 7 个项目里，有 39 个已合并 PR。

- **[Operit](https://github.com/AAswordman/Operit)** — Android AI agent · [21 个已合并 PR](https://github.com/AAswordman/Operit/pulls?q=is%3Apr+author%3Ayoruuuchan+is%3Amerged)：模型 / Provider 接入、Tool Call 与历史消息正确性、Compose / DSL 状态与时序、崩溃和 UX 修复
- **[cli2api](https://github.com/caigee-cmd/cli2api)** — 面向编码 CLI 的多账号 API 代理 · [10 个已合并 PR](https://github.com/caigee-cmd/cli2api/pulls?q=is%3Apr+author%3Ayoruuuchan+is%3Amerged)：Provider 适配（含实验性的华为云 CodeArts 接入）、同 Provider 最早过期优先的账号调度、模型目录持久化、流式 tool call 中保留工具名
- **零散的几个** — gzh-design-skill（公众号剪贴板序列化）、open-kimi-ppt-skill（浏览器启动与下载竞态，[#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5) [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6)）、awesome-ai-companion、H440-FPV 机架

---

yoruandakari@duck.com
