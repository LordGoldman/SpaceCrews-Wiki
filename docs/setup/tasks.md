# Task stations

Tasks are the crew's win condition and their alibi. Each **station** binds a task
type to a block in your map; a game assigns each crewmate common/short/long tasks
from the party settings, and impostors get a **fake** list to pretend with.

## Commands

| Command | How | Effect |
|---|---|---|
| `/sc addtask <type>` | look at the station block | adds a station (key `task_N`) |
| `/sc addtask2 <key>` | look at the second block | stage 2 for two-stage types (upload, divert, align engine) |
| `/sc removetask <key>` | — | remove a station |

The `<type>` argument tab-completes with all ~53 built-in types (plus any addon
tasks) — full list with descriptions in the [task library](../reference/tasks.md).

## Placement guidelines

- Match the fiction: put *Swipe Card* in an admin room, *Fuel Engines* near
  engines, *Submit Scan* in a medbay. Stations right-click any block, so levers,
  buttons, consoles, and blocks all work.
- **Clean Vent** must be placed within 3 blocks of a [vent](map-toolkit.md#vents)
  — it flushes out and blocks that vent while cleaning.
- **Visual tasks** (scan, asteroids, shields, garbage…) broadcast particles at the
  station — place them where onlookers can verify from a distance.
- Two-stage tasks want their stations in *different rooms* — the walk is the
  gameplay.
- Spread stations across the whole map; task routes create the traffic impostors
  hunt in.

## How players interact

- Right-click a station → the minigame GUI opens (only if that station is on the
  player's list; impostors get silence — standing at stations is what faking looks
  like).
- The **Tasks book** (hotbar) and the sidebar show the personal list; the boss bar
  shows crew progress (per the party's task-bar setting).
- Ghosts keep completing tasks from `/sc tasks` (clickable list, must float near
  the station).

## Try before you build

`/sc tasktest` (in a test-mode game) or `/sc tasks` (outside any game — the player
task browser) opens every minigame with no station needed.
