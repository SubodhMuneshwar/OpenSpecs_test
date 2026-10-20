# Design: 3D Real-Time Dragon Ball Z Battle Arena

## Context

The player needs direct control of Goku in three-dimensional space with real-time movement, flight, dodging, and projectile combat against an autonomous 3D Vegeta.

## Goals / Non-Goals

**Goals:**
- Implement a responsive Three.js 3D battle arena that runs directly in any browser without build tools.
- Deliver full 3D six-axis movement (WASD ground movement, Space to fly up, Shift to descend).
- Provide real-time projectile simulation for Ki Blasts and 3D Kamehameha/Final Flash beams.
- Implement third-person lock-on battle camera smoothly framing Goku and Vegeta.
- Deliver autonomous 3D AI for Vegeta that maneuvers, charges Ki, and fires 3D attacks.
- Retain synthesized Web Audio API sounds, HP/Ki HUD bars, and battle log.

**Non-Goals:**
- Heavy multiplayer networking (local player vs. 3D AI).
- Requiring huge external 3D `.gltf` asset downloads that cause loading delays. Construct stylized 3D anime models with high-res textured accents and volumetric energy auras.

## Decisions

### Decision 1: Three.js via CDN in self-contained `index.html`
- **Choice:** Load Three.js r128 via standard script tag.
- **Rationale:** Ensures zero build steps and 100% offline-friendly execution.

### Decision 2: 3D Stylized Anime Character Construction
- **Choice:** Create 3D anime combat rigs combining 3D martial arts body meshes, textured portraits, and dynamic particle auras.
- **Rationale:** Instant loading, full animation control (fly, punch, beam stance), and guaranteed rendering across all GPUs.

### Decision 3: Raycast / Bounding Sphere Collision System
- **Choice:** Efficient distance-based bounding sphere checks in the 60fps render loop.
- **Rationale:** High-speed detection for rapid Ki blasts and continuous beam collision.
