# Olympus Initial Object Model

This vocabulary names the initial conceptual objects. Internal data models should keep clear, explicit, machine-readable technical terms even when a future experience layer uses mythology-inspired language.

## Objects

### Realm
A major domain of activity. Initial examples: Work, Studies, Personal, Automations, and Lab.

### Initiative
A meaningful outcome, project, or ongoing effort within a Realm.

### Source
External or internal evidence from which information originates.

### Knowledge
A curated, reusable statement, concept, model, or learning.

### Decision
An authoritative choice made within Olympus or an Initiative.

### Work Item
A unit of work required to progress an Initiative. A future experience layer may visually call this a “Mission”; the canonical object remains `work_item`.

### Artifact
A durable output produced through work. Examples include a document, code, diagram, dataset, presentation, analysis, or design.

### Agent
A reusable AI worker with a defined identity, mission, capabilities, permissions, and operating boundaries.

### Capability
Something an Agent is able to perform.

### Skill
A reusable procedure or method an Agent may invoke.

### Tool
An interface that allows an Agent to retrieve information or perform an action.

### Agent Run
A recorded execution of an Agent against a task.

### Approval
A recorded human or governed authorization for a controlled transition or action.

## Independent classification dimensions

| Dimension | Question answered |
|---|---|
| Realm | Where does this belong? |
| Initiative | What outcome does it support? |
| Type | What kind of object is it? |
| Topic | What is it about? |
| Status | Where is it in its lifecycle? |
| Relationship | How is it connected to other objects? |

These dimensions are independent and must not be collapsed into one tag hierarchy.
