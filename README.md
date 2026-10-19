# ⚡ Dragon Ball Z: Ki Clash Arena · OpenSpec (SDD) Reference

> An AI-native **Spec-Driven Development (SDD)** demonstration project featuring an arcade Dragon Ball Z browser battle game built with [OpenSpec by Fission-AI](https://github.com/Fission-AI/OpenSpec).

---

## 📌 Project Overview

This repository demonstrates the modern **Spec-Driven Development (SDD)** workflow paired with AI coding assistants (such as **GitHub Copilot**, Claude Code, Cursor, and Antigravity).

Instead of **"Vibe Coding"** (letting an AI guess requirements and hallucinate code), this project enforces the **"Source of TRUTH MD Files"** strategy:
1. **Agree on the specification in plain Markdown first.**
2. **Review the architecture, requirements, and task checklist.**
3. **Execute code generation strictly against the agreed tasks.**
4. **Archive the change into permanent living system specifications.**

---

## 🎮 The Game: Dragon Ball Z Ki Clash Arena

A single-page, zero-dependency arcade battle game built strictly according to the specifications in [`openspec/specs/battle-arena/spec.md`](openspec/specs/battle-arena/spec.md).

### Features
- **Fighters:** Son Goku (Player) vs. Prince Vegeta (Automated CPU AI).
- **Vitality & Ki Meters:** Real-time animated gauges for Health (HP) and Ki energy (0-100).
- **Combat Moves:**
  - 👊 **Dragon Punch:** Quick strike dealing 10 damage to Vegeta while generating +15 Ki.
  - 🔥 **Charge Ki:** Powers up +30 Ki with a glowing Super Saiyan aura and screen shake.
  - 🌊 **Kamehameha Wave:** Consumes 50 Ki to fire a massive blue energy beam dealing 40 damage.
  - 🛡️ **Instant Guard:** Raises defensive stance to reduce incoming enemy damage by 75%.
- **Vegeta CPU AI:** Evaluates situation and retaliates with Melee, Ki Charging, or his signature yellow **Final Flash** beam.
- **Synthesized Audio:** Custom retro sound effects dynamically synthesized via the native browser **Web Audio API** (no external audio assets or CDNs required).
- **Rematch Loop:** Dynamic victory/defeat popups with one-click rematch reset.

### How to Run & Play
```powershell
# From PowerShell / Terminal
Start-Process index.html

# Or simply double-click index.html in Windows File Explorer
```

---

## 🔄 The 4-Step OpenSpec Lifecycle

Every feature in this project follows the team development cycle:

```
[1. Explore]       ──> [2. Propose]       ──> [3. Human Review] ──> [4. Apply]       ──> [5. Archive]
(/opsx:explore)        (/opsx:propose)        (Inspect Markdown)    (/opsx:apply)        (/opsx:archive)
Clarify doubts         Generate 4 MD files    Approve architecture  Implement code       Merge into living specs
```

| Phase | Command | What Happens |
| :--- | :--- | :--- |
| **Command 1** | `/opsx:explore` | Brainstorm mechanics, explore codebase, and resolve doubts before writing any code. |
| **Command 2** | `/opsx:propose <name>` | Scaffolds `openspec/changes/<name>/` and generates `proposal.md`, `specs/`, `design.md`, and `tasks.md`. |
| **Step 3** | *(Human Review)* | Quality gate: Inspect the markdown files. Tweak requirements or run `/opsx:update` if needed. |
| **Command 3** | `/opsx:apply` | The AI reads `tasks.md` and implements each task sequentially, checking off boxes (`[x]`). |
| **Command 4** | `/opsx:archive` | Merges the delta specifications into living specs (`openspec/specs/`) and archives the completed change. |

---

## 📂 Repository Architecture

```text
SPECS/
├── index.html                                        # The complete playable DBZ game
├── README.md                                         # This documentation guide
├── my_verixa_notes.md                                # Copy-ready personal learning notes for Verixa
├── notes_assets/                                     # High-resolution architectural diagrams
│   ├── 1_openspec_workflow.jpg                       # 5-Phase lifecycle diagram
│   ├── 2_vibe_vs_specs.jpg                           # Vibe Coding vs. SDD comparison
│   └── 3_openspec_architecture.jpg                   # Directory and artifact hierarchy
└── openspec/
    ├── config.yaml                                   # OpenSpec configuration profile
    ├── specs/                                        # Permanent Living Specifications (Source of Truth)
    │   └── battle-arena/
    │       └── spec.md                               # Living battle-arena spec (7 testable requirements)
    └── changes/                                      # Change proposals
        └── archive/                                  # Audit trail of completed changes
            └── 2026-10-19-dbz-battle-game/           # Archived proposal, design, specs, & tasks
```

---

## 🛠️ OpenSpec CLI Command Reference

Manage OpenSpec directly from your terminal:

```powershell
# Initialize OpenSpec and auto-configure AI tool prompts
npx @fission-ai/openspec init

# List active in-flight change proposals
npx @fission-ai/openspec list

# List permanent living system specifications
npx @fission-ai/openspec list --specs

# Launch the interactive web UI dashboard in your browser
npx @fission-ai/openspec view

# Validate a change proposal or spec
npx @fission-ai/openspec validate

# Archive a completed change and merge deltas
npx @fission-ai/openspec archive <change-name> -y
```

---

## 📚 Verixa Learning Notes

All conceptual learnings and hands-on milestones are formatted for easy copy-pasting into the **Verixa** app inside [`my_verixa_notes.md`](my_verixa_notes.md).

- **Note 1:** Understanding OpenSpec & The Death of "Vibe Coding"
- **Note 2:** The 5-Stage OpenSpec Feature Lifecycle
- **Note 3:** The 4 Core Artifacts Inside Every Change
- **Note 4:** Command Cheat Sheet (CLI vs. Chat Slash Commands)
- **Note 5:** Scaling Across Teams with OpenSpec Stores
- **Note 6:** Real-World Hands-On Case Study: Building the DBZ Game

---

## 🔗 References & Links
- **GitHub Repository:** [https://github.com/SubodhMuneshwar/OpenSpecs_test.git](https://github.com/SubodhMuneshwar/OpenSpecs_test.git)
- **Official OpenSpec Repo:** [https://github.com/Fission-AI/OpenSpec](https://github.com/Fission-AI/OpenSpec)
- **OpenSpec Docs:** [https://openspec.dev](https://openspec.dev)
