# EMBERHEIRS — VISUAL DIRECTION

## Target
A serious-looking PC settlement/city-builder using stylized realism / semi-realism. The world should look credible from a Cities: Skylines-style camera while retaining enough detail for close observation of citizens and work.

## Camera distances
### Strategic zoom
Terrain silhouette, river network, forests, settlement footprint, roads and smoke must read clearly.

### Normal gameplay zoom
Highest priority. Buildings, vegetation, resource deposits and citizens must be attractive and immediately readable.

### Close zoom
Work actions should remain credible: walking, carrying, chopping, mining, building, gathering, eating, treatment, etc. Avoid unnecessary cinematic/FPS character detail.

## Environment
Natural elevation, gentle buildable terrain near starts, forest density gradients, meadows/clearings, rocky geology, convincing shorelines, ground variation and atmospheric lighting.

Use Unreal Landscape, PCG, Water, Niagara, instancing/Nanite/LOD as appropriate, but visual systems must not own simulation logic.

## Buildings
Early structures are improvised survival architecture: tents, timber frames, salvaged sheet material, tarps, crates, work piles, fires and simple workshops. Buildings evolve visually with eras and technology.

## Citizens
Realistic human proportions, scalable materials/LODs, clear profession silhouettes and high-quality reusable animation. Avoid MetaHuman-level cost for ordinary population unless a future hero/portrait use case justifies it.

## Performance
Visual ambition must coexist with city-builder scale. Avoid treating every tree, prop, citizen or decorative object as an expensive unique Actor with independent Tick/physics.
