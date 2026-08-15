<div align="center">

# YORU

[English](README.md) · [中文](README.zh-CN.md)

*从视觉这边过来，现在做 AI 应用和创作者工具。*

</div>

---

我做的东西大多是先给自己用的，起点通常很小：手表数据出不来、代理一挂 Claude 就直连、想边听歌边把歌词变成学习卡片。然后一路做到它在真实环境里站得住。

我的底子在视觉那边：摄影、电影机、穿越机、达芬奇，也做过半年自媒体。所以我对「一个东西做出来了，别人能不能看懂、想不想用」这件事很在意，可能比对技术选型更在意。这一页上的大部分东西是我和 AI 一起做的，Yoru Studio 的署名就写着「我们三个」。

## 项目

### 日常在用的应用

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — 我自己的内容项目从灵感、分镜、外拍到复盘，散在太多个 App 里，于是做了一个装在自己机器上的执行台，只服务一个人：没有多租户，没有团队席位。它跑在 5 美元一个月的 VPS 上，外拍断网时编辑先在本地排队；AI Agent 通过 MCP 接进来，能读、能追加，不能改历史。  
`Python` · `FastAPI` · `React` · `SQLite` · `Docker` · `MCP`

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — 我想让 AI 助手真的看见我昨晚睡得怎么样，而不是每天早上等我打字告诉它。vivo 手表的数据走官方通道出不来，我就自己挖：手表端 RPK、手机端 APK、自己的数据库，再通过 MCP 交给 AI。全程在 vivo X200 Pro 和 WATCH GT 上真机验证，中间没有任何云服务。  
`Android` · `BlueOS` · `Cloudflare` · `Health Data` · `MCP`

**[LyricLens](https://github.com/yoruuuchan/LyricLens)** — 听歌的时候总想顺手把歌词里的词记下来。LyricLens 就是这个念头做成了东西：网易云里的 BetterNCM 插件读到当前歌词，交给模型生成学习卡片，跟着歌词滚动显示。后来又长出了[不依赖任何播放器的 Windows 桌面端](https://github.com/yoruuuchan/lyriclens-desktop)和手机上复习用的 PWA，三端共用一本笔记。  
`Tauri` · `Rust` · `JavaScript` · `LLM`

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — AI 服务一出问题，群里第一句话永远是「是我这边的问题吗」。所以做了一个页面，把各家官方状态页和轻量探测聚合在一起，一眼看完。整站跑在 Cloudflare 上（Worker + D1），[已经上线](https://is-ai-down.yoru-and-akari.dev)。  
`TypeScript` · `Cloudflare`

### 接线与保险

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — 我想把自己的 MCP 接进 ChatGPT，发现能力是有的，公开文档却几乎没有，每次都要重新摸索半天。于是把摸清的那条路（Remote MCP → OAuth 2.1 → Cloudflare Tunnel → 真实 tool call 验证）写成 Agent Skill，让 Claude Code 和 Codex 下次直接从固定起点出发。  
`Agent Skill` · `MCP` · `OAuth 2.1` · `Cloudflare`

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — 代理挂掉的那一刻，Claude Desktop 会立刻用你家宽带 IP 去直连，我在自己的防火墙日志里看到过 12 秒 25 次。这是一组只作用于物理网卡的 Windows 防火墙规则，让它在那一刻是断掉，而不是悄悄漏出去；顺带处理了 MSIX 更新后规则失效的问题，附一套用无害国内 IP 做 A/B 对照的验证脚本。README 里还排除了六种看起来对、实际不管用的做法。  
`PowerShell` · `Windows Firewall` · `MSIX` · `Networking`

### 视频、视觉与 Agent Skills

**[Create Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — 我想不靠 3D 团队，也能把一句创意做成一条 4K 成片。这个 Skill 让 Agent 走完整条流水线：风格锁定、分镜、AI 参考图、Blender 场景、可断点恢复的渲染、Resolve 剪辑，最后帧数、编码、色彩标签和 SHA-256 逐项校验通过才算交付。  
`Agent Skill` · `Blender` · `DaVinci Resolve` · `Video Pipeline`

**[AI Application Showcase Video](https://github.com/yoruuuchan/ai-application-showcase-video)** — AI 项目的宣传材料通常是一堆零散的 PPT、技术描述、会议纪要和没核实过的说法。这个 Skill 强制 Agent 先建立事实基线，再写任何宣传内容：事实表、缺失信息清单、60 秒脚本、分镜、拍摄清单、后期 brief、平台文案；效率类说法没核实的，一律标「待确认」。  
`Agent Skill` · `Content Workflow` · `Validation`

**[Visual Skill Library](https://github.com/yoruuuchan/visual-skill-library)** — 我一直在收集视觉上真正有辨识度的 AI Skill、工作流和设计系统，而收藏夹是这类东西的坟墓。所以做成了索引库：每一项都记来源、License 和「跟原版差多少」。先收集再整理，先记录再测试，真正在任务里用过、验证过的才往前排。  
`Visual AI` · `Editorial` · `Data Visualization` · `Design Systems`

## 开源贡献

给自己每天在用的工具，往上游提的修复。

- **[OpenCLI](https://github.com/jackwener/OpenCLI)** · 把任意网站变成 AI Agent 可用的 CLI — [#2281](https://github.com/jackwener/OpenCLI/pull/2281) Codex 适配器：优先选择主渲染进程而不是 avatar-overlay 的 CDP target，并改为跟踪最新一条 assistant 消息，附回归测试 · *审核中*
- **[Operit](https://github.com/AAswordman/Operit)** · Android 上的 AI Agent 应用 — [#974](https://github.com/AAswordman/Operit/pull/974) 修复代码编辑器在 HONOR ROM 上快速滑动即崩溃的问题（`OverScroller` 在非主线程步进，撞上了要求 Looper 的 `Choreographer` 调用）· *已合并*
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** · Kimi Slides 的 Agent Skill — [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6) Windows 上自动拉起调试用 Chrome，agent-browser 起不来浏览器时导出仍能跑通 · *已合并* · [#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5) 修复 Chrome 在扫描途中重命名下载文件导致的 `FileNotFoundError` 竞态 · *已合并*

---

## 我怎么做东西

- **测试跑通之后，我还会去真机上看一遍。** Akari Pulse 的 README 写着具体的手机型号、手表固件号和验证日期；Kill-Switch 的验证脚本没有 A/B 对照就不出结论。「demo 能跑、实机不行」这种事我遇到过太多次。
- **坏了就大声坏。** Kill-Switch 的整个设计就是 fail-closed：代理没了就断，而不是悄悄换条路。我宁可看到一个清楚的报错，也不要一个悄悄降级还显示正常的系统。
- **能自己保管的数据就自己保管。** 健康数据、创作记录、笔记都放在自己的机器或自己的 VPS 上。出了问题我知道去哪找，也知道谁能看到。

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

</div>
