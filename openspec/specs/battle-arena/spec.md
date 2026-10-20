# battle-arena Specification

## Purpose
Provides an arcade-style Dragon Ball Z combat arena where the player controls Goku against Vegeta using melee strikes, Ki charging, defensive blocking, and high-impact energy blasts.

## Requirements

### Requirement: Fighter Vitality and Energy Meters
The system SHALL display real-time numeric and visual gauges for Health Points (HP max 100) and Ki Energy (Ki max 100) for both Goku and Vegeta.

#### Scenario: Initial battle state
- **WHEN** the battle initializes
- **THEN** both Goku and Vegeta have 100 HP and 0 Ki

### Requirement: Melee Strike Action
The player SHALL be able to execute a punch attack against the opponent that inflicts moderate damage and builds a small amount of Ki.

#### Scenario: Successful punch executed
- **WHEN** the player clicks the Punch action
- **THEN** Vegeta loses 10 HP, Goku gains 15 Ki, and an entry is appended to the battle log

### Requirement: Ki Energy Charging
The player SHALL be able to charge their Ki energy to prepare for special attacks, playing a power-up aura effect.

#### Scenario: Player powers up
- **WHEN** the player clicks the Charge Ki action
- **THEN** Goku gains 30 Ki (capped at 100), a golden energy aura flashes, and the battle log reports a power charge

### Requirement: Kamehameha Energy Blast
The player SHALL be able to release a Kamehameha beam if they have at least 50 Ki, dealing heavy damage to the opponent.

#### Scenario: Firing Kamehameha with sufficient Ki
- **WHEN** Goku has 50 or more Ki and the player triggers Kamehameha
- **THEN** Goku consumes 50 Ki, Vegeta takes 40 HP damage, and a blast animation crosses the screen

#### Scenario: Firing Kamehameha without sufficient Ki
- **WHEN** Goku has less than 50 Ki and the player triggers Kamehameha
- **THEN** the attack fails, no Ki is deducted, and the battle log notifies the player that more Ki is required

### Requirement: Defensive Guard
The player SHALL be able to take a defensive stance to mitigate incoming opponent damage.

#### Scenario: Guarding against opponent turn
- **WHEN** the player activates Guard
- **THEN** incoming damage on the opponent's immediate next attack is reduced by 75%

### Requirement: Opponent AI Turn
The system SHALL trigger an automated opponent turn following every player action, where Vegeta evaluates his HP and Ki to choose between attacking, charging, or executing a Final Flash beam.

#### Scenario: Opponent takes action
- **WHEN** the player completes an action turn
- **THEN** Vegeta selects an action within 600ms, updates fighter stats, and logs the outcome

### Requirement: Battle Resolution and Rematch
The system SHALL detect when either fighter reaches 0 HP, conclude the battle with a win/loss screen, and offer an immediate rematch button.

#### Scenario: Opponent defeated
- **WHEN** Vegeta's HP drops to 0 or below
- **THEN** the game announces "Goku Wins!", disables attack buttons, and presents a "Fight Again" button that resets both fighters to 100 HP

### Requirement: Authentic Anime Visuals and Background Scenery
The system SHALL display high-resolution anime character portraits for Goku and Vegeta, set against a cinematic Dragon Ball Z battlefield environment with real-time animated background elements.

#### Scenario: Visual presentation on load
- **WHEN** the game launches
- **THEN** Goku is presented with an energetic Super Saiyan portrait, Vegeta is presented with a royal Saiyan armor portrait, and the battlefield background fills the screen

### Requirement: Interactive Ki Particle System
The system SHALL render an HTML5 canvas overlay generating animated floating Ki energy particles and electric spark discharges that intensify during charging and beam attacks.

#### Scenario: Ki charge particle surge
- **WHEN** either fighter charges Ki or unleashes a beam
- **THEN** the particle system increases particle density and velocity by at least 300%

### Requirement: Floating Damage Numbers and Impact Feedback
The system SHALL display animated floating combat text indicating damage dealt (e.g. `-10 HP`, `-40 HP CRITICAL`) and Ki gains directly over the target character on every attack.

#### Scenario: Attack registers damage floater
- **WHEN** an attack connects with an opponent
- **THEN** a vibrant damage floater appears, animates upward, and fades out within 800ms

### Requirement: Super Saiyan Overdrive Transformation
The system SHALL unlock a "Super Saiyan Overdrive" state when Goku reaches 100 Ki, altering his aura to blazing gold and boosting damage by 25%.

#### Scenario: Goku hits max Ki
- **WHEN** Goku's Ki reaches 100
- **THEN** an Overdrive aura is unlocked, notifying the player that attacks deal enhanced damage

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
