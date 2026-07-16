# Arenas & the setup wizard

Everything is configured **in-game**, standing in the arena's template world. The
resulting file is `plugins/SpaceCrews/arenas/<id>.yml` — hand-editable, but the
commands are safer (`arenas/example.yml` documents every section).

!!! warning "Template worlds"
    Use a **dedicated world per map**, never the main world. Each game clones the
    template into a private instance world (`spacecrews_<arena>_<game>`), runs
    there, and deletes it afterwards — several games can run the same map at once.

## Two ways to build

**Guided** — `/sc setup <id>` (new or existing arena) starts the step-by-step
wizard with clickable buttons. Recommended for your first map.

**Expert** — `/sc create <id>` (new) or `/sc edit <id>` (existing) opens a setup
session; run the commands below in any order. Both modes write the same session, so
you can mix them freely — the wizard offer button appears after create/edit too.

## Session lifecycle

| Command | Effect |
|---|---|
| `/sc setup <id>` | create-or-edit + guided wizard |
| `/sc create <id>` / `/sc edit <id>` | open a session (expert mode) |
| `/sc session` | list everything configured so far |
| `/sc save` | write the yml + playability checklist |
| `/sc cancel` | discard the session |
| `/sc info <id>` | full status of a saved arena |
| `/sc enable <id>` / `/sc disable <id>` | toggle availability |
| `/sc delete <id> confirm` | remove an arena |
| `/sc world <name>` / `/sc exit` | load & visit a world / return |

## Required points

| Command | How | Sets |
|---|---|---|
| `/sc setwaiting` | stand | pre-game waiting spot (in-arena) |
| `/sc addspawn` (×4+) | stand | meeting/gather spawns |
| `/sc seteject` | stand | where ejected players spectate |
| `/sc setbutton` | look at a block | generates the emergency-button structure |
| `/sc setmin` / `setmax` / `setimpostors <n>` | — | player counts (host-adjustable per party) |

`/sc removespawn` (nearest) and `/sc clearspawns` fix mistakes.

## Everything else

- [Task stations](tasks.md) — `/sc addtask <type>`
- [Sabotage & doors](sabotage-doors.md) — `/sc setsabotage`, `/sc adddoor`
- [Info systems](info-systems.md) — cameras, admin, vitals, door log, rooms
- [Map toolkit](map-toolkit.md) — vents, ziplines, platform, decon, spawn picking

## Testing

`/sc testmode on` lets a game start solo and disables the auto-win check — you are
always the impostor (with real, completable tasks). `/sc tasktest` opens a sandbox
of every task minigame with no stations needed. Turn test mode **off** for
production.
