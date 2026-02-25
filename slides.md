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
Smile. Let the room settle.
-->

---
layout: cover
background: /img/matrix.jpg
class: text-center
---

<div class="absolute inset-0 bg-black/60 z-1"></div>

<div class="relative z-2">

<div class="text-4xl font-serif italic leading-relaxed">

"All tests passed."

</div>

<div class="mt-6 text-xl text-gray-400">

(narrator voice: they did not)

</div>

</div>

<!--
Open calmly. Deadpan delivery. Pause 3 seconds. Let them laugh.
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
Tell QA story. OAuth broken. Webhook broken. Copy-paste errors.
"I was the one clicking through the app after every change. I was the bottleneck."
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
"That's the gap. The generation is fast. The verification isn't. This talk is about closing that gap."
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
Confident. No hype. "This talk is about one idea: design the environment, not just the prompt."
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
"If you're building a CLI tool, maybe one env works. Web apps? No chance.
Ports collide. OAuth breaks. Webhooks need public URLs. This is why architecture matters."
-->

---
layout: cover
background: /img/network-cables.jpg
class: text-center
---

<div class="absolute inset-0 bg-gradient-to-t from-black/80 via-black/60 to-transparent z-1"></div>

<div class="relative z-2">

# The Connected Agent Problem

<div class="mt-12 text-2xl space-y-4">

<p>Model + Tools + Untrusted input</p>

<p class="text-red-400 text-3xl font-bold">= Real blast radius</p>

</div>

<div class="mt-8 text-gray-400 text-lg">

Simon Willison: <span class="text-white font-semibold">"the lethal trifecta"</span>

</div>

</div>

<!--
Calm. Architect tone. "An agent with tool access and untrusted input isn't just powerful. It's dangerous."
-->

---
layout: section
---

# The Model

Isolation · Identity · Feedback Loops

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
"Three pillars. Everything I show you maps back to one of these."
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
"Each agent gets its own branch, database, URL. They can't step on each other."
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
Visual reset. Slow down. Let the image breathe.
"Three agents. Three branches. Zero conflicts."
-->

---
layout: section
---

# Identity

Scoped access · Separate accounts · Least privilege

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
"You wouldn't give a new hire the same access as a staff engineer."
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
Smile. Short beat. Move on.
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

I started with Playwright MCP. Now I use CDP directly through a custom skill. The tooling moves fast — the pattern matters more than the tool.

</div>

</div>

<!--
"Think progressive disclosure in UI design. The agent starts minimal. It loads skills on demand."
-->

---
layout: section
---

# Feedback Loops

Verification · Validation · Accountability

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
"You wouldn't tell a senior engineer which files to edit. You'd tell them what done looks like."
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
"The agent catches its own regressions. You only see work after it's proven."
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
Slow. Let them process 35.
"I watched two agents go 35 rounds on a single PR. No frustration. No shortcuts. Just better code."
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
-->

---
layout: section
---

# The Payoff

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
Pause between lines. Let each one land.
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

<div class="mt-8 text-2xl">

AI doesn't remove responsibility. It <span class="font-bold">redistributes</span> it.

</div>

<div class="mt-4 text-3xl font-bold text-green-400">

Design it intentionally.

</div>

</div>

</div>

<!--
Slow. Calm. Stop.
"This is the one takeaway. You are the architect of your agents' blast radius."
-->

---
layout: cover
background: /img/code-artistic.jpg
class: text-center
---

<div class="absolute inset-0 bg-gradient-to-br from-black/70 to-purple-900/30 z-1"></div>

<div class="relative z-2">

<div class="text-5xl mb-4">🙏</div>

# Thank you

<div class="mt-4 text-xl text-gray-300">

**Rida Al Barazi**

rida.me · @rida

</div>

<div class="mt-4 text-gray-400 text-sm italic">

"How can we codify our engineering culture?"

</div>

<div class="mt-4 text-gray-500 text-sm">

BranchBox: github.com/branchbox/branchbox

Blog: rida.me/blog

</div>

</div>

---
layout: center
class: text-center
---

# 📝 Feedback

<img src="/feedback-qr.png" class="w-48 h-48 mx-auto my-6 rounded-xl shadow-2xl" alt="Feedback QR Code" />

<div class="text-lg">

confoo.ca/f/B1E9D3155640A9D8A5F4E90DF8874288

</div>

<div class="text-gray-400 text-sm mt-4">

Your feedback helps!

</div>
