# My OpenSpec (SPECS) Learning Notes
*Personal notes for Verixa by Subodh*

---

## 📝 Note 1: What is OpenSpec and Why Do I Need It?

### What I Learned:
- **The Problem with "Vibe Coding":** When I prompt an AI coding assistant without a clear specification, the AI makes assumptions, hallucinates code, rewrites files I didn't ask it to touch, loses context after a few messages, and introduces hidden bugs.
- **What SPECS (OpenSpec) Is:** OpenSpec is an AI-native, Spec-Driven Development (SDD) framework created by Fission AI. It bridges the gap between my human intent and the AI's execution.
- **The Golden Rule:** **Always agree on the specification in plain Markdown BEFORE writing a single line of code.**
- **Key Philosophy:**
  - Fluid, not rigid (not a heavy waterfall process)
  - Iterative and lightweight
  - Built for both brand new projects (greenfield) and existing legacy codebases (brownfield) through "Delta Specs".

> **Visual Reference:** Attach `2_vibe_vs_specs.jpg` to this note in Verixa.

---

## 📝 Note 2: The 5-Step OpenSpec Lifecycle

### What I Learned:
Every feature or bug fix I build with an AI assistant follows a clear 5-stage loop:

1. **Step 1 - Explore (`/opsx:explore`):** 
   - I brainstorm ideas with the AI without writing any code.
   - The AI inspects my existing project setup and suggests the cleanest, lowest-risk technical approach.
2. **Step 2 - Propose (`/opsx:propose <feature-name>`):**
   - The AI generates a change proposal package inside `openspec/changes/<feature-name>/`.
   - It drafts 4 key planning files: `proposal.md`, `specs/`, `design.md`, and `tasks.md`.
3. **Step 3 - Human Review (My Quality Gate):**
   - I inspect the markdown files. If anything is wrong, I edit the markdown or ask the AI to `/opsx:update`.
   - Nothing touches my source code until I approve the plan!
4. **Step 4 - Apply (`/opsx:apply`):**
   - The AI reads `tasks.md` and implements each task one by one, checking off boxes (`[x]`).
   - Because it follows the spec strictly, there is zero hallucination or scope creep.
5. **Step 5 - Archive & Sync (`/opsx:archive`):**
   - Once tested, the feature changes are merged into the main living system specs (`openspec/specs/`) and moved to `openspec/changes/archive/`.
   - Keeps the repository clean and provides an audit log of why architectural decisions were made.

> **Visual Reference:** Attach `1_openspec_workflow.jpg` to this note in Verixa.

---

## 📝 Note 3: The 4 Core Artifacts Inside Every Change

### What I Learned:
When I run `/opsx:propose`, OpenSpec creates a folder: `openspec/changes/<feature-name>/` containing:

1. **`proposal.md` (The "Why" and "What"):**
   - Defines why we are building this feature and a summary of what is changing.
2. **`specs/` (The Behavioral Contract / Delta Specs):**
   - Instead of documenting the entire app, it only documents what changed using:
     - `## ADDED Requirements`
     - `## MODIFIED Requirements`
     - `## REMOVED Requirements`
   - Uses plain English scenarios:
     - `Requirement: <Name> SHALL <behavior>`
     - `Scenario: <Title> - WHEN <action> - THEN <outcome>`
3. **`design.md` (The Technical Architecture):**
   - Outlines technical decisions: state management, data models, API endpoints, file structures, and libraries.
4. **`tasks.md` (The Implementation Checklist):**
   - The exact sequential checklist the AI agent will execute (e.g. `[ ] 1.1 Create theme context`).

> **Visual Reference:** Attach `3_openspec_architecture.jpg` to this note in Verixa.

---

## 📝 Note 4: Commands Cheat Sheet (CLI vs Chat)

### CLI Commands (Terminal):
- `npx @fission-ai/openspec init` → Setup OpenSpec in my project and register AI agent slash commands.
- `openspec list` → View all active change proposals.
- `openspec view` → Launch an interactive browser dashboard of my specs and changes.
- `openspec archive <change>` → Archive a completed change and merge deltas.

### AI Chat Slash Commands (Inside Cursor, Claude, Antigravity, etc.):
- `/opsx:explore` → Discuss architecture & approach before starting.
- `/opsx:propose <name>` → Generate the 4 planning markdown artifacts.
- `/opsx:update` → Adjust the specs if my requirements change.
- `/opsx:apply` → Tell the AI to implement tasks.md check by check.
- `/opsx:archive` → Finalize and move to archive.

---

## 📝 Note 5: Team Scaling & OpenSpec Stores

### What I Learned:
- In larger teams or microservice architectures, features span across multiple repositories (e.g., frontend, backend, shared types).
- OpenSpec has a feature called **Stores**: a dedicated Git repo containing specs and changes.
- Multiple code repositories connect to this single store, so product managers, designers, and engineers share a single source of truth!

---

## 📝 Note 6: Hands-On Case Study — Building the DBZ Game

### What I Did and Learned:
1. **GitHub Setup & Sync:**
   - Linked my local folder to my GitHub repo: `https://github.com/SubodhMuneshwar/OpenSpecs_test.git`.
2. **Command 1 - Explore:**
   - Decided to build a Dragon Ball Z browser battle mini-game (Goku vs. Vegeta).
   - Agreed on mechanics (Punch, Ki Charge, Kamehameha, Guard, and CPU AI) without writing code upfront.
3. **Command 2 - Propose (`/opsx:propose dbz-battle-game`):**
   - Generated `proposal.md`, `specs/battle-arena/spec.md`, `design.md`, and `tasks.md`.
   - Verified that the change was 100% valid before generating any code.
   - Committed the proposal to GitHub as the "Source of Truth".
4. **Command 3 - Apply (`/opsx:apply`):**
   - Translated the spec into `index.html` with full Web Audio sound effects, Super Saiyan golden aura, and battle logic.
   - Checked off all tasks in `tasks.md` and pushed code to GitHub.
5. **Command 4 - Archive (`/opsx:archive`):**
   - Merged the delta spec into permanent living specs (`openspec/specs/`) and moved completed change to archive.

---

## 📝 Note 7: The 3D Spatial Evolution — Full Real-Time Movement

### What I Learned & Implemented:
- **From 2D to 3D Space:** Evolved the game from turn-based cards to a full 3D real-time spatial battle arena using **Three.js**.
- **Six-Axis 3D Controls:**
  - `W`, `A`, `S`, `D`: 3D ground strafe and forward/backward movement.
  - `Space`: Fly upwards into the sky.
  - `Shift`: Descend toward the ground.
  - `J` / Left-Click: Dragon Rush melee strike.
  - `K` / Right-Click: 3D Ki blast projectiles.
  - `E` (Hold): Charge Ki aura in mid-air.
  - `Q`: Fire full 3D Kamehameha energy beam.
  - `F`: Instant Guard forcefield.
- **Dynamic Lock-On Camera:** Third-person chase camera that dynamically follows Goku and keeps Vegeta locked in frame.
- **OpenSpec Brownfield Scaling:** Added this 3D feature through change `3d-battle-arena`. The living spec (`battle-arena`) expanded from 11 to **15 testable requirements**!


