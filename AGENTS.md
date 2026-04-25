# AGENTS.md

## 🛠️ Mandatory Development Checklist
- [ ] Lint: `uv run ruff check .` passes
- [ ] Test: `uv run pytest` passes
- [ ] Build: `uv run uvicorn app.main:app --reload --host 0.0.0.0 --port 8000` runs without errors

## Project Quick Facts
- **App:** Python (FastAPI, Jinja2, HTMX)
- **Frontend:** Custom CSS utilities ([see instructions](.github/instructions/css-utilities.instructions.md)), creative design ([see frontend guide](.github/instructions/frontend-design.instructions.md))
- **Key Folders:**
  - `app/` — main code, templates, static assets
  - `tests/` — API & logic tests
  - `workshop/` — step-by-step guides (multi-language)

## Custom Agents
- **Pixel Jam:** UI design, iterative, spec in `docs/design-spec.md`
- **Quiz Master:** Generates icebreaker bingo questions
- **TDD Red/Green/Refactor:** Full TDD cycle (write failing tests, minimal code, refactor)
- **UI Review:** Automated UI/UX review using Playwright

## Conventions & Rules
- Never use VS Code Simple Browser (see [.github/instructions/general.instructions.md](.github/instructions/general.instructions.md))
- Follow Python style: snake_case, type hints, no unused code
- Use only project CSS utilities for styling

## Docs & Help
- [README.md](README.md): Overview, lab guide, links
- [CONTRIBUTING.md](CONTRIBUTING.md): Contribution rules
- [workshop/](workshop/): Full offline guides

For more, see `.github/instructions/` and agent `.agent.md` files.
