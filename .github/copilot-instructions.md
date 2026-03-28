# Project Guidelines

## Mandatory Development Checklist
- [ ] Lint: `uv run ruff check .`
- [ ] Build: `uv sync`
- [ ] Test: `uv run pytest`

## Architecture
- FastAPI + Jinja2 + HTMX app.
- Keep pure game logic in `app/game_logic.py`; keep session and route orchestration in `app/game_service.py` and `app/main.py`.
- Render HTMX-friendly template fragments from `app/templates/components/`.
- Session state is in-memory (`_sessions`), keyed by cookie session ID.

## Conventions
- Use immutable board square updates (`model_copy(update=...)`), not in-place mutation.
- Board is 5x5 with fixed free center (index 12); tests expect 24 toggle buttons.
- Keep endpoint responses template-driven and aligned with existing HTMX flow.
- Prefer test updates in `tests/test_api.py` and `tests/test_game_logic.py` for behavior changes.
- Do not use VS Code Simple Browser; open http://localhost:8000 in an external browser.

## Docs and References
- Start with `README.md` and `workshop/GUIDE.md`.
- Styling guidance: `.github/instructions/css-utilities.instructions.md`.
- Global rules: `.github/instructions/general.instructions.md`.
- Frontend design guidance: `.github/instructions/frontend-design.instructions.md`.
- Reusable prompts and agents: `.github/prompts/` and `.github/agents/`.
