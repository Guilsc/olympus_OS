# Olympus Conceptual Architecture

This document records the current conceptual architecture. Greek mythology is part of the product identity and future experience layer; it does not replace explicit technical names in the underlying system.

```text
OLYMPUS
├── Inbox
├── Realms
│   └── Initiatives
├── Zeus (sovereign / governance)
├── Hermes-agent (Chief Orchestrator; display identity: Hermes)
├── Pantheon
├── Mnemosyne
├── Agent Memory
├── Working Context
└── System
```

`Hermes-core` refers to the Hermes Software/base foundation, not the Olympus Chief Orchestrator.

## Components

- **Inbox** is the entry point for uncategorized incoming material and intent.
- **Realms** are major domains of activity. **Initiatives** are outcomes or projects within Realms.
- **Zeus** is Olympus’ sovereign/governance Agent. **Hermes-agent** receives intent, determines relevant context, identifies required capabilities, routes work, coordinates handoffs, and returns validated results. It does not hold sovereign authority and should not become a do-everything super-agent.
- **Pantheon** is the registry of reusable agents and capabilities. Agents belong to Olympus rather than individual Initiatives; Initiatives assemble the capabilities they need.
- **Mnemosyne** is the curated Second Brain and durable knowledge layer.
- **Agent Memory** records experiential history from agent activity.
- **Working Context** is the temporary context for the current task.
- **System** contains governance, skills, policies, templates, and taxonomy.

## Three memory layers

### Working Context — “What am I working on now?”

Contains the current conversation, current task, scratch information, and active Initiative context. It is short-lived.

### Agent Memory — “What happened before that may help?”

Contains previous runs, observations, failures, lessons, interaction history, and agent-specific experience. It is persistent but experiential.

### Mnemosyne — “What do we actually know?”

Contains curated sources, knowledge, decisions, topics, entities, relationships, and reusable learnings. It is durable and authoritative.

Memory does not automatically become knowledge. Agent output, conversations, and observations may propose knowledge, but they do not automatically become canonical knowledge.

## High-level flow

```text
Capture
→ Hermes-agent
→ Classify
→ Initiative / Work Item
→ Specialist capability
→ Result
→ Artifact / Work Update / Proposed Decision / Proposed Knowledge
→ Review
→ Librarian
→ Mnemosyne when justified
```

## Future Experience Layer

Olympus may eventually provide a game-like spatial interface inspired by a cosmic interpretation of Greek mythology. This is a concept only; it is not implemented here.

Possible visual mappings:

| Olympus concept | Possible visual mapping |
|---|---|
| Olympus | Celestial command world |
| Realm | Planet, moon, or region |
| Initiative | Settlement or outpost |
| Work Item | Mission |
| Agent | Mythological entity |
| Capability | Power |
| Skill | Learned ability |
| Pantheon | Agent citadel |
| Mnemosyne | Memory core or archive |
| Knowledge relationship | Constellation |
| Agent handoff | Travel between locations |
| Integration | Portal |
| Builder environment | Forge |

The game layer must reflect actual Olympus state and must never become an independent source of truth. A future user may interact with the same Olympus system through **Command View**, a professional operational interface, and **Olympus View**, a spatial/game representation of the same data and activity. Do not implement either interface during this bootstrap.
