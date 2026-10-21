# battle-arena Specification Delta

## ADDED Requirements

### Requirement: Authentic Scouter Radar Mini-Map
The system SHALL render an authentic circular Scouter Radar in the HUD showing the 2D planar positions, relative elevations, and headings of both fighters in real time.

#### Scenario: Radar reflects spatial movement
- **WHEN** Goku or Vegeta navigates across 3D coordinates
- **THEN** their respective blips update position on the radar canvas with elevation arrows indicating vertical disparity

### Requirement: Interactive Keypress HUD Feedback
The system SHALL dynamically highlight control legend badges upon physical keyboard press and release events to provide real-time tactile arcade feedback.

#### Scenario: Player presses movement or attack key
- **WHEN** the player presses a bound key (e.g., W, Shift, J, V, K, Q, E)
- **THEN** the corresponding HUD key badge lights up with a luminous gold glow and resets upon key release

### Requirement: Multi-Perspective Dynamic 3D Camera Modes
The system SHALL support multiple camera perspectives allowing the player to cycle between over-the-shoulder chase, close action, and panoramic arena viewpoints.

#### Scenario: Player cycles camera view
- **WHEN** the player presses the 'C' key or clicks the Camera button
- **THEN** the camera smoothly shifts its follow distance and elevation between Chase, Close Action, and Panoramic modes

### Requirement: Cinematic HUD Visibility Toggle
The system SHALL allow players to toggle the HUD overlay visibility for cinematic battle viewing.

#### Scenario: Player toggles HUD
- **WHEN** the player presses the 'H' key or clicks the HUD toggle
- **THEN** all HUD overlays fade out smoothly, and pressing again restores the full HUD interface
