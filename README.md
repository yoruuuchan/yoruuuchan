<div align="center">

# YORU

[English](README.md) · [中文](README.zh-CN.md)

*Came from the visual side; now building AI applications and creator tools.*

</div>

---

Most of what I make is built for myself first, and it starts small: my watch won't give up its data, Claude connects directly the moment the proxy dies, I want lyrics to turn into flashcards while I listen. Then it gets pushed until it holds up in a real environment.

My background is visual: photography, cinema cameras, FPV drones, DaVinci Resolve, half a year of running my own channels. So I care a lot about whether a thing, once built, is something people can understand and want to use; possibly more than I care about the stack. Most of what's on this page was made together with AI. The credits on Yoru Studio literally read "the three of us."

## Projects

### Apps I actually run

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — My own content projects (ideas, storyboards, field shoots, retrospectives) were scattered across too many apps, so I built a studio that runs on my own box and serves exactly one person: no multi-tenant story, no team seats. It fits on a $5/month VPS, queues edits locally when the network drops mid-shoot, and lets AI agents in over MCP with read and append-only write.  
`Python` · `FastAPI` · `React` · `SQLite` · `Docker` · `MCP`

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — I wanted my AI assistant to actually see how I slept, instead of waiting for me to type it in every morning. vivo's official path won't hand the data over, so I dug it out myself: a watch-side RPK, a phone-side APK, my own database, MCP on top. Verified end to end on a vivo X200 Pro and a WATCH GT, with no cloud service anywhere in the middle.  
`Android` · `BlueOS` · `Cloudflare` · `Health Data` · `MCP`

**[LyricLens](https://github.com/yoruuuchan/LyricLens)** — I kept wanting to grab words out of lyrics while listening. LyricLens is that impulse made real: a BetterNCM plugin reads the current lyric inside NetEase Cloud Music, has a model turn it into learning cards, and shows them in sync with the lyric scroll. It later grew a [player-agnostic Windows desktop app](https://github.com/yoruuuchan/lyriclens-desktop) and a phone review PWA, all sharing one notebook.  
`Tauri` · `Rust` · `JavaScript` · `LLM`

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — Whenever an AI service hiccups, the first message in every group chat is "is it just me?" So I made one page that pulls the official status pages and lightweight reachability probes together. It runs entirely on Cloudflare (Worker + D1) and is [live](https://is-ai-down.yoru-and-akari.dev).  
`TypeScript` · `Cloudflare`

### Glue and guardrails

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — I wanted my own MCP server inside ChatGPT and found that the capability exists but the public docs barely do; every attempt cost half a day of rediscovery. So I wrote down the path that works (Remote MCP → OAuth 2.1 → Cloudflare Tunnel → a real tool-call check) as an Agent Skill, so Claude Code and Codex start from a fixed point next time.  
`Agent Skill` · `MCP` · `OAuth 2.1` · `Cloudflare`

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — The moment the proxy dies, Claude Desktop starts connecting directly over your home IP; I watched it try 25 times in 12 seconds in my own firewall log. This is a set of Windows Firewall rules scoped to physical NICs, so in that moment Claude simply drops instead of quietly leaking. It also survives the rule breakage that MSIX updates cause, and ships a verification script that A/B-tests against a harmless domestic IP. The README walks through six fixes that look right and don't work.  
`PowerShell` · `Windows Firewall` · `MSIX` · `Networking`

### Video, visuals, and Agent Skills

**[Create Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — I wanted to take a one-line idea to a finished 4K video without a 3D team. This Skill walks an agent through the whole pipeline (style lock, storyboard, AI reference images, Blender scenes, crash-recoverable rendering, Resolve editing) and won't call it delivered until frame count, encoding, color labels and SHA-256 all check out.  
`Agent Skill` · `Blender` · `DaVinci Resolve` · `Video Pipeline`

**[AI Application Showcase Video](https://github.com/yoruuuchan/ai-application-showcase-video)** — Publicity for AI projects usually starts as scattered slides, technical notes, meeting minutes and unverified claims. This Skill makes an agent establish a factual baseline before it writes a word of promotion: fact sheet, missing-information list, 60-second script, storyboard, shooting checklist, post brief, platform copy. Every unverified efficiency claim gets marked "pending confirmation."  
`Agent Skill` · `Content Workflow` · `Validation`

**[Visual Skill Library](https://github.com/yoruuuchan/visual-skill-library)** — I keep collecting AI skills, workflows and design systems with a real visual identity, and a bookmarks folder is where those go to die. So this is an index instead: every entry carries its source, its license and how faithful it is to the original. Collect first, sort later; whatever I've actually used and verified in a task floats to the top.  
`Visual AI` · `Editorial` · `Data Visualization` · `Design Systems`

## Open-source contributions

Fixes sent upstream to tools I use every day.

- **[OpenCLI](https://github.com/jackwener/OpenCLI)** · turn any website into a CLI for AI agents — [#2281](https://github.com/jackwener/OpenCLI/pull/2281) Codex adapter: prefer the main renderer over the avatar-overlay CDP target and track the latest assistant message, with regression tests · *open*
- **[Operit](https://github.com/AAswordman/Operit)** · AI agent app for Android — [#974](https://github.com/AAswordman/Operit/pull/974) Fix a fling crash in the code editor on HONOR ROMs (`OverScroller` was stepped off the main thread and hit a `Choreographer` call that requires a Looper) · *merged*
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** · Agent Skill for Kimi Slides — [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6) Auto-start a debug Chrome on Windows so exports still work when agent-browser cannot launch one · *merged* · [#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5) Fix a `FileNotFoundError` race when Chrome renames a download mid-scan · *merged*

---

## How I work

A few habits. After the tests pass I go and look on real hardware, which is why Akari Pulse's README lists the exact phone model, watch firmware and verification date, and the Kill-Switch verification script won't give a verdict without an A/B baseline. I like fail-closed designs; one clear error is far easier to deal with than a system that quietly degrades and still shows green. Data I can keep myself (health, creative records, notebooks) lives on my own machine or my own VPS, so when something goes wrong I know where to look and who can see it.

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

📮 [yoruandakari@duck.com](mailto:yoruandakari@duck.com) · [1587761204@qq.com](mailto:1587761204@qq.com)  
Happy to talk about AI products, agent tooling, creator workflows — or anything on this page.

---

<div align="center">

### Build weird things. Make them real.

</div>
