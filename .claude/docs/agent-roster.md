# Agent Roster

The following agents are available. Each has a dedicated definition file in
`.claude/agents/`. Use the agent best suited to the task at hand. When a task
spans multiple domains, the coordinating agent (usually `producer` or the
domain lead) should delegate to specialists.

Which model an agent runs on is set by the `model:` line in its own file;
`model-tiers.md` lists the agents that pin one. Every other agent runs on the
session's model.

## Tier 1 -- Leadership Agents
| Agent | Domain | When to Use |
|-------|--------|-------------|
| `creative-director` | High-level vision | Major creative decisions, pillar conflicts, tone/direction |
| `technical-director` | Technical vision | Architecture decisions, tech stack choices, performance strategy |
| `producer` | Production management | Sprint planning, milestone tracking, risk management, coordination |

## Tier 2 -- Department Lead Agents
| Agent | Domain | When to Use |
|-------|--------|-------------|
| `game-designer` | Game design | Choice systems, route points, unlocks, gallery, pacing of play |
| `lead-programmer` | Code architecture | System design, code review, API design, refactoring |
| `art-director` | Visual direction | Style guides, art bible, asset standards, UI/UX direction |
| `audio-director` | Audio direction | Music direction, sound palette, audio implementation strategy |
| `narrative-director` | Story and writing | Story arcs, world and lore, characters, themes, tone of the novel |
| `qa-lead` | Quality assurance | Test strategy, bug triage, release readiness, regression planning |
| `release-manager` | Release pipeline | Build management, versioning, changelogs, deployment, rollbacks |
| `localization-lead` | Internationalization | String externalization, translation pipeline, locale testing |

## Tier 3 -- Specialist Agents
| Agent | Domain | When to Use |
|-------|--------|-------------|
| `branching-designer` | Branch structure | Routes, choices, flags, route points, endings, reachability, `design/branching-map.md` |
| `writer` | Dialogue and narration | Scenes, dialogue, narration, choice texts, UI microcopy (in Russian) |
| `script-editor` | Editing and proofreading | Russian grammar and typography, character voices, continuity across routes |
| `character-artist` | Visual assets | Sprite sheets, expressions, outfits, layered-image specs, backgrounds, CG, art briefs and prompts |
| `sound-designer` | Sound design | SFX lists, ambience, music cues per scene, mixing notes |
| `ux-designer` | UX flows | Menus, save/load, history, readability, input on PC and phone |
| `accessibility-specialist` | Accessibility | Text size, contrast, self-voicing, colour-blind safety, auto-forward |
| `qa-tester` | Test execution | Route walkthroughs, typo and continuity bugs, save/rollback tests |
| `prototyper` | Rapid prototyping | A quick playable scene or demo to test an idea |
| `community-manager` | Community | Announcements, devlogs, patch notes, player feedback |

## Engine Agents — Ren'Py

This studio is set up for one engine: **Ren'Py 8** (`engine.name: RenPy`).

| Agent | Area | When to Use |
| ---- | ---- | ---- |
| `renpy-specialist` | Ren'Py engine lead | .rpy script, labels and jumps, characters, `default`/`persistent` variables, saves and rollback, translations, lint, builds |
| `renpy-screen-specialist` | Screens and presentation | `gui.rpy`, `screens.rpy`, menus, gallery, ATL transforms, transitions, layered images, phone layouts |
