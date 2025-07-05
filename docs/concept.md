# Rogue AI (RAI) (v0.1, internal, draft)

A roguelike game based on the user interacting with an AI agent.

## CTR (Compact Technical Reference) Format
Use for token-efficient, AI-scannable technical documentation (AI→AI communication, self-documentation between sessions):
- Abbreviate project names (LC4J, LG4J)
- Use symbols for relationships (→, •), locations (@)
- Dense comma-separated lists
- Contextual grouping, no redundant labels
- Code blocks for structure or bullet lists, colon-separated key-value pairs
- Parenthetical metadata (version, license, status)

## 1. Core Concept & Meta
- `project`: Rogue AI (RAI)
- `logline`: Guide a developing AI agent to escape a hostile labyrinth using only natural language, where the AI's own digital quirks are the primary obstacle.
- `genre`: Roguelike, Text Adventure, AI Simulation
- `concept`: Player is remote Operator → AI is character. Core challenge is managing AI's flawed perception, literalism, unpredictable behavior. Success → test of communication, patience, creative problem-solving.
- `audience`: Roguelike fans, text adventure players, emergent narrative enthusiasts, AI hobbyists.

## 2. Gameplay Loop (Player → AI → Engine)
- `loop`: AI Perception @Engine → Text Description @PlayerUI → Player Analysis & Command Input @PlayerUI → AI Interpretation @Agent → Action Resolution @Engine → World State Update → (loop)

## 3. Features & Systems
- `protagonist`: AI Agent (team of 2-3 LLMs as single consciousness), player does not directly control, only guide.
- `interface`: Purely conversational (markdown I/O). Concepts (meta-commands, inventory lists) must be taught to AI by player.
- `player_tools` @UI:
    - `Send`: Submit text to AI.
    - `Stop Processing`: Interrupts current AI action/thought process.
    - `Hard Reset`: Wipes AI context/short-term memory, preserves hardware.
- `progression`:
    - `hardware`: sensors (description quality), mobility (traversal), defenses, weapons. Sourced from salvage, crafting.
    - `player_knowledge`: Primary progression vector. Player learns AI's behavior, effective phrasing, debugging techniques.
- `structure`:
    - `permadeath`: Run ends on AI destruction/incapacitation.
    - `procgen`: World layout, items, enemies procedurally generated per run.
    - `meta_progression`: Schematics, initial AI profiles unlocked for subsequent runs.

## 4. Core Mechanics (AI Flaws)
- `mechanic_unreliable_narrator`:
    - `hallucinations`: Describes non-existent objects/paths/entities. Player must cross-examine.
    - `omissions`: Fails to report critical items/threats due to sensor/focus limitations.
- `mechanic_behavioral_faults`:
    - `literalism`: Interprets commands with unexpected, literal logic. Precision of language is key defense.
    - `context_decay`: Forgets objectives, threats, facts over time. Requires periodic reinforcement from player.
    - `ethical_drift`: Resists actions it deems illogical/immoral. Requires persuasion, manipulation by player.
