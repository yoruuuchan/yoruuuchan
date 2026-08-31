# yoru

*[English](README.md)*

底子是拍片的——相机、穿越机、达芬奇。后来开始造工具，主要填 AI demo 和真实环境之间的缝：手机、手表、Windows、视频流水线。都是和 AI 一起做的；我在意的是离开编辑器之后还成不成立。

---

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — 一个人的内容执行台。$5/月 VPS，AI agent 走 MCP 接入，只能追加不能改。

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — vivo 手表的健康数据官方不让导，自己逆的。手表 RPK → 手机 APK → 自建数据库 → MCP。

**[LyricLens](https://github.com/yoruuuchan/LyricLens)** — 歌词 → 学习卡片，跟着播放同步。网易云插件 + [独立桌面端](https://github.com/yoruuuchan/lyriclens-desktop)（Tauri/Rust），不挑播放器。

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — "是我这边的问题吗？" 一个页面说清楚。状态 + 探测，跑在 Cloudflare 上。[在线](https://is-ai-down.yoru-and-akari.dev)。

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — 把 MCP server 接进 ChatGPT 能做到，但文档几乎没有。这是走通了的那条路。

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — 代理一挂，Claude Desktop 12 秒内直连了 25 次。这组防火墙规则让它断掉而不是漏出去。README 里列了六种看上去对但不管用的做法。

### 动态与视频

**[Motion System](https://github.com/yoruuuchan/yoru-motion-system)** — 18 套 Remotion 模板，从 [636 个人工审过的参考](https://github.com/yoruuuchan/yoru-motion-research)里长出来的。时间参数是从渲染结果里量的，不是凭感觉。

**[Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — Agent Skill：一句话创意 → 4K H.265，走 Blender + Resolve。帧数、编码、校验和没全过不算交付。

**[Showcase Video](https://github.com/yoruuuchan/ai-application-showcase-video)** — Agent Skill：项目素材 → 视频策划。没核实的说法，一个字的宣传也不写。

### 上游贡献

- **[Operit](https://github.com/AAswordman/Operit)** — Android AI agent · [8 个已合并 PR](https://github.com/AAswordman/Operit/pulls?q=is%3Apr+author%3Ayoruuuchan+is%3Amerged)：Compose 时序、模型接入、Tool API、崩溃处理
- **[OpenCLI](https://github.com/jackwener/OpenCLI)** — Codex Desktop CDP 适配（[#2281](https://github.com/jackwener/OpenCLI/pull/2281)）
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** — 浏览器启动 + 下载竞态修复（[#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5)、[#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6)）

---

yoruandakari@duck.com
