# CURRENT PHASE — UNREAL ENGINE PROOF OF CONCEPT

Status: Engine/workflow evaluation. This is NOT yet an approved migration of the production Godot project.

## Current objective
Prove that Unreal Engine 5.8 + C++ + Aura/editor automation can deliver Emberheirs' core workflow efficiently and with a materially stronger visual result.

## Proof-of-concept target
Build one small playable test containing:
1. Cities: Skylines-style city-builder camera (pan, zoom, rotate, tilt).
2. One medium test Landscape with readable hills/valleys.
3. Forest/vegetation using PCG or efficient instancing.
4. One river or water feature.
5. A small Central Camp presentation.
6. One citizen.
7. Several tree resources.
8. One complete physical Wood loop: player order/task -> citizen moves to tree -> work/chop presentation -> cargo acquired -> citizen returns to camp -> Wood enters storage only on delivery.

## Evaluation criteria
- C++ iteration/build workflow is acceptable.
- Aura can reliably perform editor-focused tasks without corrupting project state.
- Asset workflow is legally clear and practical.
- Camera and environment look appropriate for a serious PC settlement/city-builder.
- Performance headroom is plausible for much larger settlements.
- Simulation remains authoritative and testable independently of presentation.
- Workflow does not consume unreasonable Codex/Aura usage for routine work.

## Do not implement yet
Professions, automatic employment, hunger, sleep, housing simulation, seasons, weather, temperature, disease, combat, factions, economy/money/taxes, zoning, private firms, multi-region gameplay, outposts, vehicles, rail, advanced citizen AI, multiplayer, or final art polish.

## Decision gate
Do not migrate the production Emberheirs project until this proof of concept has been manually evaluated against the existing Godot workflow.
