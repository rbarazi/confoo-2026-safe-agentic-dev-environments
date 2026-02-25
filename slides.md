---
theme: default
title: Safe Agentic Coding
info: |
  Environment Engineering for Reliable AI Teammates
class: text-center text-white
background: /img/server-room.jpg
drawings:
  persist: false
transition: slide-left
---

<div class="absolute inset-0 bg-black/55 z-1"></div>

<div class="relative z-2">

# Safe Agentic Coding

### Environment Engineering for Reliable AI Teammates

Rida Al Barazi · ConFoo 2026

</div>

<div class="absolute bottom-8 right-8 flex items-center gap-2 z-2">
<img src="/feedback-qr.png" class="w-24 h-24" alt="Feedback QR" />
<span class="text-xs text-gray-400">Feedback</span>
</div>

<!--
Smile. Let the room settle. "Good morning/afternoon, everyone."
-->

---
layout: center
class: text-center bg-black text-white
---

"All tests passed."

<small class="opacity-70">(narrator voice: they did not)</small>

<!--
Open calmly. Deadpan delivery. Pause. Let them laugh.
-->

---
layout: center
class: text-center
---

The real bottleneck wasn't the model.

It was me.

<!--
Tell QA story. OAuth broken. Webhook broken. Copy-paste errors. Frustration.
"I was the one clicking through the app after every change. I was the one reviewing every line. I was the bottleneck."
-->

---
layout: center
---

# The future of coding agents
## isn't prompt engineering.
## It's environment engineering.

Environment engineering = **trust architecture**

Who can run what

Who can access what

Who can approve what

<!--
Confident. No hype. Shift to architecture framing.
"This talk is about one idea: if you want agents that are reliable, you have to design the environment they work in."
-->

---
layout: center
class: text-center bg-black text-white
---

<div class="text-6xl mb-6">🔥🐕☕🔥</div>

"This is fine."

<small class="opacity-70 mt-4">When the agent says "tests passed"</small>

<!--
Quick laugh. Immediately pivot serious.
REPLACE: swap emoji for actual meme image tonight if you find one you like.
-->

---

# Why Web Apps Break Naive Agent Workflows

- Port collisions
- Shared localhost state
- OAuth redirect URLs
- Webhooks requiring public endpoints

Isolation isn't optional. It's structural.

<!--
Contrast Rust CLI vs web apps. Stateful, networked systems.
"If you're building a CLI tool, maybe you can get away with agents sharing one environment. Web apps? No chance."
This is why architecture matters.
-->

---
background: /img/network-cables.jpg
class: text-white
---

<div class="absolute inset-0 bg-black/55 z-1"></div>

<div class="relative z-2">

# The Connected Agent Problem

Model + Tools + Untrusted input = Real blast radius

</div>

<!--
Reference Simon Willison: "the lethal trifecta."
Calm. Architect tone. "An agent with tool access and untrusted input isn't just powerful. It's dangerous."
-->

---
background: /img/terminal.jpg
class: text-white
---

<div class="absolute inset-0 bg-black/60 z-1"></div>

<div class="relative z-2">

# Safe Autonomy Requires Boundaries

## Isolation

_where it runs_

## Identity

_what it can do_

## Feedback Loops

_when it's done_

</div>

<!--
This is the mental model. Return to this if lost.
"Three pillars. Everything I'm going to show you maps back to one of these."
-->

---

# Isolation

feature/login-oauth

→ git worktree
→ container
→ isolated DB
→ branch-specific URL

Isolation enables parallel autonomy.

<!--
Key phrase: Not just safety. Parallel execution. Multiple agents. No collisions.
"Each agent gets its own branch, its own database, its own URL. They can't step on each other."
-->

---
layout: center
class: text-white
background: /img/city-night.jpg
---

<div class="absolute inset-0 bg-black/45 z-1"></div>

<div class="relative z-2">

# Parallel work.
# No collisions.

</div>

<!--
Visual reset. Slow down. Let the image do the work.
"This is what isolation buys you. Three agents, three branches, zero conflicts."
-->

---

# Identity

Isolation protects the system.

Identity protects authority.

Treat agents like new hires.

<!--
New hire analogy. Provision accounts. Scope secrets. No shared credentials.
"You wouldn't give a new hire the same access as a staff engineer. Why would you give it to an agent?"
-->

---
layout: center
---

You wouldn't give a new hire:

- Production DB access
- Stripe live keys
- `rm -rf /`

<!--
Smile. Short beat. Move on.
-->

---

# Skills = Progressive Disclosure

Thin `agents.md`

References `skills/`

Load capability only when needed.

Avoid context pollution.

<!--
Don't over-explain MCP. High level only.
"Think of it like progressive disclosure in UI design. The agent starts with minimal context. It loads skills on demand."
-->

---

# Definition of Done

Don't prescribe the path.

Define the destination.

Done =

- Tests pass
- OAuth verified
- E2E works
- PR reviewed

<!--
Autonomy without verification = chaos.
Verification without autonomy = micromanagement.
This is the leadership slide.
"You wouldn't tell a senior engineer which files to edit. You'd tell them what done looks like."
-->

---

# Self-Validation Loop

Fail → Patch → Rerun → Green

Human reviews only after validation passes.

<!--
This removes you as bottleneck.
"The agent catches its own regressions. You only see the work after it's proven."
-->

---
layout: center
class: text-center
---

35 review rounds.

No ego. No fatigue. No "ship it already."

Nitpicking is free when agents do it.

<!--
Slow. Let them process 35.
"I watched two agents go back and forth 35 times on a single PR. No frustration. No shortcuts. Just better code."
-->

---

# Cross-Agent Review

Build agent opens PR

Review agent comments

Loop until stable

Structural dissent by design.

<!--
Fresh set of eyes. Humans get tired. Agents don't.
"Codex builds. Gemini reviews. Different models, different blind spots. That's the point."
-->

---

# The Payoff

Not autocomplete.

Not chaos.

Teammates.

Reliable. Accountable. Safe to collaborate with.

<!--
Pause between lines. Let each one land.
-->

---
layout: center
class: text-center text-white
background: /img/earth-night.jpg
---

<div class="absolute inset-0 bg-black/50 z-1"></div>

<div class="relative z-2">

AI doesn't remove responsibility.

It redistributes it.

If you connect agents to real systems,
you are designing their blast radius.

Design it intentionally.

</div>

<!--
Slow. Calm. Stop.
"This is the one thing I want you to take away. You are the architect of your agents' blast radius. Design it on purpose."
-->

---
layout: center
class: text-center text-white
background: /img/code-artistic.jpg
---

<div class="absolute inset-0 bg-black/60 z-1"></div>

<div class="relative z-2">

# Thank you

**Rida Al Barazi**

rida.me · @rida

<div class="mt-4 text-gray-300 text-sm">

BranchBox: github.com/branchbox/branchbox

Blog posts on all of this: rida.me/blog

</div>

</div>

---
layout: center
class: text-center
---

# Feedback

<img src="/feedback-qr.png" class="w-64 h-64 mx-auto my-4" alt="Feedback QR Code" />

<div class="text-lg mt-2">

confoo.ca/f/B1E9D3155640A9D8A5F4E90DF8874288

</div>

<div class="text-gray-400 text-sm mt-4">

Scan or visit the link — your feedback helps!

</div>
