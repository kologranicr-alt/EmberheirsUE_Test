# EMBERHEIRS — AGENT RULES (UNREAL ENGINE)

Status: Core agent constitution
Engine target: Unreal Engine 5.8.x, Windows, PC-first

Every coding or editor agent (Codex, Aura, or another AI tool) MUST read this file, `CURRENT_PHASE.md`, and the relevant documents in `docs/` before modifying the project.

## 1. Project vision
Emberheirs is a long-term post-apocalyptic civilization simulation. The player begins with a tiny group of survivors and may eventually manage settlements, towns, regions, infrastructure, institutions, industries, generations, factions, trade and logistics networks, and advanced technology.

The architecture must support gradual expansion without requiring fundamental rewrites, but the implementation must remain MVP-first. Do not implement speculative future systems merely because they are described in design documents.

## 2. Authority boundaries
- C++ owns authoritative simulation and persistent gameplay state.
- Blueprints are primarily presentation, configuration, editor integration, and thin adapters.
- Animation, VFX, audio, UI, meshes, and visual Blueprints must not become authoritative gameplay state.
- Never create a second implementation of an existing system in another layer.
- Presentation may observe simulation state; it must not silently manufacture resources, complete jobs, or alter simulation rules.

## 3. Agent responsibilities
### Codex / code-focused agent
Prefer for C++ core systems, state, deterministic rules, resource accounting, citizens, tasks/actions, buildings, construction, save/load, automated tests, and code refactors.

### Aura / editor-focused agent
Prefer for Levels, Landscape, PCG, materials, visual Blueprints, animation integration, asset import/configuration, collision setup, Niagara, Water, editor automation, and presentation.

These are ownership defaults, not hard tool restrictions. Any cross-layer change must preserve the authority boundary above.

## 4. Permanent engineering rules
- One authoritative simulation clock/tick model. Pause and speed changes must affect simulation consistently.
- Persistent entities use stable IDs. Never rely on display names, transient object pointers, array positions, or actor labels as persistent identity.
- Save data is explicitly versioned and migrations/backward compatibility are considered when schemas change.
- Resource conservation is an invariant: resources cannot appear or disappear accidentally.
- Resources picked up for transport become in-transit and are unavailable at the source immediately.
- Prefer generic reusable capabilities/components/data over bespoke one-off systems.
- Inspect existing implementation before creating new systems.
- Keep simulation separate from presentation.
- Avoid unnecessary per-frame Tick. Prefer events, timers, fixed simulation ticks, batching, instancing, LOD/HLOD, and data-oriented approaches where appropriate.
- Do not add Mass, complex crowd AI, multiplayer infrastructure, World Partition complexity, or other major frameworks until a measured need exists.
- Build the smallest real system that satisfies the current gameplay loop.
- Tests, save/load behavior, and invariants are part of a feature, not optional cleanup.

## 5. Movement and interaction
Early MVP movement may remain deliberately simple. Interaction targets should be external interaction points around buildings/resources; citizens must not disappear into building centers or overlap occupied footprints. Do not introduce a heavyweight navigation/crowd framework without an explicit task requiring it.

## 6. Assets and licensing
Read `docs/ASSET_POLICY.md` before any external asset action.
- Do not buy paid assets without explicit user approval.
- Do not download/import external assets without checking source, license, commercial-use terms, Unreal compatibility, and AI-use metadata.
- For AI-assisted workflows, only use external assets explicitly permitted for that AI use. If Fab says `Allows usage with AI: No`, AI agents must not use that asset as an input or manipulate/analyze it through an AI workflow.
- Record every third-party asset in `docs/ASSET_REGISTER.md`.

## 7. Source control
- NEVER commit or push unless the user explicitly asks.
- Do not modify unrelated files.
- Do not add generated build/cache directories to source control.
- Before finishing a task, report changed files, tests/builds run, known limitations, and manual verification steps.

## 8. Scope discipline
Before implementing anything ask: Is this required for the current playable loop?
- Yes: implement the smallest durable version.
- No, but strategically important: document it.
- No: backlog it.

Do not turn future design notes into current implementation by assumption.
