# Spec Delta: 3D Battle Arena

## ADDED Requirements

### Requirement: 3D Six-Axis Spatial Movement and Flight
The system SHALL enable the player to navigate Goku across three dimensions (X, Y, Z axes) using ground strafing, forward/backward movement, and vertical flight ascension/descension.

#### Scenario: Player moves in 3D space
- **WHEN** the player presses W, A, S, or D
- **THEN** Goku moves across the ground plane relative to the camera direction

#### Scenario: Player ascends and descends
- **WHEN** the player presses Space
- **THEN** Goku flies upward into the air; pressing Shift causes Goku to descend

### Requirement: Real-Time 3D Ki Projectiles and Kamehameha Beam
The system SHALL simulate energy blasts as physical 3D meshes traveling with velocity, collision hitboxes, and particle impact sparks.

#### Scenario: Firing rapid Ki blasts in 3D
- **WHEN** the player presses Ki Blast (Right-Click or 'K')
- **THEN** a glowing 3D energy orb spawns from Goku and accelerates along the vector toward Vegeta

#### Scenario: Firing 3D Kamehameha Beam
- **WHEN** the player triggers Kamehameha with at least 50 Ki
- **THEN** a massive 3D energy cylinder with rotating spiral rings extends from Goku toward Vegeta, dealing 40 damage on collision

### Requirement: Dynamic 3D Lock-On Battle Camera
The system SHALL provide a third-person chase camera positioned behind Goku that continuously tracks and rotates toward Vegeta to keep the opponent in view.

#### Scenario: Camera follows 3D movement
- **WHEN** Goku moves or flies in 3D space
- **THEN** the camera smoothly interpolates behind Goku while angling toward Vegeta

### Requirement: 3D Opponent Spatial Navigation and AI
The system SHALL give Vegeta autonomous 3D navigation to strafe, hover at combat range, fire 3D projectiles, and execute 3D Final Flash beams.

#### Scenario: Opponent engages in 3D combat
- **WHEN** the battle is active
- **THEN** Vegeta repositions in 3D space, charges Ki when safe, and fires 3D energy beams when at distance
