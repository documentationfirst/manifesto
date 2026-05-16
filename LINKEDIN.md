# LinkedIn Post — Documentation-Driven Development

> Copy-paste ready. Adjust the personal intro if needed.

---

🚀 **I've been working with AI coding agents for months. Here's the single most important thing I learned.**

The problem with AI agents isn't intelligence. It's **memory**.

Every new session starts from zero. No context. No history. No conventions. You spend 20 minutes re-explaining the project before getting anything useful done.

So I flipped the model.

Instead of explaining the project to the AI — **I document it for the AI.**

I call this approach **Documentation-Driven Development v2 (DDD2)**.

Not a new term — zsup defined it back in 2014: *"write the docs before the code."* Spec-first. Clarity before implementation. A great idea that never fully took off.

In 2026, with AI agents in the loop, it's no longer optional. It's the missing infrastructure. No longer an **intern task** — it's now your core **architecture**!

There's a term gaining traction in AI engineering circles: **Context Engineering** — the practice of designing and maintaining the information an AI agent needs to perform well. DDD is Context Engineering, made concrete and accessible for entire software teams.

One rule stands at the heart of it: **the 3S Rule**.
Every context document must be **Selected** (only what's relevant), **Synthetic** (distilled, not dumped), and **Structured** (headings, bullets, tables). Noise kills context. Structure is clarity.

But the deepest insight in DDD is about **harnessing**. Memory is the `.md` files. Context is the documentation. And harnessing happens *through* the context itself, not on top of it.

The `.ai_context/` folder doesn't just inform the agent. It *constrains* it. The agent knows its role, the rules, the history, the conventions.

This is **Documental Engineering**: treating the document layer as the primary engineering artifact, not a byproduct.

> *Documentation is the constant. The context is a variable.*

Documental Engineering is the ghost in the machine. Invisible to the end user, indispensable to the team building it.

The key insight: **context is not a prompt. It is architecture.**

A prompt disappears after the session. A versioned <code>.md</code> file is permanent, forkable, and gets smarter over time. That's the difference between a one-shot AI interaction and a **durable, compounding team asset**.

The idea is simple:

📄 Every architectural decision lives in a `.md` file.
📄 Every migration step is written *before* it's executed — as a spec.
📄 After execution, the AI updates a report file with everything it did and why.
📄 Every convention, rule, and constraint is written down — not in a wiki, but in versioned Markdown alongside the code.

The result?

✅ Any AI agent can pick up *exactly* where the last session left off.
✅ Any new developer can understand the project in minutes.
✅ Any PO can validate decisions without reading code.
✅ The entire project is **reconstructible from its `.md` files alone**.

That last point is the real test — the **Reconstruction Guarantee**.
If you lost the codebase tomorrow, your `.md` files must contain enough to:

🔹 Understand the project's purpose and architecture
🔹 Know every rule and convention to follow
🔹 Reproduce every migration or refactoring step
🔹 Make correct decisions in ambiguous situations

In DDD, the answer is always: yes, we can rebuild.

---

The loop looks like this:

```
PO writes specs in .md
→ Dev enriches .md with rules and constraints
→ AI reads .md, executes, updates .md with what was done
→ PO / Dev reviews → corrects → loops
```

The `.md` files are simultaneously the **spec**, the **contract**, the **journal**, and the **reconstruction kit**.

In practice, the structure looks like this:

```
.ai_context/
├── vision.md          ← product vision (permanent)
├── steps/             ← roadmap phases (permanent)
├── skills/            ← agent behaviours (permanent-* kept)
└── tasks/
    ├── specification/ ← PO writes user stories, acceptance criteria
    ├── technical/     ← Dev writes architecture decisions, constraints
    └── done/          ← AI writes the execution report after completion
```

Each context gets its own sprint cycle. Each commit is a versioned snapshot of code AND context.

And the prompt to the AI? It's just a User Story or a ticket — Jira, Linear, GitHub Issues, or even a sticky note:

```
As a [role], I want [feature] so that [outcome].
Technical context: see specs-technical.md
Rules: see best-practices.md
```

The ticket references the docs. The docs drive the execution. The AI reports back.

This isn't about generating docs from code.
This is the **opposite** — documentation drives the code.

And it has four superpowers people don't expect:

**1. Language agnostic** 🌐
The `.md` files describe intent and rules — not syntax. Angular today, something else tomorrow? The documentation survives every migration. Only the code changes.

**2. Agent agnostic** 🤖
All you need is a high-IQ adaptive AI agent with a clear view of the project in an instant, not an inflexible co-worker who attended every meeting. Any agent is expandable.

**3. Fully portable** 📦
Plain Markdown, committed alongside the code. Switch AI agents? The docs follow. Onboard a new dev? Hand them the `.ai_context/` folder. Fork the project? The entire context forks with it. Zero vendor lock-in.

**4. Contextual adaptation** 🔄
Every correction makes the next session smarter. When a convention changes → update the `.md`. When the AI makes a mistake → fix the `.md`, re-run. The error won't happen again. The documentation gets sharper with every iteration.

---

We built two open-source plugins to make DDD zero-friction in your IDE.

🔵 **DocumentFirst** for VSCode.
🔌 **DocumentFirst** for JetBrains.

👉 [github.com/documentfirst](https://www.github.com/documentfirst)

Both plugins auto-detect your `.ai_context/` folder, scaffold the right templates for a new feature or migration, and give you a tree view of your entire knowledge structure without leaving the IDE.

No external server. No special infrastructure. Just Markdown files, versioned in Git, and a plugin that knows where to look.

---

**What about MCP and contextual memory tools?**

**MCP** (Anthropic's Model Context Protocol) is a great complement — it automates the *injection* of your `.ai_context/` context into the agent without manual attachment. Think of it as the transport layer: DDD provides the content, MCP delivers it automatically. Useful for multi-agent setups or team-shared context servers.

**Memory tools** (Mem0, Zep, Mempalace...) are a different story. They store implicit, conversational memory in a vector database. But here's our working hypothesis:

> 🧪 *If you practice DDD correctly, you don't need a memory layer. If something is important enough for the agent to remember — write it in a `.md` file.*

Memory tools are opaque, non-versionable, and incompatible with closed agents like GitHub Copilot. A well-maintained `.ai_context/` folder does the same job — explicitly, transparently, and for free.

**One project makes this crystal clear: [Memoir](https://memoir-ai.dev).**

Memoir is a high-performance semantic memory system for AI agents — built around the observation that *"AI memory is a global variable anti-pattern"*. It replaces opaque vector databases with transparent, versioned, cryptographically secure memory storage. It even uses Git semantics: branch, commit, merge, rollback.

Their diagnosis is word-for-word our thesis:
> *"Your agent's memory is code without version control. One bad session poisons every future retrieval."*

Memoir's answer is infrastructure: semantic paths, O(log n) lookups, memory aggregation, multi-agent sessions.

**DDD's answer is a `.md` file committed to Git.**

Both agree on the problem. The difference is the solution layer.

---

🔬 **The theoretical proof — from Microsoft Research.**

A paper published in 2026 by Philippe Laban, Tobias Schnabel and Jennifer Neville makes the case in hard numbers: *"LLMs Corrupt Your Documents When You Delegate."*

They tested 19 models — including frontier ones — across 52 documents, with 20 editing interactions each. The result?

> **25% of document content was degraded** by the best models. Average across all 19: **50% degradation**. And the decline never plateaued — it was monotonic. The longer you delegate, the worse it gets.

Peter Naur argued in 1985 that a program is not its source code. It's **the theory** — the mental model of how and why the system works — held by the people who built it. When those people leave, the theory dies. You're left with an artifact nobody truly comprehends.
[(Source)](https://cekrem.github.io/posts/llms-corrupt-your-documents/)

This paper shows something worse. When you delegate document maintenance to an LLM, **the theory dies twice**: you didn't build the understanding because you delegated, *and* the LLM silently corrupted the artifact itself. You've lost both the map and the territory.

DDD is the antidote. The `.md` files *are* the theory — written down, versioned, human-owned. The AI executes against them. The human reviews the diff. The theory survives.

---

A proof coming from an unexpected place.

🕹️ **Legends of the Future Past** — a MUD from 1992 — just came back online in 2026.
Not because someone had the original server code. Because the **structured text files describing the world** had survived: zones, characters, rules, quests, lore.

The executable was gone. The documentation was not. The game was rebuilt from its data files alone.
[(Source)](https://www.reddit.com/r/MUD/comments/1sexcyd/legends_of_future_past_1992_is_back_online/)

Your `.md` files are those data files.
**Code is temporary. Documentation is permanent.**

---

One more thing that changes everything about how we think about IP.

In traditional software, the intellectual property lives in the code.
In DDD, that assumption is inverted.

**The real intellectual property is the documentation.**

The code is a snapshot. It gets rewritten. It becomes legacy. It is replaced.
The `.md` files encode *why* decisions were made, *what failed*, *what constraints shaped the architecture*, and *what the team actually learned*. That is **Knowledge Capital** — and it compounds over time.

A team that loses its codebase can rebuild.
A team that loses its Knowledge Capital starts from zero.

This raises a question nobody has answered yet: **what license governs a DDD project?**

MIT, Apache, CC BY — these licenses were designed for artifacts. A DDD repo is not an artifact.
It's a living context, co-authored by developers, POs, and AI agents, evolving continuously.

Who owns it? How do you attribute it? What are the obligations of a fork that inherits years of accumulated context?

We don't have a **Living Knowledge License** yet. But we need one.

---

If DDD resonates with you or your team:

☕ **Support the manifesto** — Patreon, Ko-fi, Buy Me a Coffee, GitHub Sponsors
🏆 **Documentation First Certification** — a structured audit & badge program for organizations that have adopted DDD (founding member spots open)

👉 [documentationfirst.ai](https://documentationfirst.ai)

Would love to hear how your team manages context with AI agents 👇

#AI #SoftwareEngineering #DeveloperExperience #DocumentationDrivenDevelopment #DDD #ContextEngineering #KnowledgeCapital #OpenSource #GitHub #Copilot #Cursor #JetBrains #LLM #IDEFirst
