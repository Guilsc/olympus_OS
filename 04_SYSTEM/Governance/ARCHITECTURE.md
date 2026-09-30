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
- **Zeus** is Olympus’ sovereign/governance Agent and the first institutional review point for every new Initiative. Zeus performs a lightweight governance/strategic scan, frames material goals and boundaries, and passes an intake briefing to Hermes-agent unless sovereign work is required.
- **Hermes-agent** is the Chief Orchestrator. It receives the Zeus briefing, deepens capability analysis, identifies the accountable Realm Owner, proposes the execution team, routes work, coordinates cross-Realm execution, and returns validated results. It does not hold sovereign authority and should not become a do-everything super-agent.
- **Pantheon** is the registry of reusable agents and capabilities. Agents belong to Olympus rather than individual Initiatives; Initiatives assemble the capabilities they need. Realm Owners are peers and may communicate directly for capability discovery, consultation, and bounded collaboration. Hermes-agent retains orchestration, team composition, routing, and accountability coordination.
- **Mnemosyne** is the curated Second Brain and durable knowledge layer.
- **Agent Memory** records experiential history from agent activity.
- **Working Context** is the temporary context for the current task.
- **System** contains governance, skills, policies, templates, and taxonomy.

## Initiative intake and routing

Every new Initiative passes through Zeus once for first-pass institutional review. This is not routine execution. Zeus checks strategic fit, governance implications, authority boundaries, Realm implications, major risk, and whether a persistent Agent/Realm/system change may be involved. Zeus then passes a concise briefing to Hermes-agent for operational analysis and routing.

```text
Human Owner
→ Zeus: first review / strategic + governance framing
→ Hermes-agent: capability analysis / Realm routing / team composition
→ Accountable Realm Owner + supporting Realm Owners / Temporary Workers
→ Hermes-agent: coordination / validation
→ Zeus only when sovereign escalation or approval is required
```

## Realm Owner collaboration

Realm Owners are peers. They may communicate directly to discover capabilities, request bounded contributions, negotiate artifact interfaces, and coordinate domain expertise. Direct peer conversation does not transfer Initiative accountability and does not create sovereign authority.

Hermes-agent must remain aware of team composition, ownership, and material handoffs. Routine peer collaboration does not require Hermes-agent to relay every message. Sovereign matters normally escalate `Realm Owner → Hermes-agent → Zeus`; direct Realm Owner → Zeus contact is exceptional.

## Skill Pool and capability growth

Olympus maintains a trusted Skill Pool broader than any individual Realm Owner profile. A new Realm Owner receives an intentionally curated initial Skill set during commissioning. That set is not a permanent ceiling.

When a new need appears:

- if the capability belongs to the Agent's own Realm, the Agent may re-consult the trusted Skill Pool and propose or request an appropriate Skill according to provenance, security, permission, and installation policy;
- if the need belongs primarily to another Realm, prefer collaboration with that Realm Owner instead of duplicating the other Realm's specialist Skill set;
- if a procedure is reusable across multiple Realms, keep it shared rather than treating it as one Agent's private capability;
- availability, assignment, default loading, Tool access, and action authority remain separate concepts.

This prevents capability stagnation without allowing every Agent to accumulate every Skill.

## Olympus Communication Layer V1

Inter-Agent communication is an Olympus concern separate from knowledge and memory. V1 contains:

1. Agent Message
2. Conversation / Thread
3. Console Mirror
4. Structured Event Log
5. Initiative Correlation
6. Audit / Replay

Conversation/event records should preserve provenance such as timestamp, sender, recipient, Initiative/Realm context, message type, correlation identifiers, status, and relevant artifact references. Conversation logs are operational/audit records and do not automatically become Agent Memory or Mnemosyne knowledge.

The V1 architecture does not include external transport adapters or a dedicated chat surface.

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
