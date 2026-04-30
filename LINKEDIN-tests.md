# LinkedIn Post — Documentation-Driven Development

> Copy-paste ready. Two versions: **Short** (hook post) and **Long** (full manifesto post).

---

## ✦ Version courte — Hook post

🧠 **AI agents aren't dumb. They're amnesiac.**

Every new session starts from zero. No context. No conventions. No history.

The fix isn't a better prompt. It's infrastructure.

---

I call it **Documentation-Driven Development v2**.

The idea is simple:

> *If it's not in a `.md` file — it doesn't exist.*

Every architectural decision. Every convention. Every migration step. Versioned in Markdown, committed alongside the code, readable by both humans and AI agents.

The AI doesn't "remember." It **reads the docs.**

---

The structure:

```
.ai_context/
├── CONTRACT.md     ← agent rules (permanent)
├── CONTEXT.md      ← current work
├── skills/         ← who the agent is on this project
└── documents/
    ├── specification/  ← PO specs
    ├── technical/      ← dev decisions
    └── done/           ← AI writes here after each task
```

One rule: **the AI writes in `done/`. The human reviews. Git tracks everything.**

Why? Because Microsoft Research just proved it:
19 frontier models, 52 documents, 20 interactions → **~25% of content silently corrupted.**
No plateau at 100 interactions. Agentic setups: +6% worse.

The documents are not the AI's to modify. They're the team's to maintain.

---

The result?

✅ Any agent picks up exactly where the last session left off
✅ Any dev understands the project in minutes
✅ The project is **reconstructible from its `.md` files alone**

Plain Markdown. Git. Zero lock-in. Works with Copilot, Cursor, Claude, anything.

**Context is not a prompt. It is architecture.**

👉 Full manifesto + IDE plugins (JetBrains & VSCode): [documentationfirst.ai](https://documentationfirst.ai)

#DDD #ContextEngineering #AI #SoftwareEngineering #KnowledgeCapital #DocumentationFirst

---

## ✦ Version longue — Manifesto post

🚀 **I've been working with AI coding agents for months. Here's the single most important thing I learned.**

The problem with AI agents isn't intelligence. It's **memory**.

Every new session starts from zero. No context. No history. No conventions. You spend 20 minutes re-explaining the project before getting anything useful done.

So I flipped the model.

Instead of explaining the project to the AI — **I document it for the AI.**

I call this **Documentation-Driven Development v2 (DDD)**. Not a new term — zsup defined it in 2014: *"write the docs before the code."* A great idea. In 2026, with AI agents in the loop, it's no longer optional. It's the missing infrastructure.

The key insight: **context is not a prompt. It is architecture.**

A prompt disappears after the session. A versioned `.md` file is permanent, forkable, and gets smarter over time.

One rule stands at the heart of it: **the 3S Rule**.
Every context document must be **Selected** (only what's relevant), **Synthetic** (distilled, not dumped), and **Structured** (headings, bullets, tables). Noise kills context. Structure is clarity.

---

The structure is simple:

```
.ai_context/
├── CONTRACT.md      ← agent profile: strict / standard / permissive
├── CONTEXT.md       ← current context: title, description, todos
├── skills/          ← reusable agent knowledge (permanent-* survives contexts)
└── documents/
    ├── specification/  ← PO writes specs before dev starts
    ├── technical/      ← Dev writes architecture decisions
    └── done/           ← AI writes execution reports after each task
```

The fundamental rule: **the AI only writes new files in `done/`. It never modifies existing docs. The developer reviews and commits. Git tracks everything.**

---

**Why does this matter? Because there's now empirical proof.**

🔬 Microsoft Research, April 2026 — **"LLMs Corrupt Your Documents When You Delegate"**

19 frontier models · 52 documents · 20 interactions each:
- Top-tier models: **~25% of content corrupted**
- Average across all models: **~50%**
- At 100 interactions: no plateau — monotonic decline
- With agentic tools (web, code): **+6% additional degradation**

The only domain that held? Python code — mechanically verifiable, compiler-checked. Everything else? Silently degraded. Small confident changes: a detail shifted, a nuance dropped, a meaning altered. Invisible on a quick scan.

Christian Ekrem puts it perfectly: *"The theory dies twice — you didn't build the understanding because you delegated, and the LLM corrupted the artifact. You've lost both the map and the territory."*

DDD is the structural answer:
📌 AI writes **new files** in `done/` — never modifies existing docs
📌 Developer **reviews and commits** — no silent writes
📌 Git **tracks everything** — corruption is detectable and reversible
📌 `skills/permanent-*` are **human-written** — never AI-modified

---

And there's a historical proof too.

🕹️ **Legends of the Future Past** — a MUD from 1992 — just came back online in 2026.
Not because someone had the server code. Because the **structured text files describing the world** had survived.
The game was rebuilt from its data files alone. Your `.md` files are those data files.

---

Three things I didn't expect when I started:

**🌐 Language agnostic** — docs describe intent, not syntax. Angular today, something else tomorrow? The docs survive every migration. Only the code changes.

**📦 Fully portable** — plain Markdown in Git. Switch AI agents, switch IDEs. The context follows. Zero lock-in.

**🔄 Contextual adaptation** — every correction sharpens the next session. The AI made a mistake → fix the `.md` → it won't happen again. The system learns because the team writes it down.

---

DDD is **IDE-first**. Not a chat window. Not an external platform.

```
.ai_context/ in the repo
    → referenced in your IDE agent (Copilot, JetBrains AI, Cursor…)
    → AI reads, executes, writes done/*.md
    → you review, commit code + docs together
```

Zero infrastructure. Just Markdown files, versioned in Git.

The real intellectual property of a project isn't the code. It's the documentation.
The code is a snapshot. The `.md` files encode *why* decisions were made, *what failed*, *what the team learned*. That's **Knowledge Capital** — and it compounds.

*A team that loses its codebase can rebuild. A team that loses its Knowledge Capital starts from zero.*

---

Full manifesto + IDE plugins (JetBrains & VSCode, open source): [documentationfirst.ai](https://documentationfirst.ai)

☕ Support: Patreon · Ko-fi · GitHub Sponsors
🏆 Documentation First Certification — founding spots open

Would love to hear how your team manages context with AI agents 👇

#AI #SoftwareEngineering #DeveloperExperience #DocumentationDrivenDevelopment #DDD #ContextEngineering #KnowledgeCapital #OpenSource #Copilot #Cursor #JetBrains #LLM #IDEFirst
