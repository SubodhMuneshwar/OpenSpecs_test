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
