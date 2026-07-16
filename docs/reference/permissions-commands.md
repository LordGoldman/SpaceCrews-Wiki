# Commands & permissions

## Permissions

| Permission | Default | Grants |
|---|---|---|
| `spacecrews.play` | everyone | joining/browsing games, parties, stats, the task browser |
| `spacecrews.host` | OP | editing party settings & roles in the lobby menu (as game host) |
| `spacecrews.setup` | OP | arena setup, admin, and test commands |

## Player commands

| Command | Description |
|---|---|
| `/sc join [arena]` | join a game (party leaders bring their party) |
| `/sc leave` | leave your game |
| `/sc start` | force-start (host) |
| `/sc games` | the games browser |
| `/sc tasks` | in-game: your task list (ghosts: clickable) — outside: the task browser |
| `/sc stats [player]` | stats profile GUI |
| `/sc party invite/accept/deny/leave/disband/info` | parties |
| `/sc hub` | go to the main lobby |
| `/sc protect [player]` | Guardian Angel shield (dead GA only) |
| `/sc sabotage` | sabotage panel (impostor ghosts) |

## Admin commands

| Command | Description |
|---|---|
| `/sc setup <id>` | **guided arena setup** (recommended) |
| `/sc create / edit / delete <id> confirm` | arena lifecycle (expert mode) |
| `/sc enable / disable <id>` | availability |
| `/sc info <id>` | status + missing-points checklist |
| `/sc list` | arenas & live games |
| `/sc tp <id>` · `/sc world <name>` · `/sc exit` | visit template worlds & return |
| `/sc reload` | reload arenas from disk |
| `/sc stop [arena]` | force-end live game(s) |
| `/sc kick <player>` | remove a player from their game |
| `/sc testmode [on/off]` | solo test sandbox |
| `/sc tasktest [type]` | task minigame sandbox |
| `/sc setmainlobby [server <name>]` | set the return hub |
| `/sc setskin <color> <player>` | grab a player's skin for a crew color |

## Setup-session commands

Active after `/sc setup`, `create`, or `edit` — every point of an arena:
`setwaiting`, `addspawn/removespawn/clearspawns`, `seteject`, `setbutton`,
`setsabotage <kind>`, `addvent/removevent/linkvent/unlinkvent`,
`addtask/addtask2/removetask`, `adddoor/removedoor`, `addzip/addplatform`,
`adddecon/bindecon/removedecon`, `addpickspawn/removepickspawn`, `addroom`,
`addcamera/addsensor`, `setsecurity/setadmin/setvitals/setdoorlog`,
`setmin/setmax/setimpostors`, `session`, `save`, `cancel`.

Details per system in the [Arena setup](../setup/arenas.md) section. Everything is
tab-completed, including existing ids.
