# Technical Preferences

<!-- project.yaml at the repo root is the machine-readable source of truth for
     engine, specialists, naming, performance, platform, and testing.framework.
     This file is the human-readable LEGACY FALLBACK: agents and skills resolve
     each key from project.yaml first and fall back here only when the
     project.yaml key is absent. /setup-engine dual-writes both.
     Forbidden patterns and allowed libraries are NOT migrated — they live only
     in this file. Populated by /setup-engine; updated as decisions are made. -->

## Engine & Language

- **Engine**: Ren'Py 8.5
- **Language**: Ren'Py script (.rpy) + Python 3; game text in Russian
- **Rendering**: Ren'Py (OpenGL, model-based renderer)
- **Physics**: none

## Input & Platform

<!-- Written by /setup-engine. Read by /ux-design, /ux-review, /test-setup, /team-ui, and /dev-story -->
<!-- to scope interaction specs, test helpers, and implementation to the correct input methods. -->

- **Target Platforms**: [TO BE CONFIGURED — e.g., PC, Console, Mobile, Web]
- **Input Methods**: [TO BE CONFIGURED — e.g., Keyboard/Mouse, Gamepad, Touch, Mixed]
- **Primary Input**: [TO BE CONFIGURED — the dominant input for this game]
- **Gamepad Support**: [TO BE CONFIGURED — Full / Partial / None]
- **Touch Support**: [TO BE CONFIGURED — Full / Partial / None]
- **Platform Notes**: [TO BE CONFIGURED — any platform-specific UX constraints]

## Naming Conventions

- **Classes**: PascalCase (Python classes in init python blocks)
- **Variables**: snake_case, declared with `default` (`anna_points`, `met_boris`)
- **Signals/Events**: n/a — labels snake_case with chapter prefix (`ch01_park`)
- **Files**: snake_case `.rpy` (`ch01.rpy`); images lowercase Latin words with spaces (`anna happy.png`)
- **Scenes/Prefabs**: one `.rpy` file per chapter or route
- **Constants**: UPPER_SNAKE_CASE with `define`

## Performance Budgets

- **Target Framerate**: [TO BE CONFIGURED]
- **Frame Budget**: [TO BE CONFIGURED]
- **Draw Calls**: [TO BE CONFIGURED]
- **Memory Ceiling**: [TO BE CONFIGURED]

## Testing

- **Framework**: [TO BE CONFIGURED]
- **Minimum Coverage**: [TO BE CONFIGURED]
- **Required Tests**: Lint with zero errors; every route and ending reachable; save/load and rollback on each chapter

## Forbidden Patterns

<!-- Add patterns that should never appear in this project's codebase -->
- [None configured yet — add as architectural decisions are made]

## Allowed Libraries / Addons

<!-- Add approved third-party dependencies here -->
- [None configured yet — add as dependencies are approved]

## Architecture Decisions Log

<!-- Quick reference linking to full ADRs in docs/architecture/ -->
- [No ADRs yet — use /architecture-decision to create one]

## Engine Specialists

<!-- Written by /setup-engine when engine is configured. -->
<!-- Read by /code-review, /architecture-decision, /architecture-review, and team skills -->
<!-- to know which specialist to spawn for engine-specific validation. -->

- **Primary**: renpy-specialist
- **Language/Code Specialist**: renpy-specialist
- **Shader Specialist**: renpy-screen-specialist
- **UI Specialist**: renpy-screen-specialist
- **Additional Specialists**: branching-designer, character-artist, script-editor
- **Routing Notes**: script and saves → renpy-specialist; screens, GUI, ATL → renpy-screen-specialist; branch map → branching-designer; Russian text → script-editor

### File Extension Routing

<!-- Skills use this table to select the right specialist per file type. -->
<!-- If a row says [TO BE CONFIGURED], fall back to Primary for that file type. -->

| File Extension / Type | Specialist to Spawn |
|-----------------------|---------------------|
| Game code (`*.rpy`) | renpy-specialist |
| Shaders / transforms (ATL, `renpy.register_shader`) | renpy-screen-specialist |
| UI / screen files (`screens.rpy`, `gui.rpy`) | renpy-screen-specialist |
| Images (`game/images/**`) | character-artist |
| Branch map (`design/branching-map.md`) | branching-designer |
| General architecture review | Primary |
