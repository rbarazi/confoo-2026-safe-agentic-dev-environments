---
theme: default
title: Safe Agentic Coding
info: |
  Environment Engineering for Reliable AI Teammates
class: text-center
drawings:
  persist: false
transition: slide-left
---

# Safe Agentic Coding

### Environment Engineering for Reliable AI Teammates

Rida Al Barazi · ConFoo 2026

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

# The Connected Agent Problem

Agents today can:

- Write code
- Execute commands
- Call external APIs
- Modify application state

Webhook payload → Stripe API → Database mutation

Powerful model + Tool access + Untrusted input

---

# The Model

## Isolation

_where it runs_

## Identity

_what it can do_

## Feedback Loops

_how it proves itself_

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
class: text-center
---

Until containment is default,
trust architecture is your responsibility.

Agents are powerful because they're connected.

Reliability comes from environment design.

Isolation defines where agents run.

Identity defines what they're allowed to do.

Feedback loops define when they're done.

---

# The future of coding agents

## isn't prompt engineering.

## It's environment engineering.

---

# 🎤 Notes About This Deck

- Slidev supports speaker notes using HTML comments (`<!-- -->`)
- You can enhance it with:
  - `layout: two-cols`
  - Mermaid diagrams
  - Animated fragments
  - Live coding blocks
- You can export to PDF or host on Vercel/GitHub Pages

---

# 🚀 If You Want Next-Level

We can:

- Add animated fragments for pacing
- Add Mermaid diagrams for architecture visuals
- Add a live isolation demo slide
- Add controlled meme slides
- Add dark/light theme transitions for emotional beats

---

This version is clean, technical, and ConFoo-ready.

Want me to:

- Add tasteful meme slides?
- Add diagram visuals?
- Or tighten it for a 25-minute slot?
