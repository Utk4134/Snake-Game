# GEMINI.md - Workspace Project Analysis & Guide

## Project Overview
This repository serves as a workspace for the **Gemini Course**, focused on practical Python development and AI-assisted programming exercises. The primary active component in this workspace is a standalone, lightweight desktop **Snake Game** implemented with pure Python standard libraries.

---

## Directory Structure

```text
D:\Gemini Course\
│
├── GEMINI.md                 # Project analysis, architecture, and agent instructions
│
└── snake_game/               # Interactive Snake game implementation
    ├── README.md             # Player documentation and quick-start instructions
    ├── play_snake.bat        # Windows one-click batch launcher
    └── snake.py              # Main game logic using the Python standard `turtle` module
```

---

## Component Details

### 1. `snake_game/`
A 2D arcade Snake game designed to run on any standard Python 3 installation without requiring third-party package managers or dependencies (e.g., `pygame`).

* **Technology Stack**:
  * **Language**: Python 3.x
  * **Graphics / UI**: `turtle` (Tkinter-backed standard graphics engine)
  * **Timing & State**: `time`, `random`

* **Key Mechanics & Architecture (`snake.py`)**:
  * **Game Loop**: Configured via `wn.tracer(0)` for manual screen redraws with custom tick throttling (`time.sleep(delay)`), minimizing flicker.
  * **Input Handling**: Asynchronous key listeners bound to `wn.listen()` supporting both **WASD** and **Arrow Keys**.
  * **Collision Detection**:
    * **Boundary**: Bounding box coordinate checks against window dimensions (800x800 px).
    * **Food**: Distance calculation (`head.distance(food) < 20`) triggering snake growth, score increment (+10), and game acceleration (reducing delay).
    * **Self-Collision**: Segment distance calculations resetting the snake on tail strikes.
  * **Score Tracking**: Dynamic on-screen HUD displaying real-time `Score` and session `High Score`.

* **Execution Methods**:
  * **Via Batch Script (Windows)**: Double-click `snake_game\play_snake.bat`.
  * **Via CLI**:
    ```bash
    cd "snake_game"
    python snake.py
    ```

---

## Development Guidelines for AI Agents

When modifying or expanding code in this workspace, adhere to the following conventions:

1. **Dependency Discipline**:
   * Prioritize the standard library (e.g., `turtle`, `tkinter`, `dataclasses`, `pathlib`) for simple interactive tools and games unless the user explicitly requests an external framework (e.g., `pygame`, `PyQt`).
2. **Platform Considerations**:
   * Target OS is Windows. Ensure file paths handle Windows separators cleanly and CLI instructions remain compatible with PowerShell / CMD.
3. **Modularity & Documentation**:
   * Keep modules self-contained with clear functions and readable state variables.
   * Provide or update accompanying `README.md` and helper scripts (`.bat`) for non-technical users to launch games or utilities easily.
