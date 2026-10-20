# Spec Delta: Budokai Tenkaichi 3 Combat & HUD System

## ADDED Requirements

### Requirement: Budokai Tenkaichi 3 HUD and Lock-on Metric
The system SHALL display an authentic BT3 HUD featuring layered health bars (Green over Yellow over Red), segmented 5-bar Ki gauges, Blast Stock counters, and a 3D lock-on reticle displaying real-time distance in meters.

#### Scenario: Lock-on distance updates
- **WHEN** Goku moves closer or further from Vegeta
- **THEN** the reticle displays the exact distance in meters (e.g. `18m`, `42m`)

### Requirement: Supersonic Dragon Dash Flight
The system SHALL provide a high-speed "Dragon Dash" propulsion mode that consumes Ki continuously while propelling the fighter at 300% standard flight speed with a conical energy aura.

#### Scenario: Dragon Dash engaged
- **WHEN** the player holds Shift while moving in 3D
- **THEN** Goku bursts into supersonic flight with forward shockwave particles, consuming Ki per second

### Requirement: Z-Counter Vanish Teleportation
The system SHALL allow fighters to perform an Instant Vanish that teleports them immediately behind their target upon pressing the Vanish command.

#### Scenario: Vanish behind opponent
- **WHEN** the player triggers Vanish ('V' key)
- **THEN** Goku teleports with a "bwa-shing" sound effect and appears 4 units directly behind Vegeta facing his back

### Requirement: Sparking! Mode and Multi-Hit Rush Combos
The system SHALL enable a 4-hit Rush Combo ending in an opponent knockback, and activate "Sparking! Mode" when Ki reaches maximum.

#### Scenario: Rush combo executed
- **WHEN** the player performs consecutive melee strikes
- **THEN** a 4-hit combo registers on the BT3 hit counter (e.g. "4 HITS! 1,200 DMG"), culminating in a knockback kick sending the opponent flying backward
