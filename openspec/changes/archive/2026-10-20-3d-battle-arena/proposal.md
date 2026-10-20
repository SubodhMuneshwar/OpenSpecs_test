# Proposal: 3D Real-Time Dragon Ball Z Battle Arena

## Why

The current battle game provides turn-based combat with 2D card animations. To deliver an authentic, high-speed Dragon Ball Z combat experience (akin to *Budokai Tenkaichi* or *Xenoverse*), the game must evolve into full 3D space where players have complete freedom of movement (walking, flying, strafing, high-speed dashing), real-time 3D projectile combat, and dynamic lock-on camera controls.

## What Changes

- Introduce Three.js WebGL rendering engine for full 3D hardware-accelerated graphics.
- Implement 3D player movement:
  - WASD: Forward, backward, and lateral strafing across the 3D battlefield.
  - Space / Shift: 3D vertical flight (ascend into the sky and descend to the ground).
  - High-speed vanish dash toward or away from the opponent.
- Implement dynamic 3D third-person battle camera with target lock-on on Vegeta.
- Implement real-time 3D combat mechanics:
  - 3D Melee Combo: High-speed dash strike into physical collision.
  - 3D Ki Blast Barrage: Rapid-fire 3D energy projectiles traveling with velocity and hit detection.
  - 3D Kamehameha Beam: Massive cylindrical energy beam with particle spirals blasting across 3D coordinates.
  - 3D Instant Guard: Spherical energy forcefield deflecting incoming projectiles.
- Implement 3D Opponent AI for Vegeta:
  - 3D spatial navigation, flight maneuvering, and tactical distance management.
  - Firing 3D Ki blasts and charging up full 3D **Final Flash** beams.
- Build a full 3D Wasteland Arena with rocky terrain, crater canyons, floating debris boulders, and dynamic point lights.

## Capabilities

### Modified Capabilities
- `battle-arena`: Evolve combat from 2D turn-based to real-time 3D spatial movement and physics-based projectile collision.

## Impact

- Rewrites `index.html` game engine to use Three.js WebGL canvas.
- Retains existing Web Audio API sound synthesizer and HUD meters.
