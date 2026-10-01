# EMBERHEIRS — UNREAL ARCHITECTURE

## Layer model
### Authoritative simulation (C++)
Owns persistent state and rules: simulation time, stable IDs, citizens, resources/inventories, buildings, construction, professions/employment, tasks/actions, needs, skills, local storage/logistics, save/load and deterministic rule evaluation.

### Unreal presentation/integration
Actors, ActorComponents, Data Assets/Data Tables where appropriate, Blueprints, meshes, materials, Animation Blueprints, Niagara, Landscape, Water, PCG, UI and editor tooling represent or configure simulation state without replacing it.

## Recommended boundaries
Use UObject/UStruct/plain C++ data for state that does not require an Actor. Do not create an Actor for every abstract simulation concept. Use Actors where spatial/world representation is actually required.

Avoid unconditional per-citizen/per-resource Tick. Simulation updates should be fixed-step/event-driven/batched where practical. Visual interpolation can run independently.

## Stable identity
Persistent objects require stable IDs. World Actor references are runtime conveniences, not save identity. Save records should reconnect presentation actors to simulation entities by stable ID.

## Data-driven definitions
Content definitions should use stable IDs and data assets/tables/structured data as appropriate. Examples:
- resource.food / resource.wood / resource.stone
- profession.farmer / profession.lumberjack / profession.miner / profession.worker / profession.medic / profession.explorer_fighter
- building.central_camp / building.shelter / building.farmer_camp etc.

Definitions describe content. Runtime state records instances.

## Building capabilities
Prefer reusable capabilities such as Workplace, Housing, Storage, Production/Task Provider, rather than bespoke logic per building. A Shelter can have Housing capability without Workplace; a Lumber Camp can expose Workplace/task capabilities.

## Citizen conceptual layers
Add only when milestones require them:
Identity -> Profession -> Employment -> Needs -> Skills -> Home -> Current Task -> Current Action.

## Resource/logistics invariants
Resource quantities are authoritative and conserved. A pickup removes availability at the source and creates cargo/in-transit state. Delivery transfers cargo to destination inventory. Save/load must preserve cargo and prevent duplication.

Long-term resources are local, not magically global. UI may later aggregate totals, but consumption requires accessible/local/transported stock.

## Construction pipeline
All normal buildable structures should eventually share one authoritative pipeline:
placement -> construction project -> material requirements -> physical delivery -> labor -> completed BuildingState/presentation.
Do not create separate instant-spawn logic for each workplace.

## Task/action architecture
Workplace/task systems should produce goals/tasks; citizens execute actions. Avoid direct permanent coupling such as `profession == lumberjack => add wood every N seconds`. Physical action chains should remain observable and interruptible.

## Save/load
Save schema has an explicit version. Persist authoritative simulation, not transient visual state. On load, presentation is reconstructed/rebound from simulation state. Any schema change must consider old saves.

## Performance trajectory
Target large settlements over time. Design for instanced vegetation, LOD/HLOD, animation LOD, reduced distant simulation detail, batched updates and eventually region-level LOD simulation. Do not implement those advanced systems until profiling or milestones justify them.
