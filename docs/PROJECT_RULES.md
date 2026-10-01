# EMBERHEIRS — PROJECT RULES

## Product principles
Emberheirs is a PC-first civilization/settlement simulation with a long progression arc: survivors -> camp -> settlement -> town/city -> regions -> institutions/industry/logistics -> advanced civilization.

The game should feel physical and legible: citizens travel, resources exist somewhere, construction consumes delivered materials and labor, and shortages have understandable causes.

## Core architectural principles
1. Modular and data-driven where it creates real reuse.
2. Simulation/presentation separation.
3. Deterministic behavior where practical, especially persistence-sensitive systems.
4. Stable persistent identity.
5. Versioned saves.
6. Physical/local resource logic rather than magical global transfer.
7. Performance-conscious design suitable for city-builder scale.
8. MVP-first scope control.
9. Avoid premature frameworks and abstractions.
10. Systems should compose through capabilities rather than hard-coded building classes whenever practical.

## Feature completion rule
A gameplay feature is not complete until:
- authoritative state and ownership are clear;
- invariants are defined;
- save/load impact is handled;
- automated tests cover critical logic where practical;
- manual verification steps are documented;
- presentation does not become gameplay authority.

## Development cadence
One feature -> architecture check -> implementation -> invariants -> persistence -> tests -> manual verification -> user approval -> commit only when requested.
