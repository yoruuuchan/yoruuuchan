<div align="center">

# YORU

[English](README.md) · [中文](README.zh-CN.md)

[![Typing SVG](https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=600&size=22&duration=2800&pause=800&color=5F86FF&center=true&vCenter=true&width=800&lines=AI+application+builder;Agent+tools+%C3%97+MCP+%C3%97+creator+systems;Turning+%22can+AI+do+this%3F%22+into+working+software)](https://git.io/typing-svg)

**product × engineering × visual creation × AI**

![AI Applications](https://img.shields.io/badge/AI_APPLICATIONS-5F86FF?style=for-the-badge)
![Agent Infrastructure](https://img.shields.io/badge/AGENT_INFRASTRUCTURE-5EEAD4?style=for-the-badge&labelColor=111827)
![MCP](https://img.shields.io/badge/MCP-897CD3?style=for-the-badge)
![Creator Tools](https://img.shields.io/badge/CREATOR_TOOLS-52B6D9?style=for-the-badge)
![Visual Systems](https://img.shields.io/badge/VISUAL_SYSTEMS-FF6B78?style=for-the-badge)

</div>

---

I build **AI applications, agent infrastructure, and creator tools**. Most projects start with a practical irritation or a weird “can this actually exist?” question, then get pushed until they work in a real environment instead of stopping at a demo.

I am especially interested in the seams between **product, engineering, visual communication, desktop software, MCP, and self-hosted systems**.

## Projects

### AI applications

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — A self-hosted execution studio for a single creator: inbox, projects, storyboards, field work, retrospectives, backups, and an append-only MCP channel for AI agents.  
`Python` · `FastAPI` · `React` · `SQLite` · `Docker` · `MCP`

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — A self-hosted bridge that moves health data from the owner's vivo phone and watch into an owner-controlled database and exposes it to AI assistants over MCP.  
`Android` · `BlueOS` · `Cloudflare` · `Health Data` · `MCP`

**[LyricLens](https://github.com/yoruuuchan/LyricLens)** — A multi-host lyric-learning system spanning a BetterNCM plugin, an independent Windows desktop app, and a mobile Review PWA, turning live lyrics into AI-assisted language-learning cards.  
`Tauri` · `Rust` · `JavaScript` · `LLM`

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — A small public status aggregation dashboard for AI services.  
`TypeScript` · `Cloudflare`

### AI infrastructure & integrations

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — An Agent Skill that gives Codex and Claude Code a stable engineering path for connecting custom MCP servers to ChatGPT: Remote MCP, OAuth 2.1, HTTPS exposure, and real tool-call verification.  
`Agent Skill` · `MCP` · `OAuth 2.1` · `Cloudflare`

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — A fail-closed Windows firewall guard designed to stop Claude from falling back to direct physical-interface Internet access when the proxy or TUN path disappears, with self-checks and explicit verification.  
`PowerShell` · `Windows Firewall` · `MSIX` · `Networking`

### Creative systems & Agent Skills

**[Create Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — An end-to-end Agent Skill that takes an idea or visual reference through style lock, storyboard, AI references, Blender production, recoverable rendering, Resolve editing, and final media validation.  
`Agent Skill` · `Blender` · `DaVinci Resolve` · `Video Pipeline`

**[AI Application Showcase Video](https://github.com/yoruuuchan/ai-application-showcase-video)** — An Agent Skill for turning scattered AI project materials into a fact-grounded public-facing video package: fact sheet, questions, 60-second script, storyboard, shooting plan, post brief, copy, and review record.  
`Agent Skill` · `Content Workflow` · `Validation`

**[Visual Skill Library](https://github.com/yoruuuchan/visual-skill-library)** — A curated personal library of visually distinctive AI skills, workflows, and design systems, with source, license, and fidelity notes kept alongside the collection.  
`Visual AI` · `Editorial` · `Data Visualization` · `Design Systems`

## Open-source contributions

Fixes sent upstream to tools I use every day.

- **[OpenCLI](https://github.com/jackwener/OpenCLI)** · turn any website into a CLI for AI agents — [#2281](https://github.com/jackwener/OpenCLI/pull/2281) Codex adapter: prefer the main renderer over the avatar-overlay CDP target and track the latest assistant message, with regression tests · *open*
- **[Operit](https://github.com/AAswordman/Operit)** · AI agent app for Android — [#974](https://github.com/AAswordman/Operit/pull/974) Fix a fling crash in the code editor on HONOR ROMs (`OverScroller` was stepped off the main thread and hit a `Choreographer` call that requires a Looper) · *merged*
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** · Agent Skill for Kimi Slides — [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6) Auto-start a debug Chrome on Windows so exports still work when agent-browser cannot launch one · *merged* · [#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5) Fix a `FileNotFoundError` race when Chrome renames a download mid-scan · *merged*

---

## How I like to build

- **Real-environment verification over demo success.** A passing test is a prerequisite, not the finish line.
- **Explicit failures over silent fallback.** If something is broken, the system should say where and why.
- **Owner-controlled infrastructure when it matters.** Self-hosting, local-first design, and clear data boundaries are useful when they make the system easier to understand and trust.

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

## Contact

📮 [1587761204@qq.com](mailto:1587761204@qq.com)  
Happy to talk about AI products, agent tooling, creator workflows — or anything on this page.

---

<div align="center">

### Build weird things. Make them real.

`AI applications` · `agent infrastructure` · `creator systems` · `self-hosted software` · `visual experiments`

</div>
