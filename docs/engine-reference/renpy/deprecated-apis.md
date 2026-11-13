# Ren'Py — Deprecated and avoided APIs

| Avoid | Use instead | Why |
|-------|-------------|-----|
| Python 2 syntax (`print "x"`, `unicode()`, `%` on bytes) | Python 3 | Ren'Py 8 runs Python 3 (3.12 since 8.4) |
| `$ var = value` as the first assignment of a game variable | `default var = value` | Not saved correctly, breaks old saves and rollback |
| `define` for anything that changes | `default` | `define` values are not saved |
| `ui.*` functions | Screen language (`screen`) | The `ui` API is legacy |
| `renpy.say` in screens' code | Character objects and `say` statements | Rollback and history |
| `im.*` image manipulators (`im.Scale`, `im.MatrixColor`…) | Transforms: `Transform(..., zoom=, matrixcolor=)` | Manipulators are legacy and slower |
| `pygame_sdl2` imports | Ren'Py APIs | Reported removed in 8.5 |
| `config.script_version` in a new game | Leave unset | Reverts newer behaviour |
