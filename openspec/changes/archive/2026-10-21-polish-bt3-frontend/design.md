# Design: BT3 Frontend Polish & Scouter Radar

## Architecture & Visual System

### 1. Scouter Mini-Map Radar Canvas
- An HTML5 Canvas element `#scouterRadar` sized 130x130px situated in the bottom-left corner with glassmorphism styling (`border-radius: 50%`, glowing emerald/cyan neon border).
- Rendered each animation frame:
  - Concentric grid range rings and 4-quadrant crosshairs.
  - Animated rotating radar sweep line radiating from center.
  - Goku position represented as cyan glowing dot with heading direction tip.
  - Vegeta position represented as ruby red glowing dot with relative altitude indicator (up-arrow for above, down-arrow for below, filled circle for level elevation).
  - Real-time numeric distance label below radar (`RADAR: 24.5m`).

### 2. Interactive Keypress Glow System
- Data attributes on `.badge-key` elements corresponding to keyboard input codes (`data-key="w"`, `data-key="shift"`, `data-key="j"`, etc.).
- Global `keydown` / `keyup` listeners apply/remove `.key-active` class containing intense golden-orange box shadow, border pulse, and scale transform.

### 3. Multi-Mode 3D Camera System
- State tracking variable `cameraMode` with 3 presets:
  - Mode 0 (`CHASE`): Behind-the-shoulder chase camera (distance 11 units, elevation 4.4 units).
  - Mode 1 (`CLOSE`): Intense close-up action camera (distance 6.5 units, elevation 2.5 units).
  - Mode 2 (`PANORAMIC`): Wide orbital viewpoint (distance 22 units, elevation 8.5 units).
- Toggled via `C` key or header button.

### 4. Cinematic HUD Visibility Mode
- `hudVisible` boolean state.
- When toggled (`H` key or header icon), applies `.hud-hidden` class transitioning HUD opacity to 0 with pointer-events disabled, leaving an unobtrusive semi-transparent toggle button.

### 5. Sparking! Mode Screen-Edge Vignette
- Full-screen fixed overlay `.sparking-vignette` with radial gradient glowing gold/crimson around screen edges that animates with a 60fps pulsating blur when `gameState.player.isSparking` is true.
