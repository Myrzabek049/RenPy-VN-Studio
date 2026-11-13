# Ren'Py 8 — Current best practices for this studio

## Layout

```
game/
  script.rpy          # label start + jump to chapter 1 only
  characters.rpy      # define Character objects
  variables.rpy       # every `default` and `default persistent.*`
  script/ch01.rpy     # one file per chapter
  routes/<name>.rpy   # one file per route
  screens.rpy, gui.rpy, options.rpy
  images/  audio/  fonts/
  tl/<language>/      # translations (source language is Russian)
```

## Russian-language game

- The source text is Russian. Write it directly in the script; no `_()` needed
  for dialogue and menu text, Ren'Py extracts it for translation.
- Use a font with full Cyrillic coverage and set it in `gui.rpy`
  (`gui.text_font`, `gui.name_text_font`, `gui.interface_text_font`).
  Test the letters «ё», «й», and the quote marks «» and em dash —.
- Set `config.language` only for translations; the base language stays the
  script itself.
- Typography: quotes «», dash —, ellipsis …; `script-editor` checks this.

## Variables and saves

- Every changing variable: `default` in `variables.rpy`.
- Cross-playthrough unlocks: `default persistent.<name> = ...`.
- After the first public build, never rename or delete a label a save could
  be on: leave the old label with a `jump` to the new one.

## Branching

- Route points / flags are plain `default` integers or booleans with clear
  names (`anna_points`, `met_boris`).
- Endings are chosen in one place (`label ending_select:`), reading the flags.
- `branching-designer` keeps `design/branching-map.md` in sync with the labels.

## Quality

- Run Lint (Launcher → Check Script) before every build: zero errors.
- Play every route at least once per milestone; test rollback, skip, save/load.
- Use the 8.5 automated testing framework for smoke tests of each route.
