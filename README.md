# SpecCraft 🏗️

*Your Architecture Design Companion*
---

🚧 **Under Development** 🚧

SpecCraft is an experimental AI-powered tool for iteratively building and refining software architecture specifications through conversation.  
It’s designed to bridge the gap between free-form discussion and structured, compliant architecture docs.

This public repository currently serves as a placeholder while active development happens in a private repo.

---

## Status
- **Code:** Not yet public
- **Planned release:** 8/11
- **Scope:** Conversational architecture modeling with persistent structured state

---

## Follow for Updates
📌 Star or watch this repo to be notified when the first public release is available.

---

## 1 · Why SpecCraft?

Recent agentic tools have transformed coding — you can ask Claude for a feature and get a pull request in minutes. But earlier in the SDLC, when teams are shaping a system, the workflow still runs on whiteboards, slide decks, and long meetings. This is especially true in large enterprises, where architecture work must pass manual reviews and meet detailed compliance standards.

**SpecCraft** explores a hybrid approach: conversational like working with a general LLM, but grounded in a persistent structured model that updates over multiple turns. The agent listens as you describe and refine the system, captures its structure, flags open questions, and keeps a living C4-style view in sync. It’s not a finished tool — it’s a proof of concept to explore what it feels like when an AI sidekick handles the bookkeeping (and eventually some ideation) so architects can focus on trade-offs, not templates.

---

## 2 · Problem & Approach

**The problem**
Developers lose too much time on orchestration during the planning stage of the SDLC — sitting through meetings, drawing diagrams, and manually reworking architecture documents to meet enterprise requirements.

**Two common GenAI patterns for architecture specs**
When teams try to apply GenAI here, they often go to one of two extremes:

1. **Entirely conversational** — describe the system to a general LLM (Claude, ChatGPT) and ask for a full spec in one shot
2. **Entirely agentic** — orchestrate multiple specialist agents (managers, critics, writers, etc.) to take in lots of inputs and generate the final spec in a single coordinated pass

Both approaches run into predictable problems:

| Approach                            | Why it struggles                                                                                                                                                                                                                                                                                                                                                                                                             |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **General-purpose assistant**       | - Users often miss critical details in the first prompt, forcing multiple back-and-forths — but each follow-up re-generates the entire spec, so you must reconcile changes manually<br>- The model forgets or contradicts earlier decisions since there’s no single source of truth it’s grounded in<br>- Output can vary widely between prompts and between runs, making results feel inconsistent, especially across users |
| **Heavy multi-agent orchestration** | - Orchestration logic is complex to design, test, and maintain, creating ongoing engineering overhead<br>- Performance slows as control passes between multiple agents, increasing user wait time<br>- Excessive clarifying questions interrupt the user’s flow and can feel repetitive<br>- Output quality remains inconsistent despite the added complexity                                                                |

**SpecCraft’s approach**
SpecCraft explores a hybrid — conversational and iterative like the first approach, but with a persistent structured model and targeted agentic functions to avoid the pitfalls of both extremes:

* Treat architecture specs as iterative living documents, not single-pass outputs
* Maintain a structured representation that the agent refines over multiple turns
* Use that representation as the single source of truth to generate any needed outputs — from diagrams to full documents — without losing context

---

## 3 · What It Is & How To Try It

SpecCraft is a self-contained web app — a minimal but functional proof of concept you can run straight from GitHub Pages. It’s conversational and iterative like a general-purpose LLM, but under the hood it maintains a structured model of your system that updates turn by turn. You don’t describe everything once — you refine the spec over multiple turns as new details emerge.

**Try it**

1. Open `https://astonhamilton.github.io/speccraft`
2. Go to **Settings → API Key** and paste your OpenAI key
   • Stored only in your browser’s local storage
3. Describe your system in plain language, then refine it over multiple turns
   • “Mobile app → API gateway → services → Postgres” → add missing pieces as you go
4. Watch a draft spec appear and evolve
   • The C4-style graph grows as you converse; drag to tweak
5. Export when ready
   • Copy **PlantUML** for docs or reviews

**Capabilities in v0**

* Conversation-driven extraction of elements and relationships
* C4 vocabulary at System, Container, and Component levels
* Live force-directed canvas with drag and zoom
* Local-first persistence in the browser
* One-click PlantUML export

> This repository hosts the compiled build only to make the app accessible on GitHub Pages.

---

## 4 · Scope of This Experiment (v0)

This proof of concept is designed to show how an agent can iteratively build and maintain an architecture model over multiple turns — not to serve as a fully autonomous “partner architect.” It focuses on keeping the structured model coherent as you refine it, and on producing useful artifacts from that model.

| Theme                       | In Scope                                                                                                       | Out of Scope                                                                                                 |
| --------------------------- | -------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------ |
| **Model & Reasoning**       | Iterative multi-turn projection of a C4-style model (System → Container → Component) from conversational input | Deep “partner architect” reasoning such as trade-off analysis, compliance checks, or pattern recommendations |
| **Storage & Collaboration** | Local-first persistence in browser storage to preserve the evolving model                                      | Multi-user sessions, shared cloud backends, or database sync                                                 |
| **Visualization & Export**  | Live C4 graph with drag/zoom and one-click PlantUML export                                                     | Alternative diagram types (sequence, deployment, data flow) or IDE/CI integrations                           |

---

## 5 · What v0 Demonstrates

* **Multi-turn beats one-shot**
  The agent keeps a persistent, structured model of the design, so each turn builds on the last without losing agreed-upon details.
* **State is the source of truth**
  The evolving C4 model lives outside the prompt, enabling coherent updates, accurate diagrams, and reliable exports over long conversations.
* **Artifacts come for free**
  Because the model is maintained as you go, generating diagrams and starter documents is a by-product of the workflow — not a separate, manual step.

---

## 6 · Where It Could Go Next

V0 shows that an agent can keep an evolving architecture model coherent across turns and produce useful artifacts from it. The next steps build on that same loop — expanding inputs, adding reasoning, and integrating into the broader toolchain.

**Richer inputs**

* Accept multimodal sources like whiteboard photos, hand-drawn sketches, or architecture diagrams from other tools
* Pull in meeting transcripts, RFCs, or system inventories to pre-load known components and context
* Connect to architecture repositories for reference patterns and shared component libraries

**Smarter reasoning**

* Apply enterprise architecture guardrails in real time to flag violations as the design evolves
* Surface cost, performance, and security considerations contextually during design discussions
* Suggest relevant architectural patterns based on system requirements and constraints

**Deeper integration**

* Generate additional views (sequence, deployment, data flow) from the same maintained model
* Plug into IDEs, CI/CD pipelines, or documentation platforms for seamless updates
* Enable multi-user collaborative sessions with shared state and version control

---

## 7 · License

Licensed under the **Apache License, Version 2.0** — see [`LICENSE`](./LICENSE)
