# yoru

*[中文版](README.zh-CN.md)*

Started with cameras, drones, and DaVinci Resolve. Now I build tools — mostly for the gap between AI demos and the real world: phones, watches, Windows, video pipelines. Built with AI; the part I care about is what survives outside the editor.

---

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — Content studio for one. $5/month VPS, AI agents over MCP, append-only write.

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — Reverse-engineered health data off a vivo WATCH GT. The official path won't export it, so: watch RPK → phone APK → own database → MCP.

**[LyricLens](https://github.com/yoruuuchan/LyricLens)** — Song lyrics → flashcards, synced to playback. NetEase plugin + [standalone desktop app](https://github.com/yoruuuchan/lyriclens-desktop) in Tauri/Rust.

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — "Is it just me?" One page. Status + reachability probes on Cloudflare. [Live](https://is-ai-down.yoru-and-akari.dev).

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — Getting an MCP server into ChatGPT is real but barely documented. This is the path that actually works.

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — Caught it connecting directly 25 times in 12 seconds when the proxy dropped. Fail-closed firewall rules. The README walks through six "fixes" that look correct and aren't.

### motion & video

**[Motion System](https://github.com/yoruuuchan/yoru-motion-system)** — 18 Remotion templates from [636 manually curated references](https://github.com/yoruuuchan/yoru-motion-research). Timing measured from renders, not vibes.

**[Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — Agent Skill: one idea → 4K H.265 through Blender + Resolve. Not shipped until frame count, encoding, and checksum pass.

**[Showcase Video](https://github.com/yoruuuchan/ai-application-showcase-video)** — Agent Skill: project materials → video plan. Every unverified claim flagged before a word of promo is written.

### upstream

- **[Operit](https://github.com/AAswordman/Operit)** — Android AI agent · [8 merged PRs](https://github.com/AAswordman/Operit/pulls?q=is%3Apr+author%3Ayoruuuchan+is%3Amerged): Compose timing, model integration, tool APIs, crash handling
- **[OpenCLI](https://github.com/jackwener/OpenCLI)** — Codex Desktop CDP adapter ([#2281](https://github.com/jackwener/OpenCLI/pull/2281))
- **[open-kimi-ppt-skill](https://github.com/Binaryify/open-kimi-ppt-skill)** — browser launch + download race ([#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5), [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6))

---

yoruandakari@duck.com
