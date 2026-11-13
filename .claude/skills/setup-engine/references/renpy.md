# /setup-engine — Ren'Py (the visual novel engine)

> Part of `/setup-engine`. `SKILL.md` names when to read this file; the settings it
> resolved and the rules under its later headings still apply here.

Read when the engine is **RenPy** (`/setup-engine renpy`, or no argument in this
edition: it is set up for Ren'Py only). It replaces Sections 2, 3, 6, 7 and 7.5
and gives the values Sections 4, 5 and 5.5 write; Sections 8, 9 and 12 still
apply. Never load `godot-language-config.md` or `web.md`.

**In this file:** R1 The version · R2 The values to write · R3 The reference docs ·
R4 A new Ren'Py project · R5 The specialist agents

## R1. The version

The pin is in `docs/engine-reference/renpy/VERSION.md` (Ren'Py 8.5). Ask the
user which Ren'Py version is installed (Launcher → bottom of the window, or
`renpy.sh --version`) and record it in the `Installed at pin time` row. If it is
older than 8.4, warn that features listed in `breaking-changes.md` under 8.4 and
8.5 are not available and offer to pin the installed version instead. Never
look up "latest" without telling the user; an upgrade is Section 11.

## R2. The values to write (Sections 4, 5 and 5.5)

**CLAUDE.md** (Section 4), import line `@docs/engine-reference/renpy/VERSION.md`:

```markdown
- **Engine**: Ren'Py 8.5 (visual novel engine)
- **Language**: Ren'Py script (`.rpy`) + Python 3
- **Game language**: Russian
- **Build System**: Ren'Py Launcher → Build Distributions
- **Asset Pipeline**: PNG/WebP in `game/images/`, lowercase Latin names with spaces (`anna happy.png`)
```

**technical-preferences.md** (Section 5): Engine Ren'Py 8.5, language Ren'Py
script + Python 3. Naming: labels and variables snake_case (`ch01_park`,
`anna_points`); Python classes PascalCase; constants UPPER_SNAKE_CASE; files
snake_case `.rpy`; image files lowercase Latin words separated by spaces.
Specialists: Primary `renpy-specialist`; Language/Code `renpy-specialist`;
UI `renpy-screen-specialist`; Shader `renpy-screen-specialist`; Additional
`branching-designer`, `character-artist`, `script-editor`. Routing:
`*.rpy` → `renpy-specialist` (screens in `screens.rpy`/`gui.rpy` →
`renpy-screen-specialist`); `game/images/**` → `character-artist`;
`design/branching-map.md` → `branching-designer`.

**`project.yaml`** (Section 5.5):

```yaml
engine:
  name: "RenPy"
  version: "8.5.3"
  language: "Ren'Py script + Python 3"
  rendering: "Ren'Py (OpenGL, model-based renderer)"
  physics: "none"

specialists:
  code: "renpy-specialist"
  shader: "renpy-screen-specialist"
  ui: "renpy-screen-specialist"
  additional: ["branching-designer", "character-artist", "script-editor"]
```

- `RenPy` exactly, with that capitalisation: the check is case-sensitive.
- No `engine.code_root`: `game` comes from the engine table
  (`.claude/engines/engines.tsv`).
- `commands.build` / `commands.test` stay unset unless the user gives the path
  to the Ren'Py SDK; then `commands.test` may be
  `"<sdk>/renpy.sh" . lint` (Windows: `"<sdk>\renpy.exe" . lint`).

## R3. The reference docs (Sections 6 and 7)

The reference ships in `docs/engine-reference/renpy/`. The knowledge gap is
MEDIUM: the model knows Ren'Py 8.0–8.3; 8.4 and 8.5 are covered in
`breaking-changes.md`. Write nothing unless the user pins another version; then
search the official changelog and add what changed.

## R4. A new Ren'Py project (Section 7.5)

Ren'Py projects are created by the Launcher (Create New Project), which writes
`game/gui.rpy`, `game/screens.rpy`, `game/options.rpy`, `game/script.rpy` and
the GUI images. Do not hand-write those files. Tell the user:

1. Download the Ren'Py SDK from https://www.renpy.org/latest.html
2. Launcher → Preferences → Projects Directory → the folder that holds this repository
3. Create New Project → choose this folder's name, the resolution (1920×1080 is
   the usual choice) and a colour scheme
4. Run `/setup-engine renpy` again so the studio records the installed version

If `game/` already exists, record it as it is and change nothing.

## R5. The specialist agents (Section 9)

The Ren'Py agents are `renpy-specialist` and `renpy-screen-specialist`; both
already carry a Version Awareness section pointing at
`docs/engine-reference/renpy/`. Nothing to add.
