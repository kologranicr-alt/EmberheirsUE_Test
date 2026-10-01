# EMBERHEIRS — WORKFORCE DESIGN

Status: Design direction; implement only according to roadmap/current phase.

## Core chain
Profession -> Employment -> Workplace -> Task -> Action.

- Profession: persistent qualification/identity.
- Employment: citizen's assigned workplace.
- Workplace: building capability that accepts professions and provides capacity/tasks.
- Task: current gameplay goal.
- Action: physical execution state and presentation.

## Initial profession IDs
- profession.farmer
- profession.lumberjack
- profession.miner
- profession.worker
- profession.medic
- profession.explorer_fighter

## Initial population intent
2 Farmers, 2 Lumberjacks, 2 Miners, 2 General Workers, 1 Medic, 1 Explorer/Fighter.

## Workplace rules
Only completed building instances provide workplace capacity. Construction sites and mere building definitions do not employ citizens. Central Camp must not silently act as a universal invisible workplace.

Before a matching workplace exists, citizens remain unemployed/idle unless the player gives a temporary manual camp work order. Once a completed compatible workplace exists, employment-driven work may take priority over stale manual orders.

Early capacity examples: 2 farmers, 2 lumberjacks, 2 miners, 2 builders/general workers, 1 medic. Capacity growth through upgrades/eras is future content.

## Staffing effectiveness
Understaffed workplaces should later have reduced output/effectiveness. Exact formulas are data-driven/tunable and should not be invented prematurely.

## Progression — future
Professions may later gain XP/levels/proficiency. Repeated work outside a primary profession may create secondary proficiency. Higher skill should improve speed/yield/success modestly rather than producing absurd multipliers. Do not implement until meaningful work loops exist and the milestone calls for it.
