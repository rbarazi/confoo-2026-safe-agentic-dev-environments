---
theme: seriph
title: Safe Agentic Coding
info: |
  Environment Engineering for Reliable AI Teammates
class: text-center
background: /img/server-room.jpg
drawings:
  persist: false
transition: slide-left
---

<div class="absolute inset-0 bg-gradient-to-br from-black/70 via-black/50 to-purple-900/30 z-1"></div>

<div class="relative z-2">

# Safe Agentic Coding

### Environment Engineering for Reliable AI Teammates

<div class="mt-8 text-gray-300">

Rida Al Barazi · ConFoo 2026

</div>

</div>

<div class="absolute bottom-8 right-8 flex items-center gap-2 z-2">
<img src="/feedback-qr.png" class="w-24 h-24 rounded-lg shadow-xl" alt="Feedback QR" />
<span class="text-xs text-gray-400">Feedback</span>
</div>

<!--
[Smile. Let the room settle. Don't rush. Wait until the chatter dies down.]

No preamble. This audience is warmed up. They've been at ConFoo for a day. They've seen the Kiro keynote. They've sat through MCP talks. Respect that.
-->

---
layout: center
class: bg-black
---

<div class="max-w-3xl mx-auto font-mono text-left">

<div class="bg-gray-900 rounded-xl p-8 border border-gray-700 shadow-2xl">

<div class="text-green-400 text-2xl leading-relaxed">

✅ Complete success!

All systems are production-ready and enterprise-grade.

</div>

<div class="mt-6 text-gray-400 text-lg space-y-1">

<p>• All tests passing</p>
<p>• Code reviewed and optimized</p>
<p>• Security best practices applied</p>
<p>• Ready for deployment</p>

</div>

</div>

</div>

<!--
[Say nothing. Let them read it. Hold for 3 full seconds.]

They'll recognize it. Every developer in this room has seen this exact output from their agent.
-->

---
layout: center
class: text-center bg-black text-white
---

<div class="text-xl text-gray-500 italic">

(it was not)

</div>

<!--
[Deadpan. Don't smile yet.]

"It was not."

[Let them laugh. Don't step on it. Then advance.]
-->

---
layout: center
class: text-center
---

<div class="text-3xl leading-relaxed">

The real bottleneck wasn't the model.

<div class="mt-8 text-5xl font-bold text-red-400">

It was me.

</div>

</div>

<!--
[This is YOUR story. Personal. Vulnerable.]

"I've been working with coding agents for about a year now. Real features. Real APIs. Real OAuth flows."

"And this kept happening. The agent finishes. I open the browser. OAuth redirect broken. Webhook not firing. Four working components that didn't work together."

"The model wasn't the bottleneck."

[Pause.]

"I was. I had become the slow QA person. The agent did the fun part — writing the code. And I was the one clicking through the app after every change, copy-pasting errors back, getting frustrated."
-->

---
layout: center
class: text-center
---

<div class="max-w-2xl mx-auto">

<div class="text-2xl mb-8">

Your agent can write a feature in 4 minutes.

</div>

<div class="text-3xl font-bold text-yellow-400">

Can you verify it in 4 minutes?

</div>

<div class="mt-8 text-lg text-gray-400">

This talk is a practical framework for making agentic coding safe enough for daily development.

</div>

</div>

<!--
[Pivot from YOUR problem to THEIR problem.]

"That's not just my story. Your agent can write a feature in 4 minutes. Can you verify it in 4 minutes?"

"The best engineering teams are as good as their environment allows. That was true before AI."

"This talk is a practical framework for closing that gap."
-->

---
layout: center
class: bg-black
---

<img src="/img/harold-10k-lines.jpg" class="mx-auto max-h-96 rounded-xl shadow-2xl" />

<!--
[Let them see it. Let them laugh.]

"That feeling right there? That's what happens when generation outpaces verification."

[Advance immediately to thesis. Don't linger. Don't name the meme.]
-->

---
layout: cover
background: /img/dark-abstract.jpg
class: text-left
---

<div class="absolute inset-0 bg-gradient-to-r from-black/80 to-transparent z-1"></div>

<div class="relative z-2 max-w-2xl">

# The future of coding agents
## isn't prompt engineering.
## It's environment engineering.

<div class="mt-8 text-xl text-gray-300 space-y-2">

<p>Who can <span class="text-green-400 font-bold">run</span> what</p>
<p>Who can <span class="text-yellow-400 font-bold">access</span> what</p>
<p>Who can <span class="text-red-400 font-bold">approve</span> what</p>

</div>

</div>

<!--
[Confident. Slow. This is your anchor.]

"The future of coding agents isn't prompt engineering. It's environment engineering."

"And to be clear — this is not a DevOps talk. This is about trust architecture."

"Who can run what. Who can access what. Who can approve what."

"Everything I show you today maps back to those three questions."
-->

---
background: /img/terminal.jpg
---

<div class="absolute inset-0 bg-gradient-to-b from-black/70 to-black/50 z-1"></div>

<div class="relative z-2">

# Why Web Apps Break Naive Agent Workflows

<div class="grid grid-cols-2 gap-8 mt-8">
<div>

### The Problems

<div class="space-y-3 text-lg">

- 🔴 Port collisions
- 🔴 Shared localhost state
- 🔴 OAuth redirect URLs
- 🔴 Webhooks need public endpoints

</div>

</div>
<div class="flex items-center justify-center">

<div class="text-xl font-bold text-center p-8 border-2 border-red-400/50 rounded-xl bg-red-900/20">

If you're building a CLI, one env works.

Web apps? **Isolation is structural.**

</div>

</div>
</div>

</div>

<!--
"Now — if you're building a Rust CLI, this is easy. Different folder, different binary, done."

"But most of us here are building web systems. Stateful. Networked. Callback-driven."

"OAuth requires a real redirect URL. Webhooks require a public endpoint. You can't just mock everything and pretend that's enough."

"If you want an agent to verify an OAuth flow end-to-end, it has to run against a real, reachable URL. That's when isolation stops being a nice-to-have."
-->

---
layout: cover
background: /img/network-cables.jpg
class: text-center
---

<div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/60 to-transparent z-1"></div>

<div class="relative z-2">

# The Connected Agent Problem

<div class="mt-8 text-gray-400 text-lg">

Simon Willison: <span class="text-white font-semibold">"the lethal trifecta"</span>

</div>

<div class="mt-8 text-xl space-y-4">

<p>🔒 Access to <span class="text-red-400 font-bold">private data</span></p>
<p>📨 Exposure to <span class="text-red-400 font-bold">untrusted content</span></p>
<p>📡 Ability to <span class="text-red-400 font-bold">externally communicate</span></p>

</div>

<div class="mt-6 text-gray-400 text-base">

Combine all three → your agent becomes an attack surface.

</div>

</div>

<!--
[Shift to architect tone. Calm. Serious.]

"Simon Willison has this framing he calls the lethal trifecta."

"Access to private data. Exposure to untrusted content. And the ability to externally communicate."

"Put those three together and your agent becomes an attack surface. That's not theoretical — that's the actual threat model."

"So how do we make this safe?"
-->

---
layout: cover
background: /img/containers.jpg
class: text-center
---

<div class="absolute inset-0 bg-gradient-to-br from-blue-900/70 via-black/60 to-black/80 z-1"></div>

<div class="relative z-2">

# Safe Autonomy Requires Boundaries

<div class="grid grid-cols-3 gap-8 mt-12">
<div class="p-6 bg-white/10 backdrop-blur rounded-xl">
<div class="text-4xl mb-3">🏗️</div>
<h3 class="text-xl font-bold">Isolation</h3>
<p class="text-gray-300 mt-2">prevents interference</p>
</div>
<div class="p-6 bg-white/10 backdrop-blur rounded-xl">
<div class="text-4xl mb-3">🔑</div>
<h3 class="text-xl font-bold">Identity</h3>
<p class="text-gray-300 mt-2">limits blast radius</p>
</div>
<div class="p-6 bg-white/10 backdrop-blur rounded-xl">
<div class="text-4xl mb-3">✅</div>
<h3 class="text-xl font-bold">Feedback Loops</h3>
<p class="text-gray-300 mt-2">proves correctness</p>
</div>
</div>

</div>

<!--
"Three structural controls. Isolation prevents interference. Identity limits blast radius. Feedback loops prove correctness."

"These are not prompt tweaks. These are architectural decisions. Everything I show you from here maps to one of these three."
-->

---
layout: section
---

# Isolation

Parallel environments · Zero interference

<!--
[Transition. Keep it moving.]
-->

---

# Isolation

<div class="grid grid-cols-2 gap-12 mt-8">
<div>

<div class="text-lg space-y-3">

`feature/login-oauth`

→ git worktree

→ container

→ isolated DB

→ branch-specific URL

</div>

<div class="mt-8 p-4 bg-green-900/30 border border-green-500/30 rounded-lg">

Isolation enables **parallel autonomy**.

</div>

</div>
<div class="flex items-center">

```bash
TUNNEL_HOST=feature-login-oauth.rida.me
DATABASE_URL=postgres://…/feature_login_oauth
PORT=3001
```

</div>
</div>

<!--
[This is where the parenting analogy lives. Deliver it warmly, not as a lecture.]

"One thing I learned as a parent: if you want to stop saying 'no' all the time, you manage the environment. Hide the candy. Childproof the cabinets. Once the environment is safe, you can say yes to almost everything."

"AI agents are the same way. The problem wasn't the model. It was their environment."

"Isolation means: git worktree per feature, dev container per worktree, isolated Postgres, branch-specific URL. So feature/login-oauth doesn't share a database with feature/stripe-webhook."

"No port collisions. No localhost assumptions. No agent installing random Node versions on my machine. Everything is ephemeral."

"And that's what enables safe YOLO mode."

[Pause.]

"Isolation isn't about paranoia. It's about enabling autonomy without collateral damage."
-->

---
layout: cover
background: /img/city-night.jpg
class: text-center
---

<div class="absolute inset-0 bg-black/45 z-1"></div>

<div class="relative z-2">

<div class="text-5xl font-serif leading-relaxed">

Parallel work.

No collisions.

</div>

</div>

<!--
[Hold 3 seconds. Don't narrate beyond one line.]

"Three agents. Three branches. Zero conflicts."

[Advance.]
-->

---
layout: center
class: text-center bg-black text-white
---

<div class="text-5xl mb-6">🎬</div>

# Demo: Isolation in Action

<div class="mt-6 text-xl text-gray-400 space-y-2">

<p>Create feature branch → Spin container → Hit unique URL</p>
<p>Agent CLI running inside the isolated environment</p>

</div>

<div class="mt-8 text-sm text-gray-600">~90 seconds</div>

<!--
DEMO 1: Switch to pre-recorded video.
Show: branch create → worktree → docker compose up → tunnel → agent running inside.

[Say almost nothing while it plays. Let it breathe. Under 90 seconds.]

"That's isolation. One command, one environment, completely disposable."

[If video won't play, narrate over the slide text.]
-->

---
layout: section
---

# Identity

Scoped access · Separate accounts · Least privilege

<!--
[Transition.]
-->

---

# Identity

<div class="grid grid-cols-2 gap-8 mt-8">
<div class="p-6 bg-green-900/20 border border-green-500/30 rounded-xl">

### 🔨 Build Agent

- Repo write
- DB migrations
- Stripe test key
- `playwright` · `git push`

</div>
<div class="p-6 bg-blue-900/20 border border-blue-500/30 rounded-xl">

### 👁️ Review Agent

- Read-only repo
- No DB writes
- No API keys
- `rg` · `rubocop` · `git diff`

</div>
</div>

<div class="mt-6 text-sm text-gray-400 italic text-center">

I created a separate GitHub account for my agent. My contribution graph is shrinking. Its graph is growing.

</div>

<div class="mt-4 text-center text-xl">

Isolation protects the system. Identity protects <span class="text-yellow-400 font-bold">authority</span>.

</div>

<!--
"The second boundary is identity. And I think this is the one people underappreciate."

"Think about onboarding a new engineer. You don't give them your credentials. You provision access — GitHub, Slack, ticketing, secrets — and you scope it."

"My build agent has repo write access, migration permissions, Stripe test keys. My review agent? Read-only. No DB writes. No API keys."

"I actually created a separate GitHub account for my agent. It opens PRs as itself. My contribution graph is shrinking. Its contribution graph is growing. Now I'm orchestrating. It's executing. That shift matters."

"Isolation protects the system. Identity protects authority."

[Q&A prep: if someone asks about GitHub ToS, it's a machine user account — same as a CI bot.]
-->

---
layout: center
class: text-center
---

<div class="text-2xl leading-relaxed">

You wouldn't give a new hire:

</div>

<div class="mt-8 space-y-4 text-3xl">

<p>🗄️ Production DB access</p>
<p>💳 Stripe live keys</p>
<p class="text-red-400 font-mono">🔥 rm -rf /</p>

</div>

<!--
[Smile. Let each line land.]

"You wouldn't give a new hire production database access. You wouldn't hand them live Stripe keys."

[Gesture at rm -rf.]

"So why are we giving agents all of our credentials?"

[Short beat. Move on.]
-->

---

# Skills = Progressive Disclosure

<div class="mt-8 space-y-6">

<div class="p-4 bg-gray-800/50 rounded-lg font-mono text-lg">

```
agents.md          → thin, high-level
  └── skills/      → loaded on demand
       ├── deploy/
       ├── test/
       └── review/
```

</div>

<div class="text-xl mt-6">

Only load the <span class="text-green-400 font-bold">OAuth skill</span> when you're doing OAuth.

Only load the <span class="text-green-400 font-bold">Playwright workflow</span> when you're doing E2E.

</div>

<div class="mt-4 text-sm text-gray-400">

I started with Playwright MCP. Now I use Chrome DevTools Protocol (CDP) directly through a custom skill. The tooling moves fast — the pattern matters more than the tool.

</div>

</div>

<!--
"Another lesson I learned: context gets polluted fast."

"I had this massive agents.md file. It explained everything. Loaded every time into the context window. Not sustainable."

"So I moved toward progressive disclosure. Thin core file. Referenced skills. Only load the OAuth testing skill when you're doing OAuth. Only load the Playwright workflow when you're doing E2E."

"I started with Playwright MCP for browser testing. Now I'm using Chrome DevTools Protocol — CDP — directly through a custom skill. You literally just run Chrome and open up the protocol, and the agent can control the browser directly. The tooling moves fast — what matters is the pattern, not the specific tool."

"This isn't just context optimization. It's modular architecture for reasoning."
-->

---
layout: section
---

# Feedback Loops

Verification · Validation · Accountability

<!--
[Transition.]
-->

---
background: /img/checklist.jpg
---

<div class="absolute inset-0 bg-gradient-to-r from-black/85 to-black/50 z-1"></div>

<div class="relative z-2">

# Definition of Done

<div class="text-xl mt-4 text-gray-300">Don't prescribe the path. Define the destination.</div>

<div class="mt-8 space-y-3 text-xl">

<p>✅ Tests pass</p>
<p>✅ OAuth verified</p>
<p>✅ E2E works</p>
<p>✅ PR reviewed</p>

</div>

<div class="mt-6 p-4 bg-yellow-900/20 border border-yellow-500/30 rounded-lg text-center text-lg">

Autonomy without verification = chaos.<br/>
Verification without autonomy = micromanagement.

</div>

</div>

<!--
[Call back to the opening. This is a key moment.]

"Remember that checklist from the opening? The agent wrote that one. 'Production-ready and enterprise-grade.'"

"This checklist? You write this one. That's the difference."

"Done means: the tests pass. The OAuth handshake works end-to-end. The E2E flow completes. The PR is reviewed."

"You wouldn't tell a senior engineer which files to edit. You'd tell them what done looks like."

[Pause.]

"Autonomy without verification is chaos. Verification without autonomy is micromanagement. Safe autonomy lives in the middle."
-->

---

# Self-Validation Loop

<div class="flex justify-center mt-12">
<div class="space-y-4 text-center">

<div class="text-2xl p-4 bg-red-900/30 rounded-lg">❌ Fail</div>
<div class="text-3xl">↓</div>
<div class="text-2xl p-4 bg-yellow-900/30 rounded-lg">🔧 Patch</div>
<div class="text-3xl">↓</div>
<div class="text-2xl p-4 bg-blue-900/30 rounded-lg">🔄 Rerun</div>
<div class="text-3xl">↓</div>
<div class="text-2xl p-4 bg-green-900/30 rounded-lg">✅ Green</div>

</div>
</div>

<div class="mt-8 text-center text-lg text-gray-400">

Human reviews only after validation passes.

</div>

<!--
"Once the environment supports it, the agent can: fail, patch, rerun, repeat."

"Now I'm not manually clicking through flows. I'm reviewing outcomes."

"The agent catches its own regressions. You only see work after it's proven itself."

"Human reviews only after validation passes. That's the deal."
-->

---
layout: center
class: text-center
---

<div class="text-7xl font-bold text-white">35</div>

<div class="text-2xl mt-4 text-gray-300">review rounds.</div>

<div class="mt-8 text-xl space-y-2 text-gray-400">

<p>No ego. No fatigue.</p>
<p>No "ship it already."</p>

</div>

<div class="mt-8 text-lg text-green-400 space-y-2">

<p>Nitpicking is free when agents do it.</p>
<p class="text-gray-400 text-base">That changes the economics of quality.</p>

</div>

<!--
[Say "35." Then STOP. Full 3 seconds of silence. Let them process the number.]

"Thirty-five. I would have stopped at three."

"Think about how many times we brush off nitpicky feedback just to get things moving. How many times we accept 'good enough' because we're tired and we want to ship."

"Agents don't get tired. Nitpicking is free when agents do it. That changes the economics of quality."
-->

---

# Cross-Agent Review

<div class="grid grid-cols-3 gap-6 mt-8">
<div class="p-5 bg-blue-900/20 border border-blue-500/30 rounded-xl text-center">
<div class="text-3xl mb-3">🔨</div>
<h3 class="font-bold">Build Agent</h3>
<p class="text-sm text-gray-400 mt-2">Opens PR</p>
<p class="text-sm text-gray-400">Proves green</p>
</div>
<div class="p-5 bg-purple-900/20 border border-purple-500/30 rounded-xl text-center">
<div class="text-3xl mb-3">🔍</div>
<h3 class="font-bold">Review Agent</h3>
<p class="text-sm text-gray-400 mt-2">Comments on risks</p>
<p class="text-sm text-gray-400">Suggests fixes</p>
</div>
<div class="p-5 bg-green-900/20 border border-green-500/30 rounded-xl text-center">
<div class="text-3xl mb-3">👤</div>
<h3 class="font-bold">Human</h3>
<p class="text-sm text-gray-400 mt-2">Final call</p>
<p class="text-sm text-gray-400">Merges</p>
</div>
</div>

<div class="mt-8 text-center text-xl">

Structural dissent <span class="text-purple-400">by design</span>.

</div>

<!--
"Codex builds. Gemini reviews. Different models, different blind spots. That's the point."

"Each model reads the code differently and falls into different mistakes. Claude approaches problems differently than Codex. Two different agents, two different identities. That's why cross-agent review works."

"I use Gemini's free code review feature — install it on GitHub, comment /gemini review. My build agent has the GitHub CLI, so it fetches those comments and addresses them in a loop."

"This is separation of concerns applied to agents. We already do this on human teams. Same principle. Structural dissent by design."
-->

---
layout: center
class: text-center bg-black text-white
---

<div class="text-5xl mb-6">🎬</div>

# Demo: Cross-Agent Review

<div class="mt-6 text-xl text-gray-400 space-y-2">

<p>Agent runs tests → Gemini reviews PR → Build agent addresses comments</p>

</div>

<div class="mt-8 text-sm text-gray-600">~90 seconds</div>

<!--
DEMO 2: Switch to pre-recorded video.
Show: agent pushes → tests green → Gemini reviews → comments on edge case → build agent fixes → re-verified.

[Keep it under 90 seconds. Practice the window switch.]

"That's the loop. Build, review, fix, verify. No human in the middle until it's clean."
-->

---
layout: section
---

# The Payoff

<!--
[This is your energy bridge. Before advancing, deliver this verbally:]

"We are as productive as our environment allows. That was true before AI."

"The best engineering teams were the ones with good local setup, strong verification, clean review culture. AI doesn't change that. It amplifies it."

"If your environment is chaotic, agents amplify chaos. If your environment encodes boundaries, agents amplify quality."

[Then advance.]
-->

---
layout: cover
background: /img/team-dark.jpg
class: text-center
---

<div class="absolute inset-0 bg-gradient-to-t from-black/80 to-black/40 z-1"></div>

<div class="relative z-2">

<div class="space-y-6 text-3xl font-serif">

<p>Not autocomplete.</p>

<p>Not chaos.</p>

<p class="text-4xl font-bold text-white mt-4">Teammates.</p>

</div>

<div class="mt-8 text-xl text-gray-300">

Reliable. Accountable. Safe to collaborate with.

</div>

</div>

<!--
[Pause between each line. Let each one land.]

"Not autocomplete."

[Beat.]

"Not chaos."

[Beat.]

"Teammates."

"Reliable. Accountable. Safe to collaborate with."
-->

---
layout: cover
background: /img/earth-night.jpg
class: text-center
---

<div class="absolute inset-0 bg-gradient-to-b from-transparent via-black/50 to-black/80 z-1"></div>

<div class="relative z-2">

<div class="max-w-3xl mx-auto space-y-4 text-xl leading-relaxed">

<p class="text-gray-400">Agents are powerful because they're connected.</p>
<p class="text-gray-400">Reliability comes from environment design.</p>

<p class="text-gray-300">Isolation defines where agents run.</p>
<p class="text-gray-300">Identity defines what they're allowed to do.</p>
<p class="text-gray-300">Feedback loops define when they're done.</p>

<p class="text-white text-2xl font-bold mt-4">That's how agents become teammates.</p>

</div>

</div>

<!--
[Deliver from memory if you can. Eyes on the room, not the screen. Slow. One line at a time.]

"Agents are powerful because they're connected."
"Reliability comes from environment design."

"Isolation defines where agents run."
"Identity defines what they're allowed to do."
"Feedback loops define when they're done."

[Pause.]

"That's how agents become teammates."

[Hold. Then advance.]
-->

---
layout: cover
background: /img/earth-night.jpg
class: text-center
---

<div class="absolute inset-0 bg-gradient-to-b from-black/60 via-black/70 to-black/90 z-1"></div>

<div class="relative z-2">

<div class="max-w-3xl mx-auto">

<div class="text-2xl leading-relaxed">

AI doesn't remove responsibility. It <span class="font-bold">redistributes</span> it.

</div>

<div class="mt-8 text-3xl font-bold text-green-400">

Design it intentionally.

</div>

</div>

</div>

<!--
"AI doesn't remove responsibility. It redistributes it."

"When you connect agents to real systems, you are designing their blast radius."

[Pause.]

"Design it intentionally."

[Hold. Nod. Done.]
-->

---
layout: cover
background: /img/code-artistic.jpg
class: text-center
---

<div class="absolute inset-0 bg-gradient-to-br from-black/70 to-purple-900/30 z-1"></div>

<div class="relative z-2">

# Thank you

<div class="mt-2 text-xl text-gray-300">

**Rida Al Barazi** · rida.me · @rida

</div>

<div class="mt-2 text-gray-400 text-sm italic">

"How can we codify our engineering culture?"

</div>

<div class="grid grid-cols-2 gap-8 mt-6 items-center max-w-2xl mx-auto">
<div class="text-left text-gray-400 text-sm space-y-1">

<p>BranchBox: github.com/branchbox/branchbox</p>
<p>Blog: rida.me/blog</p>

</div>
<div>

<img src="/feedback-qr.png" class="w-36 h-36 mx-auto rounded-lg shadow-xl" alt="Feedback QR" />
<div class="text-xs text-gray-500 mt-1">confoo.ca/f/B1E9…</div>

</div>
</div>

</div>

<!--
"Thank you."

[Don't rush. Let them clap.]

"If you want to try this model, BranchBox is open source. The blog has the details."

"And if you have a minute, the feedback QR is right there — it genuinely helps."

[Leave this slide up during Q&A.]
-->
