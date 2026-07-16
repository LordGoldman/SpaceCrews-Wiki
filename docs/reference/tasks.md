# Task library

Every built-in task type, usable with `/sc addtask <id>`. **Common** tasks are
shared by all crew; **short**/**long** are rolled per player. *Visual* tasks
broadcast an effect at the station on completion. *(2-stage)* types need a second
station via `/sc addtask2`.

Preview any of them in-game with `/sc tasktest` or the out-of-game browser
(`/sc tasks`).

## Classics

| Id | Task | Pool | Minigame |
|---|---|---|---|
| `wiring` | Fix Wiring | common | connect matching wire colors |
| `swipe_card` | Swipe Card | common | click the moving cursor in the timing window |
| `id_code` | Enter Id Code | common | type the 4-digit code on a keypad |
| `insert_keys` | Insert Keys | common | insert and turn the keys |
| `replace_parts` | Replace Parts | common (2-stage) | fetch, then fit the parts |
| `scan_boarding_pass` | Scan Boarding Pass | common | hold the pass on the scanner |
| `roast_marshmallow` | Roast Marshmallow | common (timed) | start roasting, come back |
| `simon` | Simon Says | long | repeat the flashing sequence, 5 rounds |
| `asteroids` | Clear Asteroids | long · visual | shoot 20 spawning asteroids |
| `scan` | Submit Scan | long · visual | stand still 10s in the scan ring |
| `upload` | Upload Data | short (2-stage) | download, then upload elsewhere |
| `divert` | Divert Power | short (2-stage) | flip the breaker, accept at the target |
| `manifolds` | Unlock Manifolds | short | press 1–10 in order |
| `o2_filter` | Clean O2 Filter | short | clear the leaves |
| `shields` | Prime Shields | short · visual | tap the red hexes |
| `garbage` | Empty Garbage | short · visual | hold the lever while it drains |
| `clean_vent` | Clean Vent | short | scrub a vent — flushes & blocks it while cleaning |

## Timed background (start it, come back later)

`inspect_sample` (59s) · `reboot_wifi` (60s) · `develop_photos` (60s) ·
`run_diagnostics` (90s) · `help_critter` (30s) · `cook_fish` (20s) — all long pool
except noted above.

## Hold-to-fill

`fuel_engines` (2-stage) · `water_jug` (2-stage) · `fill_canisters` ·
`process_data` · `measure_weather` · `decontaminate` · `start_fans` (2-stage) ·
`open_waterways` (2-stage)

## Click the targets

`towels` · `shells` · `repair_drill` · `polish` · `clean_toilet` ·
`crank_generator` · `mine_ores` · `hoist_supplies` (2-stage) · `sort_samples` ·
`store_artifacts` · `water_plants` (2-stage) · `prep_vegetables` (2-stage) ·
`weather_node` (2-stage) · `arcade` · `throw_frisbee` · `sandcastle`

## Press in order

`breakers` (7) · `sort_records` · `assemble_artifact` · `unlock_safe` ·
`chart_course` · `make_burger` · `buy_beverage` · `dress_mannequin` ·
`put_away_pistols` · `put_away_rifles`

## Align the slider

`monitor_tree` (4 sliders) · `align_engine` (2-stage) · `align_telescope` ·
`record_temperature` · `find_signal` · `rewind_tapes`

## Charge & release

`calibrate` (×3) · `lift_weights` (×3) · `fix_shower` · `fix_antenna` · `steering`

## Addon tasks

Plugins can register their own minigames through the
[Developer API](../api.md#custom-task-minigames) — they appear here automatically
(tab-complete, browser, progress, stats).
