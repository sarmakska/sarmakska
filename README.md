<!--
  sarmakska/sarmakska
  https://github.com/sarmakska
  https://sarmalinux.com
-->

<div align="center">

<a href="https://sarmalinux.com">
<img src="https://capsule-render.vercel.app/api?type=soft&color=0:0a0a14,40:0d2e4f,75:0891b2,100:22d3ee&height=180&section=header&text=sarmalinux&fontSize=92&fontColor=ffffff&fontAlignY=55&animation=fadeIn" width="100%" alt="sarmalinux"/>
</a>

<a href="https://sarmalinux.com">
<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=22&duration=2200&pause=650&color=22D3EE&background=00000000&center=true&vCenter=true&width=780&height=60&lines=Senior+software+engineer+%C2%B7+UK+PAYE+only;Nineteen+open-source+projects+%C2%B7+all+MIT;slipstream+v1.0+%C2%B7+~95%25+per-read+savings;Sarmalink-AI+%C2%B7+36-engine+failover;echo+%C2%B7+open+Jarvis+%C2%B7+1+July+2026;Eighty-seven+long-form+engineering+essays" alt="What I do"/>
</a>

<br/>

<a href="https://sarmalinux.com"><img src="https://img.shields.io/badge/sarmalinux.com-0a0a14?style=for-the-badge&logo=safari&logoColor=22d3ee&labelColor=0a0a14" alt="Website"/></a>
<a href="https://sarmalinux.com/hire-me"><img src="https://img.shields.io/badge/Hire%20me-permanent%20UK%20PAYE-22c55e?style=for-the-badge&logo=briefcase&logoColor=white" alt="Hire me"/></a>
<a href="https://sarmalinux.com/blog"><img src="https://img.shields.io/badge/Engineering%20essays-87%2B-8b5cf6?style=for-the-badge&logo=substack&logoColor=white" alt="Essays"/></a>
<a href="https://sarmalinux.com/charity"><img src="https://img.shields.io/badge/Local%20charity%20offer-free%20websites-ef4444?style=for-the-badge&logo=heart&logoColor=white" alt="Charity"/></a>
<a href="https://www.linkedin.com/in/sarmalinux"><img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white" alt="LinkedIn"/></a>

<br/>

<img src="https://komarev.com/ghpvc/?username=sarmakska&label=Profile%20views&color=22d3ee&style=for-the-badge" alt="Profile views"/>
<img src="https://img.shields.io/github/followers/sarmakska?logo=github&label=Followers&style=for-the-badge&color=34d399&labelColor=0d1117" alt="Followers"/>
<img src="https://img.shields.io/github/stars/sarmakska?affiliations=OWNER&style=for-the-badge&color=a78bfa&logo=star&logoColor=white&labelColor=0d1117" alt="Stars"/>
<img src="https://img.shields.io/badge/UK-PAYE%20only-22c55e?style=for-the-badge&logo=unitedkingdom&logoColor=white&labelColor=0d1117" alt="UK PAYE only"/>

</div>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=12,19,20,2,5,6&height=2&width=100%" alt="separator"/>

</div>

<br/>

<!-- ============================================================== -->
<!-- ==================== SARMALINK-AI ============================ -->
<!-- ============================================================== -->

<div align="center">

<a href="https://github.com/sarmakska/Sarmalink-ai">
<img src="https://capsule-render.vercel.app/api?type=soft&color=0:0a0a14,30:0d2e4f,55:0891b2,80:f97316,100:fbbf24&height=200&section=header&text=Sarmalink-AI&fontSize=78&fontColor=ffffff&fontAlignY=44&desc=multi-provider%20gateway%20%C2%B7%2036%20engines%20%C2%B7%207%20providers%20%C2%B7%20%3C50ms&descSize=18&descAlignY=78&animation=fadeIn" width="100%" alt="Sarmalink-AI, multi-provider gateway, 36 engines, 7 providers, under 50ms"/>
</a>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=20&duration=2000&pause=550&color=F97316&background=00000000&center=true&vCenter=true&width=780&height=58&lines=POST+%2Fapi%2Fv1%2Fchat%2Fcompletions+%C2%B7+OpenAI-compatible;Primary+returns+429+%E2%87%92+next+engine+fires+%3C+50ms;Intent+auto-router+%C2%B7+MCP-shape+tool+catalog;Persistent+memory+%C2%B7+FLUX+image+gen+%C2%B7+TTS+%2B+STT;36+engines+%E2%87%92+composite+uptime+99.9999%25" alt="Sarmalink-AI live ticker"/>

<br/>

### **Sarmalink-AI** &middot; *one endpoint, thirty-six engines, zero surprise bills*

</div>

<div align="center">

**Drop-in OpenAI-compatible gateway.** Every request fans across 36 engines from 7 providers. When the primary returns 429 or 5xx, the next engine fires in **under 50 milliseconds**. Round-robin key rotation, six specialised modes (Smart, Reasoner, Live, Fast, Coder, Vision), an MCP-shape tool catalog, persistent user memory, FLUX image generation with key rotation, plus TTS / STT cascades. Built so an internal AI product never sees an outage the way a single-provider wrapper does.

<br/>

#### How a request flows

</div>

```mermaid
%%{init: {'theme':'dark','themeVariables':{'primaryColor':'#0d2e4f','primaryTextColor':'#e6f5ff','lineColor':'#22d3ee','primaryBorderColor':'#22d3ee','actorBkg':'#1e3a5f','actorBorder':'#22d3ee','actorTextColor':'#ffffff'}}}%%
sequenceDiagram
    autonumber
    participant Client
    participant Router as Intent Router
    participant PA as Primary Engine
    participant PB as Failover Engine
    participant Mem as Memory + Tools
    Client->>Router: POST /api/v1/chat
    Router->>Router: classify intent (Smart / Live / Coder / ...)
    Router->>PA: dispatch primary
    PA-->>Router: 429 Too Many Requests
    Note over Router,PB: handoff in under 50ms
    Router->>PB: retry on next engine
    PB->>Mem: recall facts + tools
    Mem-->>PB: context window
    PB-->>Router: 200 streaming
    Router-->>Client: SSE first token ~120ms
```

<br/>

<div align="center">

#### Seven providers, thirty-six engines, six modes

<table align="center">
<tr>
<td align="center" width="14%"><img src="https://img.shields.io/badge/Groq-LPU-f97316?style=for-the-badge&logoColor=white" alt="Groq"/><br/><sub><b>5 engines</b><br/>GPT-OSS 120B + 20B</sub></td>
<td align="center" width="14%"><img src="https://img.shields.io/badge/SambaNova-RDU-8b5cf6?style=for-the-badge&logoColor=white" alt="SambaNova"/><br/><sub><b>4 engines</b><br/>DeepSeek V3.2</sub></td>
<td align="center" width="14%"><img src="https://img.shields.io/badge/Cerebras-WSE--3-06b6d4?style=for-the-badge&logoColor=white" alt="Cerebras"/><br/><sub><b>3 engines</b><br/>Qwen 3 235B</sub></td>
<td align="center" width="14%"><img src="https://img.shields.io/badge/Gemini-Search-4285f4?style=for-the-badge&logo=googlegemini&logoColor=white" alt="Gemini"/><br/><sub><b>4 engines</b><br/>2.5 Flash + 3</sub></td>
<td align="center" width="14%"><img src="https://img.shields.io/badge/OpenRouter-pool-10b981?style=for-the-badge&logoColor=white" alt="OpenRouter"/><br/><sub><b>17 engines</b><br/>Nemotron + GLM</sub></td>
<td align="center" width="14%"><img src="https://img.shields.io/badge/Cloudflare-FLUX-f59e0b?style=for-the-badge&logo=cloudflare&logoColor=white" alt="Cloudflare"/><br/><sub><b>images</b><br/>klein 9B + 4B</sub></td>
<td align="center" width="14%"><img src="https://img.shields.io/badge/Tavily-tools-ef4444?style=for-the-badge&logoColor=white" alt="Tavily"/><br/><sub><b>live</b><br/>weather + FX</sub></td>
</tr>
</table>

<br/>

<a href="https://github.com/sarmakska/Sarmalink-ai"><img src="https://img.shields.io/badge/36-engines-22d3ee?style=flat-square&labelColor=0d1117" alt="36 engines"/></a>
<a href="https://github.com/sarmakska/Sarmalink-ai"><img src="https://img.shields.io/badge/7-providers-f97316?style=flat-square&labelColor=0d1117" alt="7 providers"/></a>
<a href="https://github.com/sarmakska/Sarmalink-ai"><img src="https://img.shields.io/badge/%3C50ms-failover-22c55e?style=flat-square&labelColor=0d1117" alt="<50ms failover"/></a>
<a href="https://github.com/sarmakska/Sarmalink-ai"><img src="https://img.shields.io/badge/MIT-license-60a5fa?style=flat-square&logo=opensourceinitiative&logoColor=white&labelColor=0d1117" alt="MIT"/></a>
<a href="https://github.com/sarmakska/Sarmalink-ai/wiki"><img src="https://img.shields.io/badge/wiki-Setup%20Guide-fbbf24?style=flat-square&logo=readthedocs&logoColor=white&labelColor=0d1117" alt="wiki"/></a>

<br/><br/>

<a href="https://sarmalinux.com/products/sarmalink-ai"><img src="https://img.shields.io/badge/Long%20plan%20%2B%20whitepaper%20→-sarmalinux.com%2Fproducts%2Fsarmalink--ai-0d1117?style=for-the-badge&logo=safari&logoColor=22d3ee" alt="Read the long plan"/></a>
<a href="https://github.com/sarmakska/Sarmalink-ai"><img src="https://img.shields.io/badge/Clone%20%2B%20deploy%20→-15%20minutes%20to%20your%20own%20gateway-0d1117?style=for-the-badge&logo=github&logoColor=22d3ee" alt="Clone and deploy"/></a>

</div>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=20,17,12&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== SLIPSTREAM =============================== -->
<!-- ============================================================== -->

<br/>

<div align="center">

<a href="https://github.com/sarmakska/slipstream">
<img src="https://capsule-render.vercel.app/api?type=soft&color=0:0a0a14,30:064e3b,55:047857,80:34d399,100:6ee7b7&height=200&section=header&text=slipstream+v1.0&fontSize=70&fontColor=ffffff&fontAlignY=44&desc=cross-IDE+MCP+toolkit+%C2%B7+~95%25+per-read+savings&descSize=18&descAlignY=78&animation=fadeIn" width="100%" alt="slipstream v1.0, cross-IDE MCP toolkit, 95% per-read savings"/>
</a>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=20&duration=2000&pause=550&color=34D399&background=00000000&center=true&vCenter=true&width=780&height=58&lines=14+sp_*+tools+%C2%B7+scoped+symbol+pulls;React+%2B+Vite+%2B+d3+dashboard+%C2%B7+nine+views;Cross-tab+agent+bus+%C2%B7+turn-boundary+sync;75-skill+methodology+library;321+tests+%C2%B7+six+editor+install+paths" alt="slipstream live ticker"/>

```
$  cp | ctx 12%* ok | mem 4 | obs 37 | opt 71% | skill scoped-read    (~12 steps)
```

### **slipstream** &middot; *Claude Code plugin + cross-IDE MCP toolkit*

</div>

<div align="center">

**First major release.** Fourteen `sp_*` tools replace whole-file reads with scoped symbol pulls, reproducible **~95% per-read savings** via `pnpm benchmark`. A React + Vite + d3 dashboard with nine routed views including an interactive code dependency graph. A cross-tab agent bus that lets multiple Claude Code tabs on one project coordinate at turn boundaries. A cold-start knowledge feed on every SessionStart so no session begins blank. Dollar cost of tokens saved, downloadable session reports, a memory doctor, the insights band, the project knowledge brief, and a 75-skill methodology library.

**Six editor install paths &middot; 321 tests &middot; MIT**

<br/>

<a href="https://github.com/sarmakska/slipstream/releases/tag/v1.0.0"><img src="https://img.shields.io/badge/v1.0.0-shipped-34d399?style=flat-square&logo=npm&logoColor=white&labelColor=0d1117" alt="v1.0.0"/></a>
<a href="https://github.com/sarmakska/slipstream/actions"><img src="https://img.shields.io/badge/321-tests-22d3ee?style=flat-square&logo=vitest&logoColor=white&labelColor=0d1117" alt="321 tests"/></a>
<a href="https://github.com/sarmakska/slipstream"><img src="https://img.shields.io/badge/14-sp_*%20tools-8b5cf6?style=flat-square&labelColor=0d1117" alt="14 sp tools"/></a>
<a href="https://github.com/sarmakska/slipstream"><img src="https://img.shields.io/badge/75-skills-f59e0b?style=flat-square&logo=book&logoColor=white&labelColor=0d1117" alt="75 skills"/></a>
<a href="https://github.com/sarmakska/slipstream"><img src="https://img.shields.io/badge/MIT-license-60a5fa?style=flat-square&logo=opensourceinitiative&logoColor=white&labelColor=0d1117" alt="MIT"/></a>
<a href="https://github.com/sarmakska/slipstream/blob/main/CHANGELOG.md"><img src="https://img.shields.io/badge/changelog-v1.0.0-a78bfa?style=flat-square&logo=git&logoColor=white&labelColor=0d1117" alt="changelog"/></a>
<a href="https://github.com/sarmakska/slipstream/wiki"><img src="https://img.shields.io/badge/wiki-29%20pages-fbbf24?style=flat-square&logo=readthedocs&logoColor=white&labelColor=0d1117" alt="wiki"/></a>

<br/><br/>

<a href="https://sarmalinux.com/products/slipstream"><img src="https://img.shields.io/badge/Long%20plan%20%2B%20whitepaper%20→-sarmalinux.com%2Fproducts%2Fslipstream-0d1117?style=for-the-badge&logo=safari&logoColor=34d399" alt="Read the long plan"/></a>
<a href="https://sarmalinux.com/products/slipstream/setup"><img src="https://img.shields.io/badge/Install%20in%20six%20editors%20→-Claude%20%C2%B7%20Cursor%20%C2%B7%20Windsurf%20%C2%B7%20Antigravity%20%C2%B7%20VS%20Code%20%C2%B7%20JetBrains-0d1117?style=for-the-badge&logo=visualstudiocode&logoColor=22d3ee" alt="Install in six editors"/></a>

</div>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=2,6,5&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== ECHO ===================================== -->
<!-- ============================================================== -->

<br/>

<div align="center">

<a href="https://github.com/sarmakska/echo">
<img src="https://capsule-render.vercel.app/api?type=soft&color=0:0a0a14,30:3b0764,55:7e22ce,80:a78bfa,100:e9d5ff&height=200&section=header&text=echo&fontSize=86&fontColor=ffffff&fontAlignY=44&desc=open%20Jarvis%20%C2%B7%20brain-agnostic%20%C2%B7%20one%20Rust%20core%20%C2%B7%201%20July%202026&descSize=18&descAlignY=78&animation=fadeIn" width="100%" alt="echo, open Jarvis, brain-agnostic, one Rust core, 1 July 2026"/>
</a>

<img src="https://readme-typing-svg.demolab.com?font=JetBrains+Mono&weight=700&size=20&duration=2200&pause=600&color=A78BFA&background=00000000&center=true&vCenter=true&width=780&height=58&lines=Bring-your-own-subscription+%C2%B7+claude+%2F+codex+%2F+gemini;Voice+in.+Voice+out.+Vision.+Memory.;Translucent+multi-monitor+HUD+%C2%B7+one+Rust+core;Foundation+%2B+orchestration+in+%C2%B7+64+tests+green;Real+audio+I%2FO+%2B+setup+wizard+next" alt="echo live ticker"/>

<br/>

### **echo** &middot; *the open Jarvis you actually own*

</div>

<div align="center">

**Bring-your-own-subscription.** Echo never asks for an API key. It dispatches each prompt to whichever subscription-backed CLI you already pay for, `claude`, `codex` or `gemini`, picked by a router that scores capability, quota remaining and freshness. Voice in. Voice out. Vision when it helps. Memory across years. Translucent multi-monitor HUD planned. Cross-platform from one Rust core. MIT. Local-first.

**Where it is now:** Foundation + the orchestration layer are in and tested, **64 tests green**. The brain router across `claude`/`codex`/`gemini` is wired and proven against a fake CLI; the file-based memory store with PreSession digests is live; an MCP skills bus runs weather / web search / files; the voice traits are defined and the macOS TTS adapter is real.

**What is still landing:** real Porcupine wake word, real cpal mic capture, real whisper.cpp speech-to-text, real Piper TTS as the cross-platform default, the wired end-to-end voice loop, the setup wizard, sqlite-vss vector memory.

**Then:** HUD polish + multi-monitor, calendar + mail over one-click OAuth, the senses, a proactive engine, autonomous workflows, signed installers.

<br/>

<a href="https://github.com/sarmakska/echo"><img src="https://img.shields.io/badge/coming-1%20July%202026-a78bfa?style=for-the-badge&logo=clockify&logoColor=white" alt="coming 1 July 2026"/></a>
<a href="https://github.com/sarmakska/echo"><img src="https://img.shields.io/badge/Phase%200%20%2B%201-foundation%20in%20%C2%B7%2064%20tests-22d3ee?style=for-the-badge&logo=rust&logoColor=white" alt="Phase 0 + 1 foundation in, 64 tests"/></a>
<a href="https://github.com/sarmakska/echo"><img src="https://img.shields.io/badge/phases-landing%20daily-0a84ff?style=for-the-badge&logo=git&logoColor=white" alt="phases landing daily"/></a>
<a href="https://sarmalinux.com/products/echo"><img src="https://img.shields.io/badge/Long%20plan%20→-sarmalinux.com%2Fproducts%2Fecho-a78bfa?style=for-the-badge&logo=safari&logoColor=white" alt="Long plan"/></a>

</div>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=12,19,20&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== ABOUT ==================================== -->
<!-- ============================================================== -->

<br/>

<div align="center">

### About me

</div>

<div align="center">

I am Sarma. I build open-source software from a desk in the UK.

LLM infrastructure, coding agents, inference servers, storage engines, consensus protocols, WebAssembly sandboxes, platform tools. Every project lives on GitHub with a whitepaper, an architecture diagram and a quick-start guide on **[sarmalinux.com/products](https://sarmalinux.com/products)**.

What pulls me back to the desk every weekend is the same thing that pulled me into the industry: the quiet thrill of building something from scratch. A blank repository, a problem worth solving, a system that did not exist yesterday and ships today.

When I am not at the desk, I write long-form essays about what I am learning, contribute to the open-source projects I rely on, and run a small weekend charity where I build free websites for local businesses in Hemel Hempstead.

</div>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=12,19,20&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== RECENT SHIPS ============================= -->
<!-- ============================================================== -->

<br/>

<div align="center">

### Recent ships

</div>

| Date | What |
|---|---|
| **8 Jun 2026** | [echo](https://github.com/sarmakska/echo) Phase 0 + brain-router scaffolding in: `Brain` trait + Claude/Codex/Gemini subprocess wrappers, capability-and-quota router, file-based memory with PreSession digests, MCP skills bus with weather/web-search/files, voice traits + macOS TTS. 64 tests green. Real wake word, mic, whisper.cpp and Piper are next. v1.0 still aimed at 1 July 2026. |
| **6 Jun 2026** | [slipstream v1.0.0](https://github.com/sarmakska/slipstream/releases/tag/v1.0.0): first major release. React dashboard with nine views, interactive code graph, cross-tab agent bus, cold-start knowledge feed, reproducible `pnpm benchmark` hitting ~95% per-read, dollar cost of tokens saved, memory doctor, 75-skill library, 321 tests. |
| **6 Jun 2026** | [slipstream v0.27.0](https://github.com/sarmakska/slipstream/releases/tag/v0.27.0): production React dashboard (Vite + TypeScript + d3) with grouped sidebar (Now / History / Knowledge), typed JSON client and interactive knowledge graph. |
| **6 Jun 2026** | [slipstream v0.24.0](https://github.com/sarmakska/slipstream/releases/tag/v0.24.0): reproducible token-savings benchmark. `pnpm benchmark` measures whole-file vs scoped reads on real files and prints a Markdown table. |
| **6 Jun 2026** | [slipstream v0.8.0](https://github.com/sarmakska/slipstream/releases/tag/v0.8.0): dashboard insights band. Every data tab opens with a natural-language paragraph plus bullets, deterministic templates, zero LLM. |
| **4 Jun 2026** | [slipstream v0.7.0](https://github.com/sarmakska/slipstream/releases/tag/v0.7.0): tabbed dashboard (Live, Project, Journal, Sessions, Memory) with 365-day heatmap, file leaderboard, kinds donut, distilled lessons. |
| **4 Jun 2026** | [slipstream v0.6.0](https://github.com/sarmakska/slipstream/releases/tag/v0.6.0): cross-IDE parity (`sp_digest` + `sp_resume` + auto-mode-detect + `slipstream-setup`), nine backend features, redesigned glass-on-dark dashboard. |
| **3 Jun 2026** | [NVIDIA Computex 2026 recap](https://sarmalinux.com/blog/nvidia-computex-2026-what-ai-engineers-need-to-know): Vera Rubin NVL72 in production, RTX Spark, Cosmos 3, Nemotron 3 Ultra. |
| **1 Jun 2026** | [AI Engineer World's Fair 2026 recap](https://sarmalinux.com/blog/ai-engineer-worlds-fair-2026-what-mattered): MCP took the year. Six themes that defined where AI engineering is going. |
| **31 May 2026** | [echo](https://github.com/sarmakska/echo) repo opened, public launch scheduled 1 July 2026. |
| **3 May 2026** | [Sarmalink-AI v2](https://github.com/sarmakska/Sarmalink-ai): intent auto-routing, MCP-shape tool catalog, TTS/STT cascades, image generation rotation. |

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=20,17,12&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== PORTFOLIO ================================ -->
<!-- ============================================================== -->

<br/>

<div align="center">

### The portfolio &middot; nineteen MIT-licensed projects

</div>

<table align="center">
<tr>
<td width="50%" valign="top">

#### Flagships
- **[Sarmalink-ai](https://github.com/sarmakska/Sarmalink-ai)** &middot; Multi-provider OpenAI-compatible AI gateway with 36-engine failover across 7 providers, intent-based plugin auto-routing, MCP-shape tool catalog and Manus webhook persistence.
- **[slipstream](https://github.com/sarmakska/slipstream)** &middot; v1.0 shipped. Claude Code plugin and cross-IDE MCP toolkit. Fourteen `sp_*` tools, self-building memory, lossless compaction, React dashboard with nine views and an interactive code dependency graph, cross-tab agent bus, cold-start knowledge feed, 75-skill methodology library. 321 tests, MIT.

#### Coming next
- **[echo](https://github.com/sarmakska/echo)** &middot; An open Jarvis. Brain-agnostic across Claude Code, Codex CLI, Gemini CLI, Ollama and LM Studio. Translucent multi-monitor HUD planned. Phase 0 + Phase 1 orchestration scaffolding in, 64 tests; real audio I/O and the setup wizard ship next. Public v1.0 on 1 July 2026.

#### AI infrastructure
- **[agent-orchestrator](https://github.com/sarmakska/agent-orchestrator)** &middot; Durable multi-agent workflows in TypeScript, deterministic replay, journaled Postgres state, BullMQ step queue, Inspector UI.
- **[voice-agent-starter](https://github.com/sarmakska/voice-agent-starter)** &middot; Sub-second full-duplex WebRTC voice loop, mediasoup SFU, Fastify model worker, pluggable STT, LLM, TTS adapters.
- **[ai-eval-runner](https://github.com/sarmakska/ai-eval-runner)** &middot; Evals as code. Python 3.12, Typer CLI, DuckDB store, FastAPI + HTMX viewer.
- **[forge-infer](https://github.com/sarmakska/forge-infer)** &middot; Minimal LLM inference server in Rust with paged KV-cache, continuous batching and speculative decoding.

#### MCP and AI applications
- **[mcp-server-toolkit](https://github.com/sarmakska/mcp-server-toolkit)** &middot; Production Model Context Protocol server starter in Python and FastAPI.
- **[local-llm-router](https://github.com/sarmakska/local-llm-router)** &middot; OpenAI-compatible proxy routing between Ollama and cloud LLMs by policy.
- **[rag-over-pdf](https://github.com/sarmakska/rag-over-pdf)** &middot; A minimal, production-shaped RAG starter with cited streaming answers.
- **[receipt-scanner](https://github.com/sarmakska/receipt-scanner)** &middot; Vision OCR receipts to Zod-validated JSON.

</td>
<td width="50%" valign="top">

#### Systems software
- **[lsmdb](https://github.com/sarmakska/lsmdb)** &middot; Log-structured merge-tree storage engine in Go. WAL, SSTables, bloom filters, MVCC snapshots.
- **[raftkv](https://github.com/sarmakska/raftkv)** &middot; Raft KV store in Go with a fault-injection harness proving linearizability under partitions.
- **[sandboxd](https://github.com/sarmakska/sandboxd)** &middot; WebAssembly sandbox in Rust with a deny-by-default host ABI and strict CPU, wall-clock and memory bounds.

#### Platform engineering
- **[terraform-stack](https://github.com/sarmakska/terraform-stack)** &middot; Vercel, Supabase, Cloudflare and DigitalOcean modules in one Terraform repo.
- **[k8s-ops-toolkit](https://github.com/sarmakska/k8s-ops-toolkit)** &middot; Helm chart for shipping Next.js to Kubernetes with full observability pre-wired.
- **[shipyard](https://github.com/sarmakska/shipyard)** &middot; Multi-tenant SaaS scaffold in TypeScript. Tenant isolation, RBAC, billing, audit log, rate limits.

#### Tools
- **[webhook-to-email](https://github.com/sarmakska/webhook-to-email)** &middot; Webhook receiver that forwards events to email via Resend.
- **[staff-portal](https://github.com/sarmakska/staff-portal)** &middot; Open-source HR and ops portal. Leave, attendance, expenses, kiosk mode.

</td>
</tr>
</table>

<div align="center">

> Every repo has a bespoke product trio on **[sarmalinux.com/products](https://sarmalinux.com/products)**: whitepaper, architecture diagram, quick-start. All MIT.

</div>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=2,6,5&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== STACK ==================================== -->
<!-- ============================================================== -->

<br/>

<div align="center">

### Stack

<img src="https://skillicons.dev/icons?i=ts,py,go,rust,nextjs,nodejs,fastapi,fastify,postgres,supabase,redis,docker&perline=12" alt="Languages and frameworks"/>

<br/>

<img src="https://skillicons.dev/icons?i=kubernetes,terraform,vercel,cloudflare,prometheus,grafana,githubactions,vscode,linux,bash,git,markdown&perline=12" alt="Infrastructure and tooling"/>

<br/><br/>

<img src="https://img.shields.io/badge/AI%20infrastructure-multi--provider%20gateways%20%C2%B7%20failover-22d3ee?style=flat-square" alt="AI infrastructure"/>
<img src="https://img.shields.io/badge/MCP-Model%20Context%20Protocol-06b6d4?style=flat-square" alt="MCP"/>
<img src="https://img.shields.io/badge/Agent%20orchestration-deterministic%20replay-8b5cf6?style=flat-square" alt="Agent orchestration"/>
<img src="https://img.shields.io/badge/Voice-WebRTC%20%C2%B7%20mediasoup%20%C2%B7%20sub--second-f59e0b?style=flat-square" alt="Voice"/>
<img src="https://img.shields.io/badge/RAG-HNSW%20%C2%B7%20cosine%20%C2%B7%20citations-10b981?style=flat-square" alt="RAG"/>
<img src="https://img.shields.io/badge/Inference-Rust%20%C2%B7%20paged%20KV%20%C2%B7%20speculative-f43f5e?style=flat-square" alt="Inference"/>
<img src="https://img.shields.io/badge/Storage-LSM%20%C2%B7%20WAL%20%C2%B7%20MVCC-3b82f6?style=flat-square" alt="Storage"/>
<img src="https://img.shields.io/badge/Consensus-Raft%20%C2%B7%20fault%20injection-a78bfa?style=flat-square" alt="Consensus"/>
<img src="https://img.shields.io/badge/Sandboxing-WebAssembly%20%C2%B7%20capability%20ABI-fb7185?style=flat-square" alt="Sandboxing"/>
<img src="https://img.shields.io/badge/Evals-LLM--as--judge%20%C2%B7%20regression-eab308?style=flat-square" alt="Evals"/>
<img src="https://img.shields.io/badge/Platform-Kubernetes%20%C2%B7%20Helm%20%C2%B7%20Terraform-22c55e?style=flat-square" alt="Platform"/>

The full eight-tier stack with every choice and why it earned a place lives at **[sarmalinux.com/technology](https://sarmalinux.com/technology)**. Boring tech, surgical complexity. No AWS, no Azure.

</div>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=12,19,20&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== STATS ==================================== -->
<!-- ============================================================== -->

<br/>

<div align="center">

### Stats

<a href="https://github.com/sarmakska">
<img height="180" src="https://github-readme-streak-stats.herokuapp.com/?user=sarmakska&hide_border=true&background=0d1117&stroke=22d3ee&ring=34d399&fire=ec4899&currStreakLabel=34d399&sideLabels=22d3ee&dates=c9d1d9&currStreakNum=c9d1d9&sideNums=c9d1d9" alt="Streak"/>
</a>

<br/><br/>

<a href="https://github.com/sarmakska?tab=repositories">
<img src="https://img.shields.io/badge/MIT%20open--source%20projects-19-22d3ee?style=for-the-badge&logo=github&logoColor=white&labelColor=0d1117" alt="19 OSS projects"/>
</a>
<a href="https://sarmalinux.com/blog">
<img src="https://img.shields.io/badge/Long--form%20essays-87-8b5cf6?style=for-the-badge&logo=substack&logoColor=white&labelColor=0d1117" alt="87 essays"/>
</a>
<img src="https://img.shields.io/github/stars/sarmakska?affiliations=OWNER&style=for-the-badge&color=a78bfa&logo=star&logoColor=white&labelColor=0d1117&label=Total%20stars" alt="Stars"/>
<img src="https://img.shields.io/github/followers/sarmakska?style=for-the-badge&color=34d399&logo=github&logoColor=white&labelColor=0d1117&label=Followers" alt="Followers"/>

<br/>

<a href="https://github.com/sarmakska">
<img src="https://github-readme-activity-graph.vercel.app/graph?username=sarmakska&theme=react-dark&hide_border=true&bg_color=0d1117&color=34d399&line=22d3ee&point=a78bfa&area=true&area_color=34d399" alt="Activity graph"/>
</a>


</div>

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=20,17,12&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== WRITING ================================== -->
<!-- ============================================================== -->

<br/>

<div align="center">

### Writing

</div>

A handful of good entry points into the **[eighty-seven long-form engineering essays](https://sarmalinux.com/blog)**:

- [NVIDIA Computex 2026, what AI engineers need to know](https://sarmalinux.com/blog/nvidia-computex-2026-what-ai-engineers-need-to-know), Vera Rubin NVL72, RTX Spark, Cosmos 3, Nemotron 3 Ultra
- [AI Engineer World's Fair 2026, what mattered](https://sarmalinux.com/blog/ai-engineer-worlds-fair-2026-what-mattered), six themes that defined the year
- [SarmaLink-AI failover deep dive](https://sarmalinux.com/blog/sarmalink-ai-failover-deep-dive), how multi-engine fallback actually works in production
- [Building Agent Orchestrator](https://sarmalinux.com/blog/building-agent-orchestrator), the journaled-Postgres pattern behind deterministic replay
- [Why I open-sourced 12 repos](https://sarmalinux.com/blog/why-i-open-sourced-12-repos), the reasoning, the trade-offs
- [Terraform Stack vs Pulumi vs SST](https://sarmalinux.com/blog/terraform-stack-vs-pulumi-vs-sst), an honest comparison
- [F1 2026 mid-season after the cancellation](https://sarmalinux.com/blog/f1-2026-mid-season-after-cancellation), because not everything is code

<br/>

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=rect&color=gradient&customColorList=12,19,20&height=2&width=100%" alt="separator"/>
</div>

<!-- ============================================================== -->
<!-- ==================== HIRING =================================== -->
<!-- ============================================================== -->

<br/>

<div align="center">

### Hiring

I am open to **permanent, full-time PAYE** software engineering roles across the United Kingdom. Remote, hybrid or on-site. Senior or mid-level individual contributor in **AI infrastructure**, **AI engineering**, **platform engineering**, **backend** or **full-stack development**. Not taking contract, consulting or agency subcontract work.

The full pitch with a capability matrix, recent ships and selected open-source work lives at **[sarmalinux.com/hire-me](https://sarmalinux.com/hire-me)**.

<br/>

<a href="https://sarmalinux.com/hire-me"><img src="https://img.shields.io/badge/Read%20the%20full%20pitch-sarmalinux.com%2Fhire--me-22c55e?style=for-the-badge&logo=briefcase&logoColor=white" alt="Read the full pitch"/></a>
<a href="mailto:projects@sarmalinux.com?subject=Role%20enquiry%2C%20Sarma"><img src="https://img.shields.io/badge/projects%40sarmalinux.com-EA4335?style=for-the-badge&logo=gmail&logoColor=white" alt="Email"/></a>

</div>

<br/>

<div align="center">

<img src="https://capsule-render.vercel.app/api?type=waving&color=0:34d399,25:22d3ee,50:0891b2,75:7e22ce,100:0a0a14&height=160&section=footer&animation=fadeIn" width="100%" alt="footer"/>

<sub>Built by <a href="https://sarmalinux.com">sarmalinux</a> &middot; UK &middot; All projects MIT licensed &middot; Updated daily</sub>

</div>
