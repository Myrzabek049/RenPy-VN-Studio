# Ren'Py — Version Reference

This studio is set up for one engine: **Ren'Py 8**, for a visual novel written
in Russian. Every engine question goes to `renpy-specialist` (script, saves,
builds) or `renpy-screen-specialist` (screens, GUI, ATL).

| Field | Value |
|-------|-------|
| **Engine Version** | Ren'Py 8.5 |
| **Installed at pin time** | NOT DETERMINED — run the launcher (or `renpy.sh --version`) and record the installed version here. |
| **Release Date** | 8.5.3 "We Can Go to the Moon", May 15, 2026 |
| **Project Pinned** | 2026-11-13 |
| **Last Docs Verified** | 2026-11-13 (release announcements for 8.4 and 8.5) |
| **LLM Knowledge Cutoff** | May 2025 |
| **Python** | Python 3 (3.12 since Ren'Py 8.4). Never Python 2 syntax. |
| **Game language** | Russian (`ru`). Source text is written in Russian; other languages go in `game/tl/<language>/` |

## Knowledge Gap Warning

May 2025 is a floor for every model the studio runs on. The model knows Ren'Py
8.0–8.3 well. 8.4 (2025) and 8.5 (late 2025 / 2026) came after or near the
cutoff: check `breaking-changes.md` before relying on text rendering, testing
or label rules from memory, and say "unverified" when an API is not covered here.

## Installed-Version Gap Warning

This file pins 8.5. If the installed SDK is older (8.3 or earlier), features
listed in `breaking-changes.md` under 8.4 and 8.5 are not available. Check the
`Installed at pin time` row first.

## Where to check

- Official documentation: https://www.renpy.org/doc/html/
- Changelog: https://www.renpy.org/doc/html/changelog.html
- Incompatible changes: https://www.renpy.org/doc/html/incompatible.html
- Russian translation of the docs (community): https://doc-renpy-ru.vercel.app/
- Downloads: https://www.renpy.org/latest.html
