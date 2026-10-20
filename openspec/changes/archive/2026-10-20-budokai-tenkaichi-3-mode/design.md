# Design: Budokai Tenkaichi 3 Combat & HUD System

## Context

The 3D arena supports basic movement and projectiles. This design injects the signature combat dynamics of Budokai Tenkaichi 3 (BT3) to make the game feel fast, cinematic, and responsive.

## Goals / Non-Goals

**Goals:**
- Implement the authentic BT3 HUD layout:
  - Top-left & top-right character hexagon frames.
  - Multi-tier HP bars with numeric health bar multiplier (e.g., `x3 LIFE`).
  - 5-cell segmented Ki gauge that turns into flashing rainbow/gold during Sparking! Mode.
  - Blast stock numeric indicators (`0` to `3`).
  - Central dynamic lock-on ring with real-time distance readouts in meters (`21m`).
  - Dynamic right-side Comic Combo Counter (`3 HITS! 840 DMG`).
- Implement BT3 signature gameplay:
  - **Dragon Dash (`Shift + WASD`):** 3x flight velocity with conical aura shockwaves and Ki drain.
  - **Z-Counter / Instant Vanish (`V`):** Teleport directly behind the opponent.
  - **Rush Melee Chain (`J` / Left-Click):** 4-hit combo chain ending in a heavy physics knockback.
  - **Sparking! Mode:** Triggered at 100 Ki, unlocks unlimited Ki blasts for 12 seconds with max power aura.
  - **Explosive Wave (`B`):** 360-degree defensive blast pushing enemy away.

## Decisions

### Decision 1: Multi-layer HP gauge logic
- **Choice:** Maintain total HP (300 total = 3 bars of 100). The top bar displays current 100 with color coding (Green bar -> Yellow bar -> Red bar), and a badge `x3 LIFE`, `x2 LIFE`, `x1 LIFE`.
- **Rationale:** Faithfully matches the PS2 / Wii Budokai Tenkaichi 3 life bar visual.

### Decision 2: Teleport Vanish via vector offset
- **Choice:** Calculate position `vegeta.position + vegeta.forward * -4` and instantly lerp Goku with a flash effect and "bwa-shing" audio.
- **Rationale:** Produces the quintessential Dragon Ball teleport-behind-the-back maneuver.
