# EMBERHEIRS — WORLD GENERATION

## MVP objective
Generate one deterministic medium-sized starting region with enough variety and resources for the early settlement, without creating a huge always-active world.

Conceptual pipeline:
world_seed -> region_seed -> elevation -> water -> environment/biomes -> geology -> resources -> starting-area validation.

Same world seed + generator version must reproduce the same region.

## Starting region
Conceptually `region(0,0)`. Terrain should support city-builder readability and current movement: coherent hills/valleys, mostly buildable slopes around the start, natural forest/meadow transitions, rocky areas and meaningful water.

Initial environment categories should remain small: meadow/plains, forest, dense forest, rocky/hills, water.

## Water
Rivers/streams and lakes/ponds are initially geography and obstacles/presentation. Future fishing, drinking, irrigation, bridges and watermills are documented possibilities, not MVP requirements.

## Geology
Maintain a lightweight future-compatible geology/resource-potential concept. MVP gameplay exposes Stone only. Coal, iron, copper, gold and similar resources are future content, not current systems.

## Resource distribution
Food/berries: lowlands, meadows and forest edges; renewable; relatively fast regrowth.
Wood/trees: forests; renewable; slower regrowth.
Stone: rocky/hill/geological clusters; finite/nonrenewable.

Starting-area validation should ensure usable build space and reasonable access to Food/Wood/Stone/water without stacking every resource beside the camp. Invalid starts retry deterministically.

Approximate design target for starting-region Stone: enough for early progression; prior prototype target was roughly 800–1200 total with major deposits around 200–300, but final values must be tuned against actual building costs.

## Persistence
Save seed, generator version, authoritative resource depletion/regrowth state, and any modifications required to reproduce the world. Regrowth follows simulation time; pause stops it and speed modifies it.

## Future multi-region architecture — design only
World -> Region -> Settlement/Outpost -> Local Storage -> Logistics Network.
Future regions may generate on demand from world seed + region coordinates and specialize in resources. Remote regions may eventually use aggregate simulation. Do not implement multi-region gameplay during MVP unless explicitly scheduled.
