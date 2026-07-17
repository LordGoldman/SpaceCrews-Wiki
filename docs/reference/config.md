# config.yml

`plugins/SpaceCrews/config.yml` — regenerated with defaults on first boot.

```yaml
server-type: SINGLE          # SINGLE | LOBBY | GAME  (see Network mode)
server-name: ""              # proxy name of this server (LOBBY/GAME only)

redis:                       # network mode only
  host: 127.0.0.1
  port: 6379
  password: ""

network:
  rejoin-grace-seconds: 60   # mid-game disconnect slot survival (0 = off)

storage:
  type: sqlite               # sqlite | mysql
  mysql:
    host: 127.0.0.1
    port: 3306
    database: spacecrews
    user: root
    password: ""

main-lobby:                  # where players go after leaving a game
  mode: location             # location (this server) | server (proxy)
  location: "world,x,y,z,yaw,pitch"   # set with /sc setmainlobby
  server: lobby                       # set with /sc setmainlobby server <name>

progression:
  enabled: true
  xp:
    played: 20
    win: 40
    per-task: 5
    per-kill: 10
    per-correct-vote: 5
  level-base: 100            # XP for level 1 -> 2
  level-growth: 25           # each next level costs this much more

scoreboard:
  enabled: true              # in-game sidebar; disable if another plugin owns it

world:
  provider: auto             # world cloning backend

default-language: en         # languages/messages_<iso>.yml

debug:
  test-mode: false           # NEVER true in production (/sc testmode toggles it)
```

## Other files

| File | Contents |
|---|---|
| `arenas/<id>.yml` | one per arena — built by the setup commands; `example.yml` documents every section |
| `skins.yml` | crew colors + textures ([guide](../setup/skins.md)) |
| `languages/messages_en.yml` | the full message catalog — rebrand or translate freely |
| `languages/messages_<iso>.yml` | add any file (e.g. `messages_fr.yml`) and it becomes a selectable language: players switch with `/sc lang`, picks persist, missing keys fall back to English. `default-language` sets the server-wide default |
| `stats.db` | SQLite stats (when `storage.type: sqlite`) |
