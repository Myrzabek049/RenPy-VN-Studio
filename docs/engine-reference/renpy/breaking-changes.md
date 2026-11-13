# Ren'Py — Breaking and notable changes since the model's cutoff

Verified 2026-11-13 against the release announcements. When in doubt, read
https://www.renpy.org/doc/html/incompatible.html for the exact wording.

## 8.5 (pinned)

- **Automated testing framework.** Ren'Py 8.5 adds a framework for automated
  tests of games. Use it for branch and smoke tests instead of hand-rolled
  scripts; check the docs for the current statement syntax before writing one.
- **Local labels relaxed.** Local labels (`.name`) can be declared under any
  global label.
- **Unicode 17** and more emoji supported.
- **Live2D:** 8.5.3 requires Live2D 5.3 when Live2D is used, and Live2D works on
  the Web platform.
- Reported by users: `pygame_sdl2` was removed in 8.5. Do not import it or
  rely on third-party code that does.

## 8.4

- **Python 3.12** on every platform.
- **Text shaping with HarfBuzz.** Glyphs and spacing can differ from 8.3. To get
  the old behaviour:
  ```renpy
  style default:
      shaper "freetype"
  ```
- **Automatic emoji font** when needed. To turn it off:
  ```renpy
  style default:
      emoji_font None
  ```
- Faster script loading, persistent data and OpenGL drawing.

## General rule

`define config.script_version` reverts many incompatible changes at the cost of
newer features. Do not set it in a new project.
