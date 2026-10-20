# Proposal: Budokai Tenkaichi 3 Combat & HUD System

## Why

To deliver the legendary feel of *Dragon Ball Z: Budokai Tenkaichi 3* (BT3), the battle arena needs the signature BT3 combat systems: supersonic Dragon Dashing, Z-Counter Vanish teleports, Sparking! Mode, multi-hit Rush combos that knock opponents across the canyon, segmented Ki gauges, Blast Stocks, lock-on range meters, and classic BT3 combo hit counters.

## What Changes

- Implement iconic Budokai Tenkaichi 3 HUD:
  - Multi-layered Health Bars (Green/Yellow/Red layered gauges with life bar multiplier).
  - 5-segment Blue/Yellow Ki energy bars plus numeric Blast Stock counters.
  - 3D lock-on reticle displaying real-time distance in meters (e.g., `24m`).
  - BT3 stylized Comic Combo Counter (e.g., `5 HITS! 1,250 DMG`).
- Implement signature BT3 movement & combat mechanics:
  - **Dragon Dash (`Shift + Direction` or Double-Tap):** High-speed supersonic flight with forward aura shockwave.
  - **Vanish / Z-Counter (`V` or Dodge):** Instant transmission behind the enemy with "bwa-shing!" audio.
  - **Rush Combo (`J` / Left-Click):** 4-hit martial arts rush finishing in a heavy knockback that sends Vegeta flying backwards through 3D space.
  - **Sparking! Mode (`MAX KI`):** Blazing aura mode granting unlimited Ki blasts, faster dashes, and super armor.
  - **Explosive Wave (Blast 1 / `B`):** 360-degree shockwave pushing the opponent back.
- Vegeta AI upgraded with BT3 behavior (Dragon Dash pursuit, Vanish counters, and Galick Gun / Final Flash beams).

## Capabilities

### Modified Capabilities
- `battle-arena`: Integrate Budokai Tenkaichi 3 combat flow, Dragon Dashing, Vanish teleports, Sparking Mode, and BT3 HUD.

## Impact

- Upgrades `index.html` with BT3 combat loop, camera zooms, and retro UI styling.
