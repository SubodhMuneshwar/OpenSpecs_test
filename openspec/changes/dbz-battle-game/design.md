# Design: Dragon Ball Z Battle Arena Game

## Context

The repository is initializing a new browser-based arcade mini-game demonstrating Spec-Driven Development. We need a zero-dependency, self-contained architecture that can run instantly by opening a single HTML file in any browser.

## Goals / Non-Goals

**Goals:**
- Deliver an arcade-quality Dragon Ball Z turn-based battle experience in a single responsive `index.html`.
- Implement dynamic visual feedback: glowing Super Saiyan Ki aura, screen shake, Kamehameha energy beam, and hit sparks using pure CSS/canvas animations.
- Provide a responsive CPU AI that makes balanced combat decisions.
- Maintain simple, readable, modular JavaScript code adhering strictly to the specs.

**Non-Goals:**
- Multiplayer networking or WebSockets (local player vs. CPU only).
- Heavy asset downloads (spritesheets, external sound files) - use SVG / CSS graphics and Web Audio API synthesized sound effects.

## Decisions

### Decision 1: Single-file Architecture vs Multi-file bundle
- **Choice:** Consolidate HTML, CSS, and JS into a single `index.html` with modular sections.
- **Rationale:** Frictionless experience. Any developer or reviewer can double-click `index.html` without running a local web server or installing node dependencies.
- **Alternative Considered:** Vite / React build pipeline (rejected to avoid build step overhead for a lightweight mini-game).

### Decision 2: Web Audio API for Retro DBZ Sound Effects
- **Choice:** Generate laser blasts, charge hums, and punch sounds dynamically using the native browser `AudioContext`.
- **Rationale:** No broken external sound URLs or 404 assets; audio works 100% offline and reliably across all browsers.
- **Alternative Considered:** Linking external MP3 files from CDNs (prone to broken links and CORS blocks).

### Decision 3: Deterministic Turn-Based Battle State Engine
- **Choice:** Central state object `gameState` controlling player, opponent, and turn locks.
- **Rationale:** Ensures strict adherence to the behavioral scenarios defined in `specs/battle-arena/spec.md`.

## Risks / Trade-offs

- **[Browser Audio Autoplay Policy]** → AudioContext must only initialize or resume on the first user click/action.
- **[Screen Shake Accessibility]** → Keep screen shakes subtle and short (150ms) to ensure comfortable visual accessibility.
