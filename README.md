<div align="center">

# YORU

[English](README.md) · [中文](README.zh-CN.md)

*Building AI applications, agent infrastructure, and creator systems — from the visual side outward.*

</div>

---

Most of what I build starts as a real annoyance in my own workflow: my watch will not give up its data, Claude connects directly the moment the proxy dies, I want lyrics to turn into flashcards while I listen. Then I keep pushing until the thing survives the real environment instead of only the demo.

My background is visual: photography, cinema cameras, FPV drones, DaVinci Resolve, and running my own channels. These days the recurring pattern is connecting AI agents to the systems around me — local apps, phones, watches, Windows machines, cloud edges, creator tools — and making the last mile reliable enough that I actually use it.

Most of what is on this page was built with AI agents as collaborators. The part I care about is what comes after generation: deciding what should exist, understanding the system, setting constraints, debugging the ugly edge cases, and verifying that the result holds up outside the editor.

## Projects

### Apps I actually run

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — My own content projects (ideas, storyboards, field shoots, retrospectives) were scattered across too many apps, so I built a studio that runs on my own box and serves exactly one person: no multi-tenant story, no team seats. It fits on a $5/month VPS, queues edits locally when the network drops mid-shoot, and lets AI agents in over MCP with read and append-only write.  
`Python` · `FastAPI` · `React` · `SQLite` · `Docker` · `MCP`

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — I wanted my AI assistant to actually see how I slept, instead of waiting for me to type it in every morning. vivo's official path will not hand the data over, so I dug it out myself: a watch-side RPK, a phone-side APK, my own database, MCP on top. Verified end to end on a vivo X200 Pro and a WATCH GT.  
`Android` · `BlueOS` · `Cloudflare` · `Health Data` · `MCP`

**[LyricLens](https://github.com/yoruuuchan/LyricLens)** — I kept wanting to grab words out of lyrics while listening. LyricLens is that impulse made real: a BetterNCM plugin reads the current lyric inside NetEase Cloud Music, has a model turn it into learning cards, and shows them in sync with the lyric scroll. It later grew a [player-agnostic Windows desktop app](https://github.com/yoruuuchan/lyriclens-desktop) and a phone review PWA, all sharing one notebook.  
`Tauri` · `Rust` · `JavaScript` · `LLM`

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — Whenever an AI service hiccups, the first message in every group chat is "is it just me?" So I made one page that pulls the official status pages and lightweight reachability probes together. It runs entirely on Cloudflare (Worker + D1) and is [live](https://is-ai-down.yoru-and-akari.dev).  
`TypeScript` · `Cloudflare`

### Glue and guardrails

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — I wanted my own MCP server inside ChatGPT and found that the capability exists but the public docs barely do; every attempt cost half a day of rediscovery. So I wrote down the path that works (Remote MCP → OAuth 2.1 → Cloudflare Tunnel → a real tool-call check) as an Agent Skill, so Claude Code and Codex start from a fixed point next time.  
`Agent Skill` · `MCP` · `OAuth 2.1` · `Cloudflare`

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — The moment the proxy dies, Claude Desktop starts connecting directly over your home IP; I watched it try 25 times in 12 seconds in my own firewall log. This is a set of Windows Firewall rules scoped to physical NICs, so in that moment Claude simply drops instead of quietly leaking. It also survives the rule breakage that MSIX updates cause, and ships a verification script that A/B-tests against a harmless domestic IP. The README walks through six fixes that look right and do not work.  
`PowerShell` · `Windows Firewall` · `MSIX` · `Networking`

### Video, visuals, and Agent Skills

**[YORU Motion Research](https://github.com/yoruuuchan/yoru-motion-research) → [Motion System](https://github.com/yoruuuchan/yoru-motion-system)** — I did not want another folder of motion references that an agent could only vaguely imitate. I manually reviewed 636 candidates across Locomotion and Video Shotcraft, kept the full positive/negative decision history, turned it into agent-readable preference data, then built the surviving patterns into an 18-template Remotion system. Timing is measured from rendered references; the implementation separates structure, rhythm, palette and skin, registers both 16:9 and 9:16, and keeps upstream licensing boundaries explicit.  
`Remotion` · `TypeScript` · `Motion Design` · `Human Curation` · `Agent Workflow`

**[Create Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — I wanted to take a one-line idea to a finished 4K video without a 3D team. This Skill walks an agent through the whole pipeline (style lock, storyboard, AI reference images, Blender scenes, crash-recoverable rendering, Resolve editing) and will not call it delivered until frame count, encoding, color labels and SHA-256 all check out.  
`Agent Skill` · `Blender` · `DaVinci Resolve` · `Video Pipeline`

**[AI Application Showcase Video](https://github.com/yoruuuchan/ai-application-showcase-video)** — Publicity for AI projects usually starts as scattered slides, technical notes, meeting minutes and unverified claims. This Skill makes an agent establish a factual baseline before it writes a word of promotion: fact sheet, missing-information list, 60-second script, storyboard, shooting checklist, post brief, platform copy. Every unverified efficiency claim gets marked "pending confirmation."  
`Agent Skill` · `Content Workflow` · `Validation`

## Open-source contributions

Fixes and features sent upstream to tools I actually use.

- **[Operit](https://github.com/AAswordman/Operit)** · Android AI agent app — recent work spans Android/Compose state timing, model-provider integration, tool APIs, Markdown gestures and crash handling: [#974](https://github.com/AAswordman/Operit/pull/974), [#987](https://github.com/AAswordman/Operit/pull/987), [#990](https://github.com/AAswordman/Operit/pull/990), [#991](https://github.com/AAswordman/Operit/pull/991), [#992](https://github.com/AAswordman/Operit/pull/992), [#993](https://github.com/AAswordman/Operit/pull/993), [#996](https://github.com/AAswordman/Operit/pull/996), and [#997](https://github.com/AAswordman/Operit/pull/997) merged; [#1002](https://github.com/AAswordman/Operit/pull/1002) is open.
- **[OpenCLI](https://github.com/jackwener/OpenCLI)** · turn websites and desktop apps into CLIs for AI agents — [#2281](https://github.com/jackwener/OpenCLI/pull/2281) adapts the Codex Desktop integration to its current CDP target layout and virtualized conversation DOM · *open*
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** · Agent Skill for Kimi Slides — [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6) auto-starts a debug browser on Windows when agent-browser cannot launch one · [#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5) fixes a Chrome download rename race · *merged*

---

## How I work

Before building another layer, I look for the existing one. If a mature project is close to what I need, I would rather use it, patch it, fork it, or send the fix upstream than rewrite the same infrastructure from zero.

Passing tests is a prerequisite, not the finish line. I go back to the real machine and the real hardware, which is why project docs tend to contain exact devices, environment checks, verification scripts and failure states. I like fail-closed designs: one explicit, diagnosable error is much easier to deal with than a system that quietly degrades and still shows green.

Data I can keep myself (health, creative records, notebooks) stays on my own machines or infrastructure whenever practical. When something breaks, I want to know where to look — and who can see it.

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

## Contact

[yoruandakari@duck.com](mailto:yoruandakari@duck.com) · [1587761204@qq.com](mailto:1587761204@qq.com)  
Happy to talk about AI products, agent tooling, creator workflows — or anything on this page.

---

<div align="center">

### Build weird things. Make them real.

</div>
