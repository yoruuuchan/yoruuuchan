# yoru

*[中文版](README.zh-CN.md)*

Started with cameras, drones, and DaVinci Resolve. Now I build AI products, agent infrastructure, and tools that have to survive contact with real devices and real workflows: phones, watches, Windows, creator pipelines. I care less about demos than whether the thing still works after deployment, user input, and edge cases.

---

### selected work

**[芦苇 (Reed)](https://github.com/yoruuuchan/wechat-md-studio)** — A typesetting workbench where a person and an AI work on the same WeChat article. 227 themes over one semantic AST, 3 written here and 224 ported with author and license kept. Markdown stays the only source; AI drafts through MCP without owning the document. [Live](https://wechat.yoru-and-akari.dev).

**[Claude Desktop Kill-Switch](https://github.com/yoruuuchan/claude-desktop-killswitch)** — Caught Claude Desktop connecting directly 25 times in 12 seconds when the proxy dropped. Fail-closed firewall rules, plus the six "fixes" that looked right and weren't.

**[Akari Pulse](https://github.com/yoruuuchan/akari-pulse)** — Reverse-engineered health data off a vivo WATCH GT. The official path won't export it, so: watch RPK → phone APK → own database → MCP.

**[Listening Bridge](https://github.com/yoruuuchan/listening-bridge)** — Gives an AI fresh listening context from Android or Windows: active track, synced-lyrics context, and explicit playback controls over MCP.

**[Yoru Studio](https://github.com/yoruuuchan/yoru-studio-oss)** — A self-hosted execution studio for solo creators: projects, storyboards, field work, retrospectives, backups, and MCP-connected AI agents.

**[is-ai-down](https://github.com/yoruuuchan/is-ai-down)** — "Is it just me?" One page. Status + reachability probes on Cloudflare. [Live](https://is-ai-down.yoru-and-akari.dev).

**[chatgpt-mcp-connect](https://github.com/yoruuuchan/chatgpt-mcp-connect)** — Verified ways to get custom MCP servers into ChatGPT, including direct servers and runtime/aggregation setups.

### creative systems

**[Yoru Design Systems](https://github.com/yoruuuchan/yoru-design-systems)** — Nine self-contained design systems, each one an installable Agent Skill: design guide, CSS tokens, components, and specimen cards for web, video, slides, and long-form content.

**[Blender Story Video](https://github.com/yoruuuchan/create-blender-story-video)** — Agent Skill: one idea → 4K H.265 through Blender + Resolve, with delivery checks for frame count, encoding, and checksum.

### open source

39 merged pull requests outside my own repositories, in 7 projects.

- **[Operit](https://github.com/AAswordman/Operit)** — Android AI agent · [21 merged PRs](https://github.com/AAswordman/Operit/pulls?q=is%3Apr+author%3Ayoruuuchan+is%3Amerged): model/provider integration, tool-call and history correctness, Compose/DSL state & timing, crash and UX fixes
- **[cli2api](https://github.com/caigee-cmd/cli2api)** — multi-account API proxy for coding CLIs · [10 merged PRs](https://github.com/caigee-cmd/cli2api/pulls?q=is%3Apr+author%3Ayoruuuchan+is%3Amerged): provider adapters (including an experimental Huawei Cloud CodeArts one), earliest-expiry-first account scheduling, model catalog persistence, tool-name preservation on streamed tool calls
- **Smaller ones** — gzh-design-skill (WeChat clipboard serialization), open-kimi-ppt-skill (browser launch and download races, [#5](https://github.com/Binaryify/open-kimi-ppt-skill/pull/5) [#6](https://github.com/Binaryify/open-kimi-ppt-skill/pull/6)), awesome-ai-companion, H440-FPV frame

---

yoruandakari@duck.com
