# LinkedIn Post — Documentation-Driven Development

> Copy-paste ready. Adjust the personal intro if needed.

---

🚀 **In one year, our job as software developers has completely changed.**

We started from manual craft, hunting for documentation, copy-pasting Stack Overflow, writing every line by hand. Autocomplete arrived in our IDEs, then the first AI chats. And in 2026, agentic AI settled into our daily practice for real.

So I started asking: how do we work *well* with it?

I kept coming back to the most neglected part of our craft: **documentation and specs**. Not as an afterthought. As the foundation.

I wanted to frame this as a proper methodology, and build the tooling to go with it. Here it is, along with two plugins to make it zero-friction in your IDE:

🔵 **Extension VSCode** → [documentationfirst](https://marketplace.visualstudio.com/items?itemName=DocumentationFirst.ddd-documentation-first)
🔌 **PlugIn Intellij** → [documentationfirst](https://plugins.jetbrains.com/plugin/31829-documentation-first--ddd2)

I call this approach **Documentation-Driven Development v2 (DDD2)**.

Not a new term, zsup defined it back in 2014: *"write the docs before the code."* Spec-first. Clarity before implementation. A great idea that never fully took off.

In 2026, with AI agents in the loop, it's no longer optional. It's the missing infrastructure. No longer an **intern task**, it's now your core **architecture**!

There's a term gaining traction in AI engineering circles: **Context Engineering**, the practice of designing and maintaining the information an AI agent needs to perform well. DDD is Context Engineering, made concrete and accessible for entire software teams.

One rule stands at the heart of it: **the 3S Rule**.
Every context document must be **Selected** (only what's relevant), **Synthetic** (distilled, not dumped), and **Structured** (headings, bullets, tables). Noise kills context. Structure is clarity.

The `.ai_context/` folder, we created as the convention at the heart of our DDD, doesn't just inform the agent. The agent knows its role, the rules, the history, the conventions.

This is **Documental Engineering**: treating the document layer as the primary engineering artifact, not a byproduct.

Documental Engineering is the ghost in the machine. Invisible to the end user, indispensable to the team building it.

The key insight: **context is not a prompt. It is architecture.**

**Specs are fundamental.**

The result: The entire project is **reconstructible from its `.md` files alone**, the **Reconstruction Guarantee**.

---

Two real-world proofs of this.

🕹️ **Legends of the Future Past**, a MUD from 1992, just came back online in 2026.
Not because someone had the original server code. Because the **structured text files describing the world** had survived: zones, characters, rules, quests, lore. The executable was gone. The documentation was not. The game was rebuilt from its data files alone.
[(Source)](https://www.reddit.com/r/MUD/comments/1sexcyd/legends_of_future_past_1992_is_back_online/)

⚠️ **[malus.sh](https://malus.sh/)**, real or satirical, proposes to use AI robots to *independently recreate* any open source library from scratch, delivering "legally distinct code" with zero attribution, zero copyleft. Whether it ships or not, it names something unavoidable: **if an AI can reconstruct a codebase from its documentation alone, what does IP mean when the docs are the only survivor?**

Your `.md` files are those data files. **Code is temporary. Documentation is permanent.**

---

This raises a question nobody has answered yet.

In DDD, the real intellectual property is **the documentation**, not the code. The code is a snapshot. It gets rewritten. It becomes legacy. The `.md` files encode *why* decisions were made, *what failed*, *what constraints shaped the architecture*. That is **Knowledge Capital**, and it compounds over time.

MIT, Apache, CC BY, these licenses were designed for artifacts. A DDD repo is not an artifact.
It's a living context, co-authored by developers, POs, and AI agents, evolving continuously.

We don't have a **Living Knowledge License** yet. But we need one.

---

👉 Full manifesto: [documentationfirst.github.io](https://documentationfirst.github.io)
📬 Questions or feedback: contact@documentationfirst.ai

#AI #SoftwareEngineering #DeveloperExperience #DocumentationDrivenDevelopment #DDD #ContextEngineering #KnowledgeCapital #OpenSource #GitHub #Copilot #Cursor #JetBrains #LLM

