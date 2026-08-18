<div align="center">

# YORU

[English](README.md) · [中文](README.zh-CN.md)

*从视觉这边出发，往 AI 应用、Agent 基础设施和创作者系统里长。*

</div>

---

我做的东西大多从自己真的遇到的问题开始：手表数据出不来、代理一挂 Claude 就直连、想边听歌边把歌词变成学习卡片。然后一路往下做，直到它不只在 Demo 里好看，而是真的能在日常环境里站得住。

我的底子在视觉这边：摄影、电影机、穿越机、达芬奇，也做过自己的账号。现在反复出现的一条主线，是把 AI Agent 接进我身边真实存在的系统——本地应用、手机、手表、Windows 机器、云端入口、创作工具——再把最后一公里磨到我自己愿意长期用。

这一页上的大部分东西都和 AI Agent 一起完成。真正让我在意的，是生成之后的部分：决定什么东西值得存在、理解系统、设约束、处理难看的边角问题，以及确认它离开编辑器以后仍然成立。

## 项目

### 日常真的在用

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — 我自己的内容项目从灵感、分镜、外拍到复盘，散在太多个 App 里，于是做了一个装在自己机器上的执行台，只服务一个人：没有多租户，没有团队席位。它跑在 5 美元一个月的 VPS 上，外拍断网时编辑先在本地排队；AI Agent 通过 MCP 接进来，能读、能追加，不能改历史。  
`Python` · `FastAPI` · `React` · `SQLite` · `Docker` · `MCP`

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — 我想让 AI 助手真的看见我昨晚睡得怎么样，而不是每天早上等我打字告诉它。vivo 手表的数据走官方通道出不来，我就自己挖：手表端 RPK、手机端 APK、自己的数据库，再通过 MCP 交给 AI。已经在 vivo X200 Pro 和 WATCH GT 上做过完整真机验证。  
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

给自己真的在用的工具往上游送修复和功能。

- **[Operit](https://github.com/AAswordman/Operit)** · Android AI Agent 应用 — 最近的改动横跨 Android / Compose 状态时序、模型供应商接入、Tool API 和崩溃处理：[ #974](https://github.com/AAswordman/Operit/pull/974)、[#990](https://github.com/AAswordman/Operit/pull/990)、[#991](https://github.com/AAswordman/Operit/pull/991)、[#993](https://github.com/AAswordman/Operit/pull/993) 已合并；[#987](https://github.com/AAswordman/Operit/pull/987) 和 [#992](https://github.com/AAswordman/Operit/pull/992) 审核中。
- **[OpenCLI](https://github.com/jackwener/OpenCLI)** · 把网站和桌面应用变成 AI Agent 可用的 CLI — [#2281](https://github.com/jackwener/OpenCLI/pull/2281) 适配当前 Codex Desktop 的 CDP target 布局和虚拟化对话 DOM · *审核中*
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** · Kimi Slides 的 Agent Skill — [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6) 在 Windows 上自动拉起调试浏览器，解决 agent-browser 无法启动 Chrome 时的导出问题；[#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5) 修复 Chrome 下载文件重命名竞态 · *已合并*

---

## 我怎么做东西

在决定再造一层之前，我会先去找已经存在的那一层。成熟项目只差一点就能满足需求时，我更愿意直接用、patch、fork，或者把修复送回上游，而不是从零重写一遍通用基础设施。

测试通过只是前置条件，不是完成。我还是会回到真实机器和真实硬件上看，所以项目文档里经常会出现具体设备、环境检查、验证脚本和失败状态。我偏爱 fail-closed：一个明确、可诊断的错误，比一个悄悄降级却还显示正常的系统好处理得多。

能自己保管的数据（健康、创作记录、笔记）在现实可行时尽量留在自己的机器或基础设施里。出了问题，我想知道该去哪找，也想知道谁能看见它。

---

## Toolbox

<p>
  <img src="https://img.shields.io/badge/TypeScript-3186FF?style=flat-square&logo=typescript&logoColor=white" />
  <img src="https://img.shields.io/badge/Python-5F86FF?style=flat-square&logo=python&logoColor=white" />
  <img src="https://img.shields.io/badge/Rust-2C3440?style=flat-square&logo=rust&logoColor=white" />
  <img src="https://img.shields.io/badge/Kotlin-897CD3?style=flat-square&logo=kotlin&logoColor=white" />
  <img src="https://img.shields.io/badge/React-52B6D9?style=flat-square&logo=react&logoColor=white" />
  <img src="https://img.shields.io/badge/FastAPI-45C496?style=flat-square&logo=fastapi&logoColor=white" />
  <img src="https://img.shields.io/badge/Tauri-9898DC?style=flat-square&logo=tauri&logoColor=white" />
  <img src="https://img.shields.io/badge/Android-5DCE9C?style=flat-square&logo=android&logoColor=white" />
  <img src="https://img.shields.io/badge/Cloudflare-F0A000?style=flat-square&logo=cloudflare&logoColor=white" />
  <img src="https://img.shields.io/badge/Docker-3C90FF?style=flat-square&logo=docker&logoColor=white" />
  <img src="https://img.shields.io/badge/SQLite-74A7D8?style=flat-square&logo=sqlite&logoColor=white" />
  <img src="https://img.shields.io/badge/PowerShell-2F3E66?style=flat-square&logo=powershell&logoColor=white" />
  <img src="https://img.shields.io/badge/MCP-9898DC?style=flat-square" />
</p>

---

## 联系

[yoruandakari@duck.com](mailto:yoruandakari@duck.com) · [1587761204@qq.com](mailto:1587761204@qq.com)  
欢迎聊 AI 产品、Agent 工具、创作者工作流，或者这一页上的任何东西。

---

<div align="center">

### 把奇怪的念头做成真的。

</div>
