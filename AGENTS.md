# AGENTS.md

## What this repo is
Python learning workspace. Single active component: `snake_game/` (Python 3, `turtle` module, no dependencies).

## Running the game
```bash
python snake_game/snake.py
```
Requires a display (uses Tkinter under the hood). Works on Windows only (`.bat` launcher provided). `wn.tracer(0)` disables auto-redraw — game loop calls `wn.update()` manually.

## Constraints
- **No external dependencies** — only Python 3 stdlib. Do not add `pip install` steps or third-party packages unless user explicitly asks.
- **Target OS: Windows** — paths use backslashes; `.bat` scripts are part of the UX.
- **Single-file architecture** — all game logic lives in `snake.py` (188 lines). Keep it that way unless the user asks for a refactor.

## Existing docs
`GEMINI.md` in repo root contains detailed architecture notes. Prefer the executable source (`snake.py`) over prose if they conflict.
