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

---
layout: center
---

# The future of coding agents
## isn't prompt engineering —
## it's environment engineering.

Environment engineering = **trust architecture**

Who can run what

Who can access what

Who can approve what

---
layout: center
---

The first time I gave an agent full access to my repo,
it felt incredible.

Then it modified files outside the feature scope.

**The agent didn't know what it wasn't allowed to touch.**

And worse — I hadn't defined that either.

---

This isn't a prompting problem.

It's a **trust architecture** problem.

---
background: /img/network-cables.jpg
class: text-white
---

<div class="absolute inset-0 bg-black/55 z-1"></div>

<div class="relative z-2">

# The Connected Agent Problem

</div>

---

Agents today can:

- Write code
- Execute commands
- Call external APIs
- Modify application state

Webhook payload → Stripe API → Database mutation

Powerful model + Tool access + Untrusted input

---
background: /img/terminal.jpg
class: text-white
---

<div class="absolute inset-0 bg-black/60 z-1"></div>

<div class="relative z-2">

# The Model

## Isolation

_where it runs_

## Identity

_what it can do_

## Feedback Loops

_how it proves itself_

</div>

---

# Isolation

feature/login-oauth
→ git worktree
→ docker compose up
→ isolated DB
→ branch-specific URL

Isolation protects boundaries.

---

# Isolation in Practice

App container
↓
Postgres
↓
Tunnel → feature-x.rida.me

Now agents can test:

- OAuth flows
- Webhooks
- Full end-to-end paths

---

# Identity

Isolation protects the system.

Identity protects authority.

---

# Identity in Practice

## Build Agent

- Repo write
- DB migrations
- Test API keys

## Review Agent

- Read-only repo
- No DB writes
- No API keys

---

Two isolated agents with identical credentials
share the same blast radius.

Treat agents like new hires.

<!--
Pause here.
"You don't give interns production database access on day one.
… unless you work at a startup."
-->

---

# Feedback Loops

Validation:

- Unit tests
- End-to-end tests

Accountability:

- Cross-agent review
- Human merge

---

An agent without verification
is just autocomplete with confidence.

---

# Agentic Lifecycle

Spec
→ Worktree
→ Container
→ Build
→ Validate
→ Review
→ Merge

```bash
npx playwright test oauth-flow.spec.ts
```

---
layout: center
class: text-center bg-black text-white
---

The agent finishes.

You don't trust it.

You become the bottleneck.

<!--
Pause. Let it sit.
-->

---

# Self-Validation Loop

Failing test
↓
Patch
↓
Rerun
↓
Green

Human reviews only after validation passes.

---

# Cross-Agent Review as Architecture

Single-agent workflow = one actor owns lifecycle.

Human teams separate build & review.

Cross-agent review = separation of concerns applied to agents.

Codex builds. Gemini reviews.

Structural dissent enforced by identity boundaries.

---

# The Payoff

Not autocomplete.

Not chaos.

Teammates.

Reliable. Accountable. Safe to collaborate with.

---

# Reference Implementation

branch → worktree → container → tunnel → agent

Encoded as one abstraction.

It's open source.

Clone it. Spin up a branch. See the model in action.

---
layout: center
class: text-center text-white
background: /img/earth-night.jpg
---

<div class="absolute inset-0 bg-black/50 z-1"></div>

<div class="relative z-2">

Until containment is default,
trust architecture is your responsibility.

Agents are powerful because they're connected.

Reliability comes from environment design.

Isolation defines where agents run.

Identity defines what they're allowed to do.

Feedback loops define when they're done.

</div>

---

# The future of coding agents

## isn't prompt engineering.

## It's environment engineering.

---
layout: center
class: text-center text-white
background: /img/code-artistic.jpg
---

<div class="absolute inset-0 bg-black/60 z-1"></div>

<div class="relative z-2">

# 🙏 Thank you

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

# 📝 Feedback

<img src="/feedback-qr.png" class="w-64 h-64 mx-auto my-4" alt="Feedback QR Code" />

<div class="text-lg mt-2">

confoo.ca/f/DA39E62348AF40D2BBD8A4F9B51A2B00

</div>

<div class="text-gray-400 text-sm mt-4">

Scan or visit the link — your feedback helps!

</div>
