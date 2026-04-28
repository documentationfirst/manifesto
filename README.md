<div align="center">

# Documentation-Driven Development (DDD)
### A Manifesto for Human–AI Collaborative Software Engineering

[![Version](https://img.shields.io/badge/version-1.0-3fb950?style=flat-square)](https://documentationfirst.ai)
[![License](https://img.shields.io/badge/license-CC%20BY%204.0-a855f7?style=flat-square)](https://creativecommons.org/licenses/by/4.0/)
[![Website](https://img.shields.io/badge/website-documentationfirst.ai-58a6ff?style=flat-square)](https://documentationfirst.ai)
[![GitHub](https://img.shields.io/badge/GitHub-documentationfirst%2Fmanifesto-30363d?style=flat-square&logo=github)](https://github.com/documentationfirst/manifesto)

*April 2026 — Built on [zsup's 2014 foundation](https://gist.github.com/zsup/9434452). Extended for the AI era.*

</div>

---

## Table of Contents

- [Roots & Prior Art](#roots--prior-art)
- [What is DDD?](#what-is-ddd)
- [The Problem DDD Solves](#the-problem-ddd-solves)
- [The Core Principle](#the-core-principle)
- [DDD as Context Engineering](#ddd-as-context-engineering)
- [The 3S Rule](#the-3s-rule--what-makes-a-good-context-document)
- [The DDD Loop](#the-ddd-loop)
- [The Four DDD File Types](#the-four-ddd-file-types)
- [Why Markdown?](#why-markdown)
- [The Reconstruction Guarantee](#the-reconstruction-guarantee)
- [Real-World Proof](#real-world-proof-legends-of-the-future-past-1992)
- [Language Agnostic](#language-agnostic)
- [Portability](#portability)
- [Contextual Adaptation](#contextual-adaptation)
- [DDD as Knowledge Capital](#ddd-as-knowledge-capital)
- [A Call for a New Kind of License](#a-call-for-a-new-kind-of-license)
- [The IDE-First Ecosystem](#the-ide-first-ecosystem)
- [DDD & MCP — Advanced Integration](#ddd--mcp--advanced-integration)
- [DDD & Contextual Memory Tools](#ddd--contextual-memory-tools)
- [DDD Tooling Roadmap](#ddd-tooling-roadmap)
- [What's Next](#whats-next)
- [Getting Started](#getting-started)
- [Support the Manifesto](#support-the-manifesto)
- [Documentation First Certification](#documentation-first-certification)
- [Contribute](#contribute)

---


## Roots & Prior Art

Documentation-Driven Development is not a new idea.

In 2014, **zsup** published a foundational definition:
> *"Documentation-Driven Development is the practice of writing the documentation before writing the code. If you can't explain it clearly, you don't understand it yet."*
> — [gist.github.com/zsup/9434452](https://gist.github.com/zsup/9434452)

This was later expanded by others (see [Andrew's article on Medium](https://buildwithandrew.medium.com/whats-documentation-driven-development-4b007f4de6a1)) into a broader practice: write user-facing documentation, API specs, and feature descriptions **before** writing any implementation — making documentation the first test of clarity.

**This manifesto builds on that foundation — and extends it into the AI era.**

| DDD v1 (2014) | DDD v2 — this manifesto (2026) |
|---|---|
| Write docs *before* code | Docs are *persistent infrastructure*, not a phase |
| Human-to-human communication | Human-to-human *and* human-to-AI communication |
| Spec-first for APIs and features | Context-first for the entire project lifecycle |
| Documentation as clarity check | Documentation as the executable contract and Knowledge Capital |
| One author, one moment | Continuous, multi-agent co-authorship |

We stand on the shoulders of zsup and the DDD community.
We extend their work for a world where **AI agents are first-class contributors**.

---

## What is DDD?

**Documentation-Driven Development** is a software engineering approach where **Markdown documentation files are the single source of truth** that drives the entire development lifecycle — for both humans and AI agents.

In DDD, documentation is not written *after* the code. It is written *before*, *during*, and *instead of* many conversations — because it persists, it versions, and it can be read by anyone in the loop: developers, product owners, architects, and AI agents.

---

## The Problem DDD Solves

Modern AI coding agents are powerful but **stateless**. Every new session starts from zero. Without a persistent shared context, teams lose:

- The reasoning behind architectural decisions
- The migration history and what was already done
- The rules and conventions the AI should follow
- The ability to onboard a new agent (or a new developer) quickly

The traditional answer was "write better comments" or "maintain a wiki". But wikis rot. Comments lie. And AI agents can't read Confluence.

**DDD solves this by making documentation the executable contract of the project.**

---

## The Core Principle

> *If it's not in a `.md` file, it doesn't exist.*

Every decision, every convention, every migration step, every architectural rule — lives in a versioned Markdown file, committed alongside the code.

---

## DDD as Context Engineering

A new discipline is emerging in AI-assisted development: **Context Engineering** — the practice of deliberately designing, structuring, and maintaining the information an AI agent needs to perform at its best.

DDD *is* Context Engineering — applied to software teams.

Where Context Engineering describes the *what* (give the AI the right context), DDD describes the *how*:

### The 3S Rule — What Makes a Good Context Document

A DDD context document is not just any Markdown file. Every `.md` file in `.ai_context/` should satisfy the **3S Rule**:

| 3S | Principle | Meaning |
|---|---|---|
| **Selected** | Only what the agent needs | Don't dump everything — choose what is relevant to the task, the feature, or the constraint. Noise kills context. |
| **Synthetic** | Summarised, not verbose | Each document should be as short as possible while being complete enough to act on. Avoid copy-pasting raw logs or long prose — distill to the essential. |
| **Structured** | Formatted for AI consumption | Use Markdown headings, bullet points, tables, and code blocks. Flat walls of text are hard for agents (and humans) to parse. Structure is clarity. |

> *A document that is Selected, Synthetic, and Structured is a document the agent can actually use.*

This rule applies to every file type in the DDD taxonomy: specs, technical notes, best practices, and execution reports.



| Context Engineering concept | DDD implementation |
|---|---|
| Persistent context across sessions | Versioned `.md` files committed in the repo |
| Structured knowledge base | `.ai_context/` folder organized by domain |
| Role-specific information | `specs-functional.md` (PO) vs `specs-technical.md` (dev) |
| Behavioral rules and constraints | `best-practices.md` — always read first |
| Execution trace and auditability | `DONE.md` — written by the AI after each task |
| Context scoping | One subfolder per feature, migration, or domain |

The key insight is that **context is not a prompt — it is infrastructure**.

A one-shot prompt disappears after the session. A well-structured `.ai_context/` folder is permanent, versionable, shareable, and improvable. It turns ephemeral AI interactions into a **durable, compounding asset** for the entire team.

> *Context Engineering asks: "what does the AI need to know?"*
> *DDD answers: "everything — and it lives in `.md` files."*

---

## The DDD Loop

```
┌─────────────────────────────────────────────────────────────────┐
│                        THE DDD LOOP                             │
│                                                                 │
│   Product Owner                                                 │
│       │  defines specs and acceptance criteria in .md           │
│       ▼                                                         │
│   Developer                                                     │
│       │  enriches .md with conventions, rules, constraints      │
│       ▼                                                         │
│   AI Agent                                                      │
│       │  reads .md → executes → updates .md with what was done  │
│       ▼                                                         │
│   Developer / PO                                                │
│       │  reviews output → corrects .md → loops                  │
│       └─────────────────────────────────────────────────────────┘
```

The `.md` files are simultaneously:

| Role | Description |
|---|---|
| **Spec** | What we want to build |
| **Contract** | The rules every contributor must follow |
| **Journal** | What was done, why, and how |
| **Reconstruction kit** | Everything needed to rebuild from scratch |

---

## The Four DDD File Types

### 1. `best-practices.md`
Rules, conventions, and patterns the AI **must** follow. Updated as the team learns.

### 2. `migration-xxx.md`
Instructions for a specific migration or refactoring. Written *before* execution. Acts as a prompt and a checklist.

### 3. `MIGRATION_DONE.md` (or equivalent)
The execution report. Written *by the AI* after completing the task. Describes every change made, every decision taken, and every trade-off.

### 4. `docs/*.md`
Deep-dive documentation on specific topics (zoneless Angular, RxJS vs signals, testing patterns, etc.). The AI reads these to understand the project's technical philosophy.

---

## Why Markdown?

- **Universal** — every editor, every platform, every tool reads it
- **Versionable** — Git tracks every change, every author, every date
- **LLM-friendly** — AI agents parse Markdown natively and efficiently
- **Human-readable** — no special tooling required
- **Publishable** — renders instantly on GitHub, GitHub Pages, Notion, Confluence

---

## The Reconstruction Guarantee

> *The project must be fully reconstructible from its `.md` files alone.*

If a new developer joins, or a new AI agent session starts, or the entire codebase is lost — the `.md` files must contain enough information to:

1. Understand the project's purpose and architecture
2. Know every rule and convention to follow
3. Reproduce every migration or refactoring step
4. Make correct decisions in ambiguous situations

This is the ultimate test of a DDD-compliant project.

---

## Real-World Proof: *Legends of the Future Past* (1992)

> 🕹️ **The game that proved documentation outlives code.**

**Legends of the Future Past** is a MUD (Multi-User Dungeon) that went offline and stayed dark for decades.
In 2026, it came back online — not because someone had the original server code, but because the
**structured text files describing the world** had survived: zones, characters, rules, quests, lore.

The executable was gone. The documentation was not. The game was rebuilt from its data files alone.

> [Read the story on Reddit →](https://www.reddit.com/r/MUD/comments/1sexcyd/legends_of_future_past_1992_is_back_online/)

This is the ultimate demonstration of the DDD Reconstruction Guarantee.
In software engineering, your `.md` files *are* those data files.
The codebase can be rewritten by any competent developer — or any AI agent.
The **context** — decisions, conventions, architecture, history — cannot be recovered if it was never written down.

> *Code is temporary. Documentation is permanent.*

---

## Language Agnostic

DDD is **not tied to any language, framework, or toolchain**.

The `.md` files describe *intent*, *rules*, and *context* — not syntax. The same DDD approach works whether your stack is Angular, React, Spring Boot, Django, Rust, or anything else. When you migrate from one framework to another, the documentation survives the migration. Only the code changes.

> *Your `.md` files will still be valid the day you switch from Angular to something that doesn't exist yet.*

---

## Portability

Because DDD documentation lives in plain Markdown files committed alongside the code, it is **infinitely portable**:

- Move from GitHub to GitLab? The docs follow.
- Switch from GitHub Copilot to Claude to a local model? The docs follow.
- Onboard a new team member or a new AI agent? Hand them the `.ai_context/` folder.
- Fork the project? The entire context forks with it.

No vendor lock-in. No proprietary format. No special tooling required to read, write, or update.

---

## Contextual Adaptation

DDD documentation is **living documentation** — it evolves with the project.

When a new constraint is discovered, a new `.md` entry is added. When a convention is invalidated, the file is updated and the change is committed with a clear message. When a migration introduces breaking decisions, the execution report captures every trade-off.

This means the AI agent always operates on **the current truth**, not a stale snapshot:

| Event | DDD Response |
|---|---|
| New framework version available | Update `migration-xxx.md`, execute, update `MIGRATION_DONE.md` |
| Convention changed by the team | Update `best-practices.md`, commit |
| New architectural constraint | Add entry in `docs/`, reference it in `best-practices.md` |
| AI produced something wrong | Correct the relevant `.md`, re-run — the error won't happen again |

> *Every correction makes the documentation smarter. Every session improves the next one.*

---

## DDD is not

- ❌ A replacement for code comments
- ❌ A wiki that nobody maintains
- ❌ A one-time README
- ❌ An AI-only practice
- ❌ About generating documentation from code (the opposite)

---

## DDD is

- ✅ A living contract between all contributors — human and AI
- ✅ A forcing function for clarity: if you can't write it in a `.md`, you don't understand it yet
- ✅ The answer to AI agent statelessness
- ✅ Applicable to any language, any framework, any team size
- ✅ Compatible with any AI coding agent (GitHub Copilot, Cursor, Claude, etc.)

---


## DDD as Knowledge Capital

In traditional software engineering, the intellectual property of a project lives in its code.
In DDD, this assumption is inverted.

**The real intellectual property is the documentation.**

The code is an artifact — a snapshot of one implementation, in one language, at one point in time.
It can be rewritten, refactored, or replaced entirely. It frequently is.

The `.md` files are something different. They encode:

- **Why** decisions were made — not just what was decided
- **What was tried and failed** — and why it failed
- **The constraints** that shaped every architectural choice
- **The domain knowledge** accumulated by the team over months or years
- **The conventions** that make the codebase coherent

This is **Knowledge Capital** — the compounding intellectual asset of the team.
It grows with every session, every correction, every new `.md` entry.
Unlike code, it does not become legacy. It becomes richer.

> *A team that loses its codebase can rebuild. A team that loses its Knowledge Capital starts from zero.*

---

## A Call for a New Kind of License

Current open-source licenses (MIT, Apache, GPL, CC BY) were designed for **artifacts** — files that exist at a point in time.

DDD documentation is not an artifact. It is a **living, compounding context** — something closer to a methodology, a knowledge base, and a collaborative memory than a static file.

We propose the concept of a **Living Knowledge License** — a license that recognizes:

| Traditional license assumption | Living Knowledge License assumption |
|---|---|
| The value is in the artifact | The value is in the accumulated context |
| A copy is equivalent to the original | A fork diverges and must be maintained separately |
| Authorship is a moment in time | Authorship is a continuous, multi-agent contribution |
| The license governs distribution | The license governs contribution, attribution, and evolution |

This is not a formal legal license — yet. It is a call for the open-source community to recognize that **AI-assisted, documentation-driven projects represent a new category of intellectual property** that existing licenses were not designed to protect or govern.

**The questions we need to answer:**

- Who owns the Knowledge Capital when an AI agent contributes to it?
- How should attribution work when a `.md` file is co-authored by a developer, a PO, and an AI?
- What are the obligations of a fork that builds on accumulated DDD context?
- How do we license a methodology, not just its output?

Until the community answers these questions, DDD projects are published under **CC BY 4.0** — with the explicit acknowledgment that this license is a placeholder, not a solution.

> *The code belongs to the license. The context belongs to the team. We need a license that understands the difference.*

---

## The IDE-First Ecosystem

DDD's primary interface is **your IDE and its built-in AI agent** — not a chat window, not an external tool.

The `.md` files live in the repository. The AI agent lives in the IDE. The developer stays in flow.

```
┌─────────────────────────────────────────────────────────────┐
│                   THE IDE-FIRST LOOP                        │
│                                                             │
│   .ai_context/ (in repo)                                    │
│         │                                                   │
│         ▼  attached / referenced by the developer           │
│   IDE Agent (Copilot, JetBrains AI, Cursor, Windsurf...)    │
│         │                                                   │
│         ▼  reads context → executes → updates .md           │
│   Code + updated DONE.md                                    │
│         │                                                   │
│         ▼  reviewed and committed by the developer          │
│   Git — versioned snapshot of code AND context              │
└─────────────────────────────────────────────────────────────┘
```

This is not MCP. This is not an external service. This is a **local, zero-dependency, agent-agnostic workflow** that works with any IDE and any AI agent — today, without any additional tooling.

MCP and other context protocols are valid extensions for advanced use cases (multi-agent, shared context servers), but they are **not required** and not the primary use case.

---

## DDD & MCP — Advanced Integration

**Model Context Protocol (MCP)** is an open standard by Anthropic that allows AI agents to connect to external context sources (files, APIs, databases, tools) in a structured and interoperable way.

DDD and MCP are **complementary, not competing**. MCP provides the *transport layer*. DDD provides the *structured, versioned content* worth transporting.

### How they map to each other

| DDD concept | MCP equivalent |
|---|---|
| `.ai_context/` folder | **MCP Resources** — files exposed to the agent |
| `README_AI.md` / agent contract | **MCP System Prompt** — instructions injected at session start |
| `best-practices.md` | **MCP Prompt template** — reusable, named prompt |
| Interaction profiles (strict / standard / open) | **MCP Tool permissions** — scoped access control |
| DDD IDE Plugin | **MCP Client** — the IDE becomes the MCP client |
| Agent context server | **MCP Server** — local or remote, exposing DDD files |

### Architecture in an MCP-enabled DDD project

```
IDE (IntelliJ / VSCode)
  └── DDD Plugin (MCP Client)
        ├── exposes .ai_context/  → MCP Resources
        ├── exposes README_AI.md  → MCP System Prompt
        ├── exposes templates/    → MCP Prompt Templates
        └── connects to ──────→  AI Agent (Claude, Copilot, etc.)
                                        via local MCP Server
```

### When to use MCP with DDD

MCP becomes relevant when:

- **Multiple agents** collaborate on the same project (e.g. a planning agent + a coding agent)
- **Shared context servers** are needed across a team (one MCP server, many IDE clients)
- **Dynamic context** is required (the server queries a database or live API to enrich the `.md` context)
- **Audit and traceability** of context injection is required at the infrastructure level

For individual developers working in a single IDE, **MCP is not required** — the DDD local workflow is sufficient and simpler.

### The DDD Plugin as an MCP Server

The planned DDD IDE plugins (JetBrains, VSCode) can optionally expose a local MCP server endpoint, making the `.ai_context/` context available to any MCP-compatible agent — including Claude Desktop, custom agents, or CI pipelines.

```json
// mcp-server-config.json (optional, in .ai_context/)
{
  "name": "ddd-context-server",
  "version": "1.0.0",
  "resources": [
    { "uri": "file://.ai_context/**/*.md", "description": "Project DDD context" }
  ],
  "prompts": [
    { "name": "agent-contract", "file": "README_AI.md" },
    { "name": "best-practices", "file": "best-practices.md" }
  ]
}
```

> *MCP makes DDD context portable across agents. DDD makes MCP context meaningful and maintained.*

---

## DDD & Contextual Memory Tools

A new category of tools has emerged alongside MCP: **contextual memory layers** — systems that give AI agents persistent, semantic memory across sessions.

Examples: **Mem0**, **Zep**, **Mempalace**, **Letta (MemGPT)**.

These tools store facts, preferences, and past interactions in a vector database, and automatically surface relevant memories when the agent needs them.

### How they differ from DDD

| Dimension | DDD (`.ai_context/`) | Memory tools (Mem0, Zep...) |
|---|---|---|
| What is stored | Structured rules, specs, decisions | Implicit facts, conversation history, preferences |
| Who writes it | Developers and POs — deliberately | The agent — automatically |
| Versionable | ✅ Yes — committed in Git | ❌ No — opaque vector store |
| Shareable with the team | ✅ Yes | ❌ No — personal or session-scoped |
| Auditable | ✅ Yes | ❌ Rarely |
| Works with GitHub Copilot | ✅ Yes (via file attachment) | ❌ No — Copilot is a closed environment |
| Works with Claude, Cursor, Cline | ✅ Yes | ✅ Yes — via MCP or SDK |

### The key insight

Memory tools and DDD operate at **different layers of memory**:

```
┌─────────────────────────────────────────────────────┐
│              AI AGENT MEMORY LAYERS                 │
│                                                     │
│  Semantic memory  ←  Mem0 / Zep / Mempalace         │
│  "you told me that..."                              │
│                                                     │
│  Structured context  ←  DDD (.ai_context/)          │
│  "it is written in best-practices.md"               │
│                                                     │
│  Transport layer  ←  MCP                            │
│  (delivers both layers to the agent automatically)  │
└─────────────────────────────────────────────────────┘
```

### Is a memory layer necessary alongside DDD?

> 🧪 **Working Hypothesis** — *If you practice DDD correctly, you don't need a contextual memory layer. A well-maintained `.ai_context/` folder is a strictly superior alternative: explicit, versionable, auditable, and infrastructure-free. This hypothesis guides all DDD tooling decisions.*

**In most cases: no.**

Memory tools add complexity, infrastructure cost, and opacity — in exchange for automating something DDD already does better, explicitly.

Apply this test:
> *If it's important enough for the agent to remember, it's important enough to be in a `.md` file.*

Implicit memory is a shortcut that creates **context debt** — exactly the problem DDD is designed to eliminate.

| Problem with memory tools | DDD solution |
|---|---|
| Opaque — you don't know what the agent "remembers" | Explicit — you know exactly what it read |
| Degrades over time — old memories pollute new decisions | Always current — the `.md` reflects the current truth |
| Infrastructure overhead — vector DB, embeddings, always-on | Zero infrastructure — plain files in Git |
| Not versionable — no audit trail | Fully versionable — every change is a commit |
| Breaks with closed agents (Copilot) | Works everywhere |

| Situation | DDD alone | DDD + Memory tool |
|---|---|---|
| Single developer, one IDE (Copilot) | ✅ Sufficient | ❌ Not compatible |
| Team sharing rules and conventions | ✅ Sufficient | ➖ Not needed |
| Multi-session personal preferences | ⚠️ Manual effort | ✅ Marginal value |
| Multi-agent pipelines (Claude, Cursor...) | ✅ Sufficient | ✅ Complementary |
| Enterprise: shared context across teams | ✅ via Git | ➖ Adds infrastructure cost |

Memory tools may add marginal value in **highly personal, conversational, multi-session** workflows — but for team-scoped, project-scoped, or agent-scoped context, DDD is strictly superior.

> *What you want the team to remember → DDD. What the agent learns about you personally → memory tools, if you accept the trade-offs. When in doubt: write a `.md`.*

---

## DDD Tooling Roadmap

DDD works today with any IDE. The next step is **native IDE support** — plugins that make DDD a first-class citizen of the development environment.

### JetBrains Plugin (IntelliJ, WebStorm, Rider...)

- Auto-detects `.ai_context/` in the project
- **Templates by language/framework** at project init (Angular, Spring Boot, Python, Rust...)
- Injects the relevant `.md` files into the **JetBrains AI agent context** automatically
- UI panel to create, edit, and browse DDD files without leaving the IDE
- "DDD Ready" project badge in the project tree

### VSCode / Cursor / Windsurf Plugin

- Same auto-detection and template system
- Generates `.cursorrules`, `CLAUDE.md`, `COPILOT_INSTRUCTIONS.md` from the `best-practices.md`
- Compatible with all major AI extensions (GitHub Copilot, Cursor, Continue, Cline...)
- Command palette integration: `DDD: New feature context`, `DDD: New migration plan`, `DDD: View DONE.md`

### Why IDE-first matters

| Approach | Context delivery | Session persistence | Vendor lock-in |
|---|---|---|---|
| Copy-paste to chat | Manual, per session | None | High |
| MCP server | Automated, external | Partial | Medium |
| **DDD + IDE plugin** | **Automated, local** | **Full (committed)** | **None** |

The plugin eliminates the only remaining friction in DDD: manually attaching files to the agent context. With the plugin, **the context is always ready — because it lives in the repo.**

---

## What's Next

> Ideas under exploration — not yet implemented, but guiding the direction of DDD tooling.

### 💬 Conversation-to-Document: Closing the Last Gap

The DDD loop has one remaining blind spot: **the conversation itself**.

Every meaningful session with an AI agent produces decisions, trade-offs, and discoveries. Today, those disappear when the session closes. They live nowhere — not in the code, not in the `.md` files, not in Git.

The proposed solution: a plugin feature that **reads the current conversation and transforms it into a structured, editable DDD document**.

Not a raw transcript — a **synthesized extraction**:

```
Conversation (16/04/2026) — ng-idle removal
  ↓  plugin analyses and proposes
decisions.md       ← "decided to remove ng-idle because Zone.js dependency"
best-practices.md  ← "new rule: avoid Zone-dependent libraries"
DONE.md            ← "what was done during this session"
```

The developer reviews, adjusts, and commits. **The conversation becomes Knowledge Capital.**

#### The three principles of this feature

| Principle | Rationale |
|---|---|
| **Extract, don't dump** | A raw transcript is noise. The plugin extracts what deserves to be permanent. |
| **Propose, don't auto-commit** | The human validates what enters the `.md`. No silent writes. |
| **`.md` first, not vector memory** | The output is editable Markdown — versionable, auditable, readable by any agent. |

> *The conversation is the raw material. The plugin proposes. The developer decides what becomes documentation.*

This is the final piece of the DDD loop — making sure **nothing that matters gets lost between sessions**.

---

## Getting Started

### Step 1 — Create the `.ai_context/` folder structure

Organize documentation by context, each in its own versioned subfolder:

```
.ai_context/
├── best-practices.md          ← global rules & conventions for the AI
├── docs/                      ← deep-dive technical references
│   ├── RXJS_SIGNALS.md
│   ├── ZONELESS_MIGRATION.md
│   └── ...
├── features/                  ← one subfolder per functional domain
│   ├── authentication/
│   │   ├── specs-functional.md    ← functional specifications (PO-owned)
│   │   ├── specs-technical.md     ← technical specifications (dev-owned)
│   │   └── DONE.md                ← execution report (AI-written)
│   └── notifications/
│       ├── specs-functional.md
│       ├── specs-technical.md
│       └── DONE.md
└── migrations/                ← one subfolder per migration or refactoring
    ├── angular-21/
    │   ├── migration-plan.md
    │   └── MIGRATION_DONE.md
    └── ...
```

### Step 2 — Write the functional specifications

In each feature subfolder, create a `specs-functional.md`. This is **PO territory** — written in business language, no code:

- User stories and acceptance criteria
- Business rules and edge cases
- Expected behaviors and error scenarios
- Links to mockups or design files

### Step 3 — Write the technical specifications

In the same subfolder, create a `specs-technical.md`. This is **dev territory**:

- Architecture decisions and patterns to follow
- API contracts, data models, component structure
- Dependencies, constraints, known risks
- References to relevant `docs/*.md` files

### Step 4 — Write `best-practices.md`

Global rules the AI **must** follow on every task — naming conventions, coding patterns, what to avoid, which libraries to use. This file is always read first.

### Step 5 — Prompt as a User Story or ticket

When asking the AI to execute a task, frame your prompt exactly like a **User Story or a Jira/Linear/GitHub issue**:

```
As a [role], I want [feature] so that [outcome].

Acceptance criteria:
- [ ] ...
- [ ] ...

Technical context: see .ai_context/features/authentication/specs-technical.md
Rules to follow: see .ai_context/best-practices.md
```

This works with any system — Jira, Linear, GitHub Issues, Notion, or even a personal note. The point is: **the ticket references the `.md` files, not the other way around.**

### Step 6 — Let the AI execute and report

Ask the AI agent to:
1. Read the relevant `specs-functional.md` and `specs-technical.md`
2. Execute the task following `best-practices.md`
3. Write or update the `DONE.md` with every change made, every decision taken, every trade-off

### Step 7 — Commit everything

Commit the `.md` files alongside the code, with meaningful messages:

```
feat(auth): implement login flow

See .ai_context/features/authentication/DONE.md for full execution report.
```

Every commit is a versioned snapshot of both the code **and** its context.

---

## Support the Manifesto

DDD is free, open, and will stay that way.
If it improved your workflow or sparked a conversation in your team — consider supporting the project:

| Platform | Link |
|---|---|
| ❤️ Patreon | [patreon.com/documentationfirst](https://www.patreon.com/documentationfirst) |
| ☕ Buy Me a Coffee | [buymeacoffee.com/documentationfirst](https://buymeacoffee.com/documentationfirst) |
| 🎨 Ko-fi | [ko-fi.com/documentationfirst](https://ko-fi.com/documentationfirst) |
| 💜 GitHub Sponsors | [github.com/sponsors/documentationfirst](https://github.com/sponsors/documentationfirst) |

Every contribution helps maintain the manifesto, grow the community, and work toward the **Living Knowledge License**.

---

## Documentation First Certification

The **Documentation First Certification** is a structured audit and recognition program for teams and organizations that have adopted DDD practices.

### What it includes

- **Audit** — a structured review of your `.ai_context/` folder, your DDD loop, and your team's practices
- **Certificate** — a dated, versioned certificate recognizing your organization as *Documentation First Certified*
- **Badge** — a digital badge for your GitHub repo, with a verification link proving authenticity
- **Annual renewal** — ensuring your practices stay current as DDD evolves with the AI landscape

### Founding Member Program

Certification is currently in its **founding program** — early adopters get a *Founding Member* status and a reduced rate. Limited spots available.

📩 Apply: [certification@documentationfirst.ai](mailto:certification@documentationfirst.ai)

---

## Contribute

This manifesto is open and versionable. Fork it, adapt it, improve it.
Every team will develop its own DDD vocabulary — and that's the point.

The only rule: **the documentation drives the development, not the other way around.**

---

*Documentation-Driven Development — v1.0 — April 2026*
*Published under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)*
*Website: [documentationfirst.ai](https://documentationfirst.ai)*
*GitHub: [github.com/documentationfirst/manifesto](https://github.com/documentationfirst/manifesto)*

