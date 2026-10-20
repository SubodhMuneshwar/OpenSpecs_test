# Design: Frontend Visual Enhancement

## Context

The initial game implementation is fully functional but visually minimal. This design incorporates authentic high-res anime art, ambient particle physics, combat motion graphics, and audio enhancements.

## Goals / Non-Goals

**Goals:**
- Implement high-res anime character portraits in `assets/goku.jpg` and `assets/vegeta.jpg`.
- Implement cinematic battlefield environment in `assets/battlefield.jpg`.
- Implement background HTML5 canvas particle engine rendering dynamic energy orbs, rising Ki embers, and lightning bolts.
- Add CSS animations for fighter attack lunges, damage shakes, and floating combat text (`-40 HP CRITICAL!`).
- Add an interactive Scouter HUD displaying dynamic fluctuating battle power.
- Support audio mute/unmute control with state persistence.

**Non-Goals:**
- Changing core game balance or backend infrastructure.
- Adding third-party UI libraries (keep vanilla HTML5/CSS/JS).

## Decisions

### Decision 1: Canvas particle system vs DOM elements
- **Choice:** Use a single `<canvas>` element layered in the background.
- **Rationale:** 60fps performance without DOM bloat, supporting 80+ simultaneous glowing Ki embers and lightning discharge arcs.

### Decision 2: Floating Combat Text via dynamic DOM elements
- **Choice:** Spawn ephemeral `.combat-text` elements positioned over the target fighter with CSS `@keyframes floatUpFade`.
- **Rationale:** Allows rich typographic styling, drop-shadows, and critical hit scaling that automatically garbage-collects upon animation end.
