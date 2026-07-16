# Network mode

Run one or more **lobby** servers (players browse and queue) and any number of
**game** servers (arenas run there), connected by **Redis** behind a Velocity or
BungeeCord proxy. Single-server installs ignore all of this.

## You need

- A Redis server (any recent version).
- A Velocity or BungeeCord proxy with all servers registered.
- SpaceCrews + PacketEvents on every lobby and game server.
- **MySQL recommended** (`storage.type: mysql`) so stats/XP are shared network-wide.

## Game servers

```yaml
server-type: GAME
server-name: game-1          # MUST match this server's name in the proxy config
redis:
  host: 127.0.0.1
  port: 6379
  password: ""
network:
  rejoin-grace-seconds: 60   # mid-game disconnect: how long the slot waits (0 = off)
main-lobby:
  mode: server
  server: lobby              # players return here when a game ends
storage:
  type: mysql
  mysql: {host: 127.0.0.1, port: 3306, database: spacecrews, user: sc, password: "..."}
```

Set up arenas on game servers as usual — template worlds live there.

## Lobby servers

```yaml
server-type: LOBBY
server-name: lobby
redis: {host: 127.0.0.1, port: 6379, password: ""}
storage:
  type: mysql
  mysql: {..same database..}
```

Lobby servers need no arenas. `/sc games` there shows every server's live games and
arenas; clicking **reserves** the slots (whole parties travel together, never
split) and sends players through the proxy straight into the game.

## What you get

- **Cross-server browser** — game listings refresh every 5s; a crashed server's
  listings expire on their own.
- **Reservations** — capacity is booked before anyone travels; two lobbies can't
  oversell a game.
- **Autoscaling** — arena rows auto-pick the least-loaded game server hosting that
  map, spinning a fresh instance if needed.
- **Rejoin grace** — a mid-game disconnect becomes a ghost immediately (no gameplay
  limbo), but the slot survives `rejoin-grace-seconds`; reconnecting to any lobby
  routes the player back to resume as a ghost (tasks + end-of-game XP intact).
- **Party travel** — members away in a game show "(away playing)" and the party
  survives their absence.

!!! note "Graceful degradation"
    Redis unreachable or `server-name` missing → the server logs a warning and runs
    standalone. Keep one lobby server per network for parties (multi-lobby party
    sync is a roadmap item).
