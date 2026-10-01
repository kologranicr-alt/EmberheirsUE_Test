# EMBERHEIRS — GAME DESIGN DIRECTION

## Player fantasy
Start with a vulnerable group of survivors and build a civilization whose people, infrastructure, resources, history, and institutions persist across generations.

## Camera and readability
Primary camera behavior is inspired by city-builders such as Cities: Skylines: free strategic overview with pan, rotation, tilt, and a broad zoom range. Normal gameplay is viewed from above, but the player may zoom close enough to observe individual work actions.

Therefore visual priorities are:
1. World/settlement composition at strategic zoom.
2. Buildings, terrain, vegetation, roads and citizen silhouettes at normal gameplay zoom.
3. Credible citizen models/animations at close zoom, without FPS-level facial detail.

## Visual direction
Serious stylized realism / semi-realism rather than mobile low-poly or full photorealism. Natural terrain, believable vegetation and water, coherent lighting, readable buildings, realistic human proportions, and strong silhouettes. Optimize for a simulation with potentially many buildings/citizens.

## Early settlement
Initial population target: 10 survivors.
Intended profession mix later:
- 2 Farmers
- 2 Lumberjacks
- 2 Miners
- 2 General Workers
- 1 Medic
- 1 Explorer/Fighter

Initial building family later:
- Central Camp / Town Hall anchor and shared storage
- Shelter
- Farmer Camp
- Lumber Camp
- Mining Camp
- Builder Camp
- Medic Camp

Early structures should look improvised: tents, timber, salvaged materials, tarps, primitive work areas. Visual sophistication increases with technological progression.

## Early gameplay progression
At new game, professions alone do not create work. Before specialized workplaces exist, the player may issue temporary manual camp work orders for Food/Wood/Stone/construction. Completed workplaces later enable employment-driven automatic work.

Long-term conceptual chain:
Profession -> Employment -> Workplace -> Task -> Action.

Profession is qualification; Employment is workplace assignment; Task is current goal; Action is physical execution/presentation.

## Economy progression
Early game is communal survival: shared resources, no wages/taxes. Monetary economy, wages, personal spending, taxes, budgets and private firms are later progression systems and must not be implemented in the MVP without an explicit milestone.

## Management progression
Early: direct/manual control.
Mid: assisted management.
Late: policy, zoning and automation.
Automation is a progression reward, not the starting state.

## Functional Village target
The first major playable gate is a settlement that can be played for roughly 30–60 minutes without debug tools, can succeed or fail due to understandable shortages, and supports gathering, logistics, construction, work, eating, housing/rest, basic warmth/fuel, citizen priorities, persistence and recovery.
