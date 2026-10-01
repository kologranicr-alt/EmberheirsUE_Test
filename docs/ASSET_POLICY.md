# EMBERHEIRS — ASSET & AI POLICY

## Goal
Use third-party assets legally, traceably and consistently while allowing AI-assisted Unreal workflows where the asset's terms permit them.

## Mandatory pre-import check
Before any external asset is downloaded, imported, analyzed, modified, retargeted, processed, or placed by an AI agent, verify:
1. Asset name and creator/publisher.
2. Original source URL.
3. Exact license / Fab license tier or other terms.
4. Commercial game use permitted.
5. Unreal Engine/version compatibility.
6. AI-use metadata/terms.
7. Attribution requirement.
8. Redistribution or other restrictions.

## Fab AI rule
`FREE` does NOT imply AI permission.

If Fab displays `Allows usage with AI: No`, AI agents must not use that asset as an input to a generative-AI workflow or analyze/manipulate it as AI input. Do not ask Aura, Codex, or another generative agent to process such an asset.

For the AI-driven workflow, prefer assets explicitly marked `Allows usage with AI: Yes` and record that status at acquisition time.

If terms are ambiguous, stop and ask the user; do not infer permission.

## Purchasing
Do not purchase any asset without explicit user approval. Prefer free, commercially usable, AI-compatible assets during the proof of concept.

## Visual direction
Serious stylized realism / semi-realism suitable for a city-builder camera. Favor coherent packs over mixing many unrelated art styles. Environment can be detailed, but citizens/buildings must remain scalable to large populations/settlements.

## Technical selection criteria
Prefer assets with sensible LOD/Nanite/instancing support where applicable, efficient materials, usable collision, standard Unreal skeletons for characters, retargetable animations, and documented UE compatibility.

Do not select an asset only because it looks good in an FPS close-up. Evaluate it at strategic and normal city-builder zoom.

## Register requirement
Every third-party asset actually used must be entered in `ASSET_REGISTER.md` before the task is considered complete.
