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

## Design Guide: Nature & Organic Theme

### Color System (CSS Variables in `app/static/css/app.css`)
All colors are defined as CSS variables for consistency. Always use variables, never hardcode hex values.

**Primary Palette (Nature-Inspired Greens):**
- `--color-nature-dark: #1a4d3e` — Deep forest green, use for text on light/hover states
- `--color-nature-base: #2d6a5c` — Primary brand green, buttons and key UI elements
- `--color-nature-mid: #4a8f7f` — Mid-tone green, secondary buttons, accents
- `--color-nature-light: #a8d5ca` — Light green, hover states, borders
- `--color-nature-pale: #e8f5f0` — Pale green, backgrounds, negative space

**Accent Palette (Neon Purple):**
- `--color-accent-neon: #d946ef` — Primary neon purple, marked squares, celebration elements
- `--color-accent-neon-dark: #c026d3` — Darker purple, hover states
- `--color-accent-neon-light: #e879f9` — Lighter purple, button hover text

**Supporting Colors:**
- `--color-white: #ffffff` — Card backgrounds, text on dark
- Grays: `--color-gray-50` through `--color-gray-900` — UI layers, text variants

### Typography
- **Headings:** `font-heading` (Poppins family) — bold, distinctive, playful
- **Body text:** `font-body` (Outfit family) — modern, warm, readable
- **Font weights:** 400 (regular), 500 (medium), 600 (semibold), 700 (bold)
- Use `.font-heading` class on title/hero elements for visual hierarchy

**Size Scale:**
- `.text-xs` through `.text-6xl` — use semantic sizing, never assume pixel values
- Headings typically `.text-4xl` or `.text-5xl`, body `.text-sm` or `.text-base`

### Spacing & Sizing
- Use CSS variable spacing scale: `--space-1` (0.25rem) through `--space-12` (3rem)
- Apply via utility classes: `.p-4`, `.mb-6`, `.gap-3`, etc.
- Grid gaps: use `.gap-2` or `.gap-3` (not `.gap-1` — too cramped)
- Padding: minimum `.p-3` inside cards for breathing room

### Border Radius (Organic Styling)
- `.rounded-sm` — minimal rounding (alerts, small elements)
- `.rounded-base` — standard cards and buttons
- `.rounded-lg` — larger cards
- **`.rounded-organic`** — 1rem radius, use for main UI components, buttons, modals (distinctive, nature-inspired)
- `.rounded-full` — circular elements (avatars, badges)

### Shadows (Depth & Layering)
- `.shadow-sm` — subtle depth, unused or secondary elements
- `.shadow-base` — standard cards, buttons
- `.shadow-md` — elevated cards, hover states
- `.shadow-lg` — modals, overlays
- `.shadow-neon` — glow effect for neon accent elements (e.g., marked squares: `--shadow-neon: 0 0 20px rgba(217, 70, 239, 0.3)`)
- `.shadow-neon-heavy` — strong neon glow for winning/celebration elements

### Animation & Motion
All animations are CSS-driven and respect `prefers-reduced-motion`.

**Key Animations:**
- `.animate-fade-in` — smooth fade on page load
- `.animate-slide-up` — element enters from below (0.6s spring easing)
- `.animate-bounce-smooth` — celebration/win modal bounce (0.8s)
- `.animate-scale-bounce` — emoji celebration effect (0.6s)
- `.animate-glow-pulse` — neon glow pulse for "BINGO!" status indicator (2s infinite)

**Staggered Animations (for sequential reveals):**
- `.animate-stagger-1` through `.animate-stagger-5` — each applies 100ms delay increments
- Use on rules, rules cards, or button groups for progressive reveal effect
- Example: `<h1 class="animate-stagger-1">Title</h1>` staggered with siblings

**Transitions:**
- `.transition-all` — smooth color/scale/shadow changes (300ms default)
- `.transition-colors` — color-only transitions
- `.transition-transform` — scale/position only
- `.transition-smooth` — explicit smooth easing
- Durations: `.duration-150`, `.duration-200`, `.duration-300`, `.duration-500`

### Component Patterns

**Buttons:**
- Base: `bg-nature-base text-white rounded-organic font-bold`
- Hover: `hover:shadow-md hover:scale-105` + optional purple glow
- Focus: `focus:outline-none focus-visible:outline-2 focus-visible:outline-offset-2 focus-visible:outline-accent-neon`
- Secondary: `bg-white border-2 border-nature-mid text-nature-dark`

**Cards:**
- `bg-white rounded-organic shadow-base border-2 border-nature-light`
- Hover: `hover:shadow-md hover:scale-[1.02] hover:border-nature-mid transition-all`
- With left border accent: `border-l-4 border-nature-mid`

**Board Squares:**
- Unmarked: `bg-nature-pale text-nature-dark border-2 border-nature-light`
- Marked: `bg-nature-base text-white border-2 border-nature-mid shadow-md`
- Winning: `bg-accent-neon text-white border-2 border-accent-neon shadow-neon-heavy`
- Transitions: `transition-all duration-300` for smooth state changes

**Backgrounds:**
- Default: `bg-gradient-nature` (linear gradient pale→light green)
- Header: `bg-gradient-hero` (deep nature-dark → mid → base)
- Overlay: `bg-overlay` (semi-transparent dark: `rgba(0,0,0,0.5)`)

### Responsive Design
- Mobile-first approach: base styles for mobile, then enhance
- Use media query utilities: `.sm\:text-2xl`, `.md\:gap-4` (at 768px breakpoint)
- Ensure 60px minimum touch targets for buttons
- Test board scaling: 5×5 grid should fit most screens without horizontal scroll

### Accessibility Requirements
- **Focus rings:** All interactive elements must have visible focus indicator (purple outline)
- **Color contrast:** Text must meet WCAG AA (4.5:1 for body text, 3:1 for large text)
- **Reduced motion:** Respect `prefers-reduced-motion: reduce` preference (animations disabled)
- **ARIA labels:** Board squares have `aria-label` and `aria-pressed` attributes
- **Semantic HTML:** Use `<button>`, `<h1>`, etc., not generic divs for interaction

### When to Use What

| Use Case | Recommendation |
|----------|-----------------|
| CTA buttons (Start, Keep Playing) | `bg-nature-base`, `.rounded-organic`, hover glow |
| Secondary buttons (Back, Reset) | `text-accent-neon`, no fill, hover scale |
| Card containers | `bg-white`, `.rounded-organic`, `.shadow-base` |
| Rule/instruction cards | Add `.border-l-4 border-nature-mid` for visual hierarchy |
| Marked squares on board | `bg-nature-base`, strong shadow, checkmark emoji |
| Winning/celebration elements | Neon purple (`bg-accent-neon`), heavy glow shadow |
| Loading/progress indicators | `animate-glow-pulse`, fade-in animation |
| Page transitions | `animate-slide-up` or staggered reveals for lists |

## Docs and References
- Start with `README.md` and `workshop/GUIDE.md`.
- Styling guidance: `.github/instructions/css-utilities.instructions.md`.
- Global rules: `.github/instructions/general.instructions.md`.
- Frontend design guidance: `.github/instructions/frontend-design.instructions.md`.
- Reusable prompts and agents: `.github/prompts/` and `.github/agents/`.
