# SpecCraft 🏗️

*An experiment in ontology-driven architecture agents*

🚧 **Work in progress** 🚧

SpecCraft explores a central question:
👉 *Can ontologies serve as the backbone for AI agents that help design software systems?*

Unlike most GenAI tooling, which relies on flat text prompts or transient memory, SpecCraft grounds every interaction in a persistent **ontology of software architecture elements and relationships**. This ontology becomes the agent’s working memory, its reasoning scaffold, and the source of truth for every artifact it generates.

---

## 1 · Why This Experiment

AI coding agents have proven they can write production code. But before code, there’s architecture — and here, teams still spend hours in meetings, diagrams, and compliance reviews. Traditional GenAI patterns struggle in this stage:

* **Conversational LLMs**: generate a spec from a one-off prompt, but lose consistency and structure across iterations
* **Orchestration frameworks**: coordinate multiple agents, but without a persistent model, their outputs remain brittle and hard to trust

SpecCraft is testing whether **ontologies can fix this**:

* They give the agent a backbone — a structured state of “what the system is” that survives across turns
* They enforce coherence and constraint without needing giant prompts
* They enable multiple projections (docs, diagrams, compliance checks) from the same underlying model

---

## 2 · What Ontology-Driven Means Here

SpecCraft uses an **ontology of systems, containers, and components** (inspired by C4 but extensible). Every user utterance is mapped into updates on this ontology:

* Add / refine / remove entities and relationships
* Attach annotations like assumptions, risks, or open questions
* Keep a single evolving model that the agent can always explain

Artifacts — markdown specs, PlantUML diagrams, exports — are not “outputs” in themselves. They’re **views projected from the ontology.**

---

## 3 · Scope of the Experiment (v0)

This experiment is deliberately narrow:

**In scope**

* Test if an ontology can serve as durable agent memory for system design
* Map conversational inputs into ontology updates
* Project ontology into C4-style diagrams + markdown docs
* Build the agent as a stateful frontend app (easy to distribute, scalable, no backend — just OpenAI Agent SDK for model communication)

**Out of scope (for now)**

* Rich compliance rules
* Multi-agent orchestration
* Shared multi-user state
* Alternative ontologies beyond core C4 vocabulary

---

## 4 · What Success Looks Like

If SpecCraft works, it will show:

* **Ontologies as backbone** → agent stays coherent across turns
* **Multi-projection** → docs/diagrams are trivial side effects, not fragile generations
* **Agentic reasoning** → the ontology enables the agent to critique, ask clarifying questions, and track risks without prompt bloat

---

## 5 · Future Directions

This is a stepping stone. If the ontology backbone holds, we could extend into:

* Richer ontologies (compliance, risks, performance, infra)
* Multi-modal inputs (sketches, transcripts, inventories → ontology)
* Multi-agent collaboration, each grounded in the same ontology
* Enterprise integrations (review workflows, CI/CD pipelines, governance)

---

### TL;DR

SpecCraft isn’t “just another spec generator.” It’s an experiment to test whether **ontology-driven memory** is the missing layer that makes AI agents reliable for architecture work.
