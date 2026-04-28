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

📁 `.ai_context/features/authentication/`
&nbsp;&nbsp;&nbsp;&nbsp;📄 `specs-functional.md` ← PO writes user stories, acceptance criteria, business rules
&nbsp;&nbsp;&nbsp;&nbsp;📄 `specs-technical.md` ← Dev writes architecture decisions, API contracts, constraints
&nbsp;&nbsp;&nbsp;&nbsp;📄 `DONE.md` ← AI writes the execution report after completion

Each context gets its own versioned subfolder. Each subfolder is a self-contained unit of knowledge.

And the prompt to the AI? It's just a User Story or a ticket — Jira, Linear, GitHub Issues, or even a sticky note:

```
As a [role], I want [feature] so that [outcome].
Technical context: see specs-technical.md
Rules: see best-practices.md
```

The ticket references the docs. The docs drive the execution. The AI reports back.

This isn't about generating docs from code.
This is the **opposite** — documentation drives the code.

And it has three superpowers people don't expect:

**1. Language agnostic** 🌐
The `.md` files describe intent and rules — not syntax. Angular today, something else tomorrow? The documentation survives every migration. Only the code changes.

**2. Fully portable** 📦
Plain Markdown, committed alongside the code. Switch AI agents? The docs follow. Onboard a new dev? Hand them the `.ai_context/` folder. Fork the project? The entire context forks with it. Zero vendor lock-in.

**3. Contextual adaptation** 🔄
Every correction makes the next session smarter. When a convention changes → update the `.md`. When the AI makes a mistake → fix the `.md`, re-run. The error won't happen again. The documentation gets sharper with every iteration.

---

One thing I want to be clear about: **DDD is IDE-first**.

Not a chat window. Not an external platform. Your IDE — JetBrains AI, GitHub Copilot, Cursor, Windsurf — whatever you already use.

The flow is:

```
.ai_context/ in the repo
    → you attach or reference them in the IDE agent
    → AI reads context, executes, updates DONE.md
    → you commit code + docs together
```

No external server. No special infrastructure. Just Markdown files, versioned in Git, read by your IDE agent.

---

**What about MCP and contextual memory tools?**

**MCP** (Anthropic's Model Context Protocol) is a great complement — it automates the *injection* of your `.ai_context/` context into the agent without manual attachment. Think of it as the transport layer: DDD provides the content, MCP delivers it automatically. Useful for multi-agent setups or team-shared context servers.

**Memory tools** (Mem0, Zep, Mempalace...) are a different story. They store implicit, conversational memory in a vector database. But here's our working hypothesis:

> 🧪 *If you practice DDD correctly, you don't need a memory layer. If something is important enough for the agent to remember — write it in a `.md` file.*

Memory tools are opaque, non-versionable, and incompatible with closed agents like GitHub Copilot. A well-maintained `.ai_context/` folder does the same job — explicitly, transparently, and for free.

The next step? **Native IDE plugins** — for JetBrains and VSCode — that auto-detect your `.ai_context/` folder, inject the right context automatically, and scaffold templates for new features or migrations based on your tech stack.

Zero friction. Always-ready context. No copy-paste.

---

🔭 **One more idea on the horizon.**

The DDD loop still has one blind spot: **the conversation itself**.

Every session produces decisions, discoveries, trade-offs. Today, they vanish when the session closes.

The next step for the IDE plugins: **read the current conversation and propose a structured `.md` draft** — decisions, new rules, execution notes — that the developer reviews and commits.

Not a memory tool. Not a transcript. A **proposed document**, human-validated, that enters the Knowledge Capital of the project.

> *The conversation is the raw material. The plugin proposes. The developer decides.*

That's the last missing piece of the DDD loop.

---

 The proof  coming from an unexpected place.

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
