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

<div class="absolute inset-0 bg-gradient-to-br from-black/80 via-black/60 to-indigo-900/20 z-1"></div>

<div class="relative z-2 flex flex-col items-center justify-center h-full">

<h1 class="!text-5xl !font-light tracking-tight">Safe Agentic Coding</h1>

<p class="text-xl text-white/60 mt-4 font-light tracking-wide">Environment Engineering for Reliable AI Teammates</p>

<div class="mt-12 text-white/40 text-sm tracking-widest uppercase">
Rida Al Barazi · ConFoo 2026
</div>

</div>

<div class="absolute bottom-8 right-8 flex items-center gap-3 z-2">
<img src="/feedback-qr.png" class="w-20 h-20 rounded-lg opacity-80" alt="Feedback QR" />
<span class="text-xs text-white/30">Feedback</span>
</div>

<!--
[Smile. Let the room settle. Don't rush. Wait until the chatter dies down.]

No preamble. This audience is warmed up. They've been at ConFoo for a day. They've seen the Kiro keynote. They've sat through MCP talks. Respect that.
-->

---
layout: center
class: bg-[#0a0a0a]
---

<div class="max-w-3xl mx-auto font-mono text-left">

<div class="rounded-xl p-8 border border-white/10 bg-white/[0.03]">

<div class="text-emerald-400 text-2xl leading-relaxed font-medium">

✅ Complete success!

All systems are production-ready and enterprise-grade.

</div>

<div class="mt-6 text-white/40 text-lg space-y-1">

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
class: text-center bg-[#0a0a0a]
---

<div class="text-xl text-white/30 italic font-light">

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

<div class="text-2xl leading-relaxed text-white/70 font-light">

The real bottleneck wasn't the model.

<div class="mt-10 text-5xl font-bold text-white">

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

<div class="text-2xl text-white/60 font-light">

Your agent can write a feature in 4 minutes.

</div>

<div class="text-3xl font-semibold text-amber-400 mt-8">

Can you verify it in 4 minutes?

</div>

<div class="mt-10 text-lg text-white/40 font-light leading-relaxed">

This talk is a practical framework for making agentic coding<br/>safe enough for daily development.

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
class: bg-[#0a0a0a]
---

<img src="/img/harold-10k-lines.jpg" class="mx-auto max-h-96 rounded-xl" />

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

<div class="absolute inset-0 bg-gradient-to-r from-black/85 via-black/60 to-transparent z-1"></div>

<div class="relative z-2 max-w-2xl">

<h1 class="!text-4xl !font-light !leading-snug">
The future of coding agents<br/>
<span class="!font-semibold">isn't prompt engineering.</span><br/>
<span class="!font-semibold">It's environment engineering.</span>
</h1>

<div class="mt-10 text-xl text-white/50 space-y-3 font-light">

<p>Who can <span class="text-emerald-400 font-medium">run</span> what</p>
<p>Who can <span class="text-amber-400 font-medium">access</span> what</p>
<p>Who can <span class="text-rose-400 font-medium">approve</span> what</p>

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

<div class="absolute inset-0 bg-gradient-to-b from-black/80 to-black/60 z-1"></div>

<div class="relative z-2">

# Why Web Apps Break Naive Agent Workflows

<div class="grid grid-cols-2 gap-12 mt-8">
<div>

<div class="space-y-4 text-lg text-white/70">

- Port collisions
- Shared localhost state
- OAuth redirect URLs
- Webhooks need public endpoints

</div>

</div>
<div class="flex items-center justify-center">

<div class="text-lg text-center p-8 border border-white/10 rounded-xl bg-white/[0.03]">

<p class="text-white/50">If you're building a CLI, one env works.</p>
<p class="text-white font-medium mt-3">Web apps? Isolation is structural.</p>

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

<div class="absolute inset-0 bg-gradient-to-t from-black/85 via-black/65 to-black/40 z-1"></div>

<div class="relative z-2">

<h1 class="!font-light">The Connected Agent Problem</h1>

<div class="mt-4 text-white/40 text-lg font-light">

Simon Willison · <span class="text-white/70 font-normal">"the lethal trifecta"</span>

</div>

<div class="mt-10 text-xl space-y-5 text-white/70">

<p>Access to <span class="text-rose-400 font-medium">private data</span></p>
<p>Exposure to <span class="text-rose-400 font-medium">untrusted content</span></p>
<p>Ability to <span class="text-rose-400 font-medium">externally communicate</span></p>

</div>

<div class="mt-8 text-white/30 text-base font-light">

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

<div class="absolute inset-0 bg-gradient-to-br from-indigo-900/50 via-black/70 to-black/85 z-1"></div>

<div class="relative z-2">

<h1 class="!font-light">Safe Autonomy Requires Boundaries</h1>

<div class="grid grid-cols-3 gap-8 mt-14">
<div class="p-6 bg-white/[0.04] backdrop-blur rounded-xl border border-white/[0.06]">
<h3 class="text-xl font-semibold text-emerald-400">Isolation</h3>
<p class="text-white/40 mt-3 font-light">prevents interference</p>
</div>
<div class="p-6 bg-white/[0.04] backdrop-blur rounded-xl border border-white/[0.06]">
<h3 class="text-xl font-semibold text-amber-400">Identity</h3>
<p class="text-white/40 mt-3 font-light">limits blast radius</p>
</div>
<div class="p-6 bg-white/[0.04] backdrop-blur rounded-xl border border-white/[0.06]">
<h3 class="text-xl font-semibold text-rose-400">Feedback Loops</h3>
<p class="text-white/40 mt-3 font-light">proves correctness</p>
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

<div class="text-emerald-400 font-light tracking-wide">Part I</div>

# Isolation

<div class="text-white/40 font-light mt-2">Parallel environments · Zero interference</div>

<!--
[Transition. Keep it moving.]
-->

---

# Isolation

<div class="grid grid-cols-2 gap-12 mt-8">
<div>

<div class="text-lg space-y-3 text-white/70 font-light">

`feature/login-oauth`

→ git worktree

→ container

→ isolated DB

→ branch-specific URL

</div>

<div class="mt-8 p-4 bg-emerald-500/[0.08] border border-emerald-500/20 rounded-lg">

<span class="text-emerald-400 font-medium">Isolation enables parallel autonomy.</span>

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

<div class="absolute inset-0 bg-gradient-to-b from-black/60 via-black/50 to-black/70 z-1"></div>

<div class="relative z-2 flex items-center justify-center h-full">

<div class="text-4xl font-light leading-loose tracking-tight text-white/90">

Parallel work.<br/>No collisions.

</div>

</div>

<!--
[Hold 3 seconds. Don't narrate beyond one line.]

"Three agents. Three branches. Zero conflicts."

[Advance.]
-->

---
layout: center
class: text-center bg-[#0a0a0a]
---

<div class="text-white/20 text-sm uppercase tracking-widest mb-6">Demo</div>

# Isolation in Action

<div class="mt-8 text-lg text-white/40 font-light space-y-2">

<p>Create feature branch → Spin container → Hit unique URL</p>
<p>Agent CLI running inside the isolated environment</p>

</div>

<div class="mt-10 text-sm text-white/20">~90 seconds</div>

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

<div class="text-amber-400 font-light tracking-wide">Part II</div>

# Identity

<div class="text-white/40 font-light mt-2">Scoped access · Separate accounts · Least privilege</div>

<!--
[Transition.]
-->

---

# Identity

<div class="grid grid-cols-2 gap-8 mt-8">
<div class="p-6 bg-white/[0.03] border border-white/[0.06] rounded-xl">

### Build Agent

<div class="text-white/50 mt-4 space-y-2 font-light">

- Repo write access
- DB migrations
- Stripe test key
- `playwright` · `git push`

</div>

</div>
<div class="p-6 bg-white/[0.03] border border-white/[0.06] rounded-xl">

### Review Agent

<div class="text-white/50 mt-4 space-y-2 font-light">

- Read-only repo
- No DB writes
- No API keys
- `rg` · `rubocop` · `git diff`

</div>

</div>
</div>

<div class="mt-8 text-sm text-white/30 italic text-center font-light">

I created a separate GitHub account for my agent.<br/>My contribution graph is shrinking. Its graph is growing.

</div>

<div class="mt-4 text-center text-lg text-white/70">

Isolation protects the system. Identity protects <span class="text-amber-400 font-medium">authority</span>.

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

<div class="text-2xl text-white/50 font-light leading-relaxed">

You wouldn't give a new hire

</div>

<div class="mt-10 space-y-5 text-2xl text-white/70">

<p>Production DB access</p>
<p>Stripe live keys</p>
<p class="font-mono text-rose-400">rm -rf /</p>

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

<div class="p-6 bg-white/[0.03] rounded-xl border border-white/[0.06] font-mono text-lg text-white/60">

```
agents.md          → thin, high-level
  └── skills/      → loaded on demand
       ├── deploy/
       ├── test/
       └── review/
```

</div>

<div class="text-xl mt-8 text-white/70 font-light">

Only load the <span class="text-emerald-400 font-medium">OAuth skill</span> when you're doing OAuth.

Only load the <span class="text-emerald-400 font-medium">Playwright workflow</span> when you're doing E2E.

</div>

<div class="mt-6 text-sm text-white/30 font-light">

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

<div class="text-rose-400 font-light tracking-wide">Part III</div>

# Feedback Loops

<div class="text-white/40 font-light mt-2">Verification · Validation · Accountability</div>

<!--
[Transition.]
-->

---
background: /img/checklist.jpg
---

<div class="absolute inset-0 bg-gradient-to-r from-black/90 to-black/60 z-1"></div>

<div class="relative z-2">

# Definition of Done

<div class="text-lg mt-4 text-white/40 font-light">Don't prescribe the path. Define the destination.</div>

<div class="mt-10 space-y-4 text-xl text-white/70 font-light">

<p>Tests pass</p>
<p>OAuth verified end-to-end</p>
<p>E2E flow completes</p>
<p>PR reviewed</p>

</div>

</div>

<!--
[Call back to the opening.]

"Remember that checklist from the opening? The agent wrote that one. 'Production-ready and enterprise-grade.'"

"This checklist? You write this one. That's the difference."

"Done means: the tests pass. The OAuth handshake works end-to-end. The E2E flow completes. The PR is reviewed."

"You wouldn't tell a senior engineer which files to edit. You'd tell them what done looks like."
-->

---
layout: center
class: text-center
---

<div class="max-w-2xl mx-auto space-y-8">

<div class="text-2xl text-rose-400/80 font-light">Autonomy without verification — chaos.</div>

<div class="text-2xl text-amber-400/80 font-light">Verification without autonomy — micromanagement.</div>

<div class="text-2xl font-medium text-emerald-400 mt-6">Safe autonomy lives in the middle.</div>

</div>

<!--
[Pause after each line. Let them land separately.]

"Autonomy without verification is chaos." [Beat.]

"Verification without autonomy is micromanagement." [Beat.]

"Safe autonomy lives in the middle."

[Hold. This is the thesis of the entire Feedback Loops section. Then advance.]
-->

---

# Self-Validation Loop

<div class="flex justify-center mt-12">
<div class="flex items-center gap-6">

<div class="text-lg p-5 bg-rose-500/[0.08] rounded-xl border border-rose-500/15 text-center w-32">
<div class="text-rose-400 font-medium">Fail</div>
</div>

<div class="text-white/20 text-2xl">→</div>

<div class="text-lg p-5 bg-amber-500/[0.08] rounded-xl border border-amber-500/15 text-center w-32">
<div class="text-amber-400 font-medium">Patch</div>
</div>

<div class="text-white/20 text-2xl">→</div>

<div class="text-lg p-5 bg-sky-500/[0.08] rounded-xl border border-sky-500/15 text-center w-32">
<div class="text-sky-400 font-medium">Rerun</div>
</div>

<div class="text-white/20 text-2xl">→</div>

<div class="text-lg p-5 bg-emerald-500/[0.08] rounded-xl border border-emerald-500/15 text-center w-32">
<div class="text-emerald-400 font-medium">Green?</div>
</div>

</div>
</div>

<div class="text-center mt-6 text-white/30 text-sm italic font-light">repeat until green</div>

<div class="mt-8 text-center text-lg text-white/50 font-light">

Human reviews only after the loop exits green.

</div>

<!--
"The agent fails. Patches. Reruns. And if it's still red? Back around. Fail, patch, rerun. Again."

"This isn't a waterfall. It's a loop. The agent keeps going until it's green."

"Human reviews only after the loop exits. That's the deal."
-->

---
layout: center
class: text-center
---

<div class="text-8xl font-extralight text-white tracking-tight">35</div>

<div class="text-xl mt-4 text-white/40 font-light">review rounds.</div>

<div class="mt-10 text-lg space-y-2 text-white/30 font-light">

<p>No ego. No fatigue.</p>
<p>No "ship it already."</p>

</div>

<div class="mt-10 text-lg text-emerald-400/80 font-light">

Nitpicking is free when agents do it.

</div>

<div class="text-white/30 text-sm mt-1 font-light">That changes the economics of quality.</div>

<!--
[Say "35." Then STOP. Full 3 seconds of silence. Let them process the number.]

"Thirty-five. I would have stopped at three."

"Think about how many times we brush off nitpicky feedback just to get things moving. How many times we accept 'good enough' because we're tired and we want to ship."

"Agents don't get tired. Nitpicking is free when agents do it. That changes the economics of quality."
-->

---

# Cross-Agent Review

<div class="grid grid-cols-3 gap-6 mt-10">
<div class="p-6 bg-white/[0.03] border border-white/[0.06] rounded-xl text-center">
<h3 class="font-semibold text-emerald-400">Build Agent</h3>
<div class="text-sm text-white/40 mt-3 space-y-1 font-light">
<p>Opens PR</p>
<p>Proves green</p>
</div>
</div>
<div class="p-6 bg-white/[0.03] border border-white/[0.06] rounded-xl text-center">
<h3 class="font-semibold text-amber-400">Review Agent</h3>
<div class="text-sm text-white/40 mt-3 space-y-1 font-light">
<p>Comments on risks</p>
<p>Suggests fixes</p>
</div>
</div>
<div class="p-6 bg-white/[0.03] border border-white/[0.06] rounded-xl text-center">
<h3 class="font-semibold text-white/80">Human</h3>
<div class="text-sm text-white/40 mt-3 space-y-1 font-light">
<p>Final call</p>
<p>Merges</p>
</div>
</div>
</div>

<div class="mt-10 text-center text-xl text-white/60 font-light">

Structural dissent <span class="text-amber-400 font-medium">by design</span>.

</div>

<!--
"Codex builds. Gemini reviews. Different models, different blind spots. That's the point."

"Each model reads the code differently and falls into different mistakes. Claude approaches problems differently than Codex. Two different agents, two different identities. That's why cross-agent review works."

"I use Gemini's free code review feature — install it on GitHub, comment /gemini review. My build agent has the GitHub CLI, so it fetches those comments and addresses them in a loop."

"This is separation of concerns applied to agents. We already do this on human teams. Same principle. Structural dissent by design."
-->

---
layout: center
class: text-center bg-[#0a0a0a]
---

<div class="text-white/20 text-sm uppercase tracking-widest mb-6">Demo</div>

# Cross-Agent Review

<div class="mt-8 text-lg text-white/40 font-light space-y-2">

<p>Agent runs tests → Gemini reviews PR → Build agent addresses comments</p>

</div>

<div class="mt-10 text-sm text-white/20">~90 seconds</div>

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

<div class="absolute inset-0 bg-gradient-to-t from-black/85 to-black/50 z-1"></div>

<div class="relative z-2 flex flex-col items-center justify-center h-full">

<div class="space-y-6 text-3xl font-light">

<p class="text-white/50">Not autocomplete.</p>

<p class="text-white/50">Not chaos.</p>

<p class="text-4xl font-semibold text-white mt-4">Teammates.</p>

</div>

<div class="mt-8 text-lg text-white/40 font-light">

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

<div class="absolute inset-0 bg-gradient-to-b from-transparent via-black/60 to-black/85 z-1"></div>

<div class="relative z-2 flex flex-col items-center justify-center h-full">

<div class="max-w-3xl mx-auto space-y-4 text-lg leading-loose font-light">

<p class="text-white/40">Agents are powerful because they're connected.</p>
<p class="text-white/40">Reliability comes from environment design.</p>

<p class="text-white/60 mt-4">Isolation defines where agents run.</p>
<p class="text-white/60">Identity defines what they're allowed to do.</p>
<p class="text-white/60">Feedback loops define when they're done.</p>

<p class="text-white text-2xl font-medium mt-6">That's how agents become teammates.</p>

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

<div class="absolute inset-0 bg-gradient-to-b from-black/70 via-black/75 to-black/90 z-1"></div>

<div class="relative z-2 flex flex-col items-center justify-center h-full">

<div class="max-w-3xl mx-auto">

<div class="text-2xl font-light text-white/70 leading-relaxed">

AI doesn't remove responsibility. It <span class="font-semibold text-white">redistributes</span> it.

</div>

<div class="mt-10 text-3xl font-medium text-emerald-400">

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

<div class="absolute inset-0 bg-gradient-to-br from-black/80 via-black/60 to-indigo-900/20 z-1"></div>

<div class="relative z-2 flex flex-col items-center justify-center h-full">

<h1 class="!font-light !text-4xl">Thank you</h1>

<div class="mt-3 text-lg text-white/50 font-light">

Rida Al Barazi · rida.me · @rida

</div>

<div class="mt-2 text-white/30 text-sm italic font-light">

"How can we codify our engineering culture?"

</div>

<div class="grid grid-cols-2 gap-12 mt-8 items-center max-w-xl mx-auto">
<div class="text-left text-white/30 text-sm space-y-2 font-light">

<p>BranchBox: github.com/branchbox/branchbox</p>
<p>Blog: rida.me/blog</p>

</div>
<div>

<img src="/feedback-qr.png" class="w-32 h-32 mx-auto rounded-lg opacity-80" alt="Feedback QR" />
<div class="text-xs text-white/20 mt-2">confoo.ca/f/B1E9…</div>

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
