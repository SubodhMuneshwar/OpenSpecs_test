# Proposal: BT3 Frontend Polish & Scouter Radar

## Problem Statement
While the core 3D Dragon Ball Z Budokai Tenkaichi 3 gameplay and HUD are functional, several high-impact frontend polish opportunities exist to heighten player immersion and visual feedback:
1. **Situational Awareness:** Players in 3D combat cannot see enemy relative elevation or spatial heading when maneuvering at extreme speed without a mini-map. Authentic BT3 features an iconic circular Scouter Radar in the bottom-left corner.
2. **Keyboard Tactile Feedback:** Players cannot see if their keypresses (`W`, `A`, `S`, `D`, `Shift`, `J`, `K`, `E`, `Q`, `V`) are registering on the on-screen legend.
3. **Camera Perspectives:** The camera is fixed to a single chase distance; players cannot switch between cinematic action, panoramic views, or over-the-shoulder perspectives.
4. **Cinematic Immersion:** No option exists to hide the HUD for screenshots or uninterrupted cinematic combat viewing.
5. **Sparking! Mode Visual Energy:** Sparking Mode lacks screen-edge fiery vignette effects to make the power surge palpably intense.

## Proposed Solution
Enhance the frontend in `index.html` with:
- **Scouter Radar Mini-Map Canvas:** A circular radar displaying real-time 3D spatial coordinates, sweep line animation, and elevation indicators for Goku and Vegeta.
- **Interactive Keyboard Input Highlighting:** Real-time visual pulses on control legend badges upon physical keypresses.
- **Dynamic Camera Mode Selector:** Toggle between 3 camera perspectives (`CHASE`, `CLOSE ACTION`, and `ORBIT PANORAMIC`) via `C` key or button.
- **Cinematic HUD Toggle:** Toggle UI overlays on and off via `H` key or header button.
- **Sparking! Screen Vignette:** Golden pulsating edge energy vignette when Sparking! Mode is engaged.
