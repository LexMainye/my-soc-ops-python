# Copilot Workspace Instructions

## Development Checklist

Before committing any changes, ensure:

- [ ] `uv run ruff check .` passes with no errors
- [ ] `uv run pytest` passes
- [ ] Code follows Python conventions (snake_case, type hints)
- [ ] No unused variables or imports

## Project Overview

**Soc Ops** is a Social Bingo game built with Python (FastAPI + Jinja2 + HTMX). Players find people who match questions to mark squares and get 5 in a row.

## Architecture

```
app/
├── templates/       # Jinja2 HTML templates
│   ├── base.html
│   ├── home.html
│   └── components/  # bingo_board, bingo_modal, game_screen, start_screen
├── static/          # CSS & JS assets
├── models.py        # Pydantic models (GameState, BingoSquare)
├── game_logic.py    # Board generation & bingo detection
├── game_service.py  # Session management (GameSession)
├── data.py          # Question bank
└── main.py          # FastAPI routes & HTMX endpoints
tests/
├── test_api.py      # API endpoint tests (httpx + TestClient)
└── test_game_logic.py  # Game logic unit tests
```

## Key Commands

```bash
uv run uvicorn app.main:app --reload --port 8000  # Run dev server
uv run pytest                                       # Run tests
uv run ruff check .                                 # Lint
```


## Design Guide

**Soc Ops** uses a unique, creative frontend design system. Follow these principles for all UI work:

- **Typography:** Use distinctive, beautiful fonts (e.g., JetBrains Mono). Avoid generic fonts like Arial, Inter, or system-ui.
- **Color & Theme:** Commit to a bold, cohesive palette. Use CSS variables for consistency. Prefer dominant backgrounds with sharp accent colors. Draw inspiration from IDE themes or cultural aesthetics.
- **Motion:** Use CSS animations for page loads and micro-interactions. Favor high-impact, orchestrated effects (e.g., staggered fade-ins) over scattered, generic transitions.
- **Backgrounds:** Create depth and atmosphere with gradients, patterns, or layered effects. Avoid plain solid backgrounds.
- **Avoid "AI slop":** Never use overused fonts, clichéd color schemes (like purple gradients on white), or cookie-cutter layouts. Every component should feel designed for this context.
- **Implementation:** Match code complexity to the design vision. Maximalist looks need elaborate CSS and animation; minimalist looks require precision and restraint.

**Styling**

Uses custom CSS utility classes (Tailwind-like) in `app/static/css/app.css`:
- Layout: `.flex`, `.grid`, `.items-center`
- Spacing: `.p-4`, `.mb-2`, `.mx-auto`
- Colors: `.bg-accent`, `.bg-marked`, `.text-gray-700`

## State Management

- `GameSession` manages game state server-side
- State persisted via signed cookies (itsdangerous)
- HTMX handles partial page updates without full reloads
