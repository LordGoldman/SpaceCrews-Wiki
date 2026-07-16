# Developer API

Compile against **`spacecrews-api-<version>.jar`** (shipped with the plugin) — never
the plugin jar; its internals are not API. Add `depend: [SpaceCrews]` (or
`softdepend`) to your `plugin.yml`, then grab the service:

```java
SpaceCrewsAPI api = Bukkit.getServicesManager().load(SpaceCrewsAPI.class);
```

All methods are main-thread unless noted.

## Games & players

```java
Collection<GameView> games = api.getGames();
GameView game = api.getGame(player.getUniqueId());   // or by game id
if (game != null) {
    game.broadcast("§eHello from my addon!");
    PlayerView view = game.getPlayer(player.getUniqueId());
    Role role = view.getRole();                      // CREWMATE / IMPOSTOR
}
api.joinGame(player, "skeld");                       // same path as /sc join
api.leaveGame(player);
```

!!! danger "Spoiler data"
    `PlayerView.getRole()` and `isAlive()` are the game's secrets. Never expose them
    to living players — SpaceCrews itself hides deaths until meetings.

## Stats

```java
api.getStats(uuid, stats -> {           // async lookup, callback on the main thread
    if (stats != null) {
        int level = stats.getLevel();
        int wins  = stats.getWins();
    }
});
```

## Parties

```java
UUID leader = api.getPartyLeader(uuid);              // null = not in a party
Collection<UUID> members = api.getPartyMembers(uuid);
```

## Custom task minigames

The flagship extension point: register a minigame and it becomes a first-class task
type — builders place stations with `/sc addtask <id>`, it appears in the task
browser, and completions count toward progress, stats, and XP.

```java
api.registerTask(new CustomTask() {
    public String getId() { return "button_mash"; }
    public String getDisplay() { return "Button Mash"; }
    public TaskDifficulty getDifficulty() { return TaskDifficulty.SHORT; }
    public boolean isVisual() { return false; }

    public void onOpen(Player player, TaskHandle handle) {
        // run ANY mechanic — a chest GUI, chat game, movement challenge — then:
        handle.complete();   // progress, task bar, stats, XP all handled
        // or handle.abort();
    }
});
```

Register once in `onEnable`. Ids must match `[a-z0-9_-]+` and be unique.

## Events

Package `com.spacecrews.api.event` — standard Bukkit listeners:

| Event | Fired |
|---|---|
| `GameStateChangeEvent` | every lifecycle transition (lobby, countdown, running, meeting, ending) |
| `PlayerJoinGameEvent` / `GameEndEvent` | roster joins / game over (winners + losers lists) |
| `RoleAssignEvent` | roles dealt at start |
| **`PreKillEvent`** (cancellable) | after every kill check passes, before the death — cancel = silent veto, no cooldown consumed |
| `ImpostorKillEvent` | a kill happened |
| **`PreMeetingEvent`** (cancellable) | button/report about to start a meeting, before side effects |
| `MeetingStartEvent` / `PlayerEjectEvent` | meeting started / vote resolved |
| `SabotageTriggerEvent` / `SabotageFixEvent` | sabotage lifecycle |
| `PlayerVentEvent` | vent use |
| `TaskCompleteEvent` | a task fully completed |
| `PlayerXpGainEvent` / `PlayerLevelUpEvent` | progression |

```java
@EventHandler
public void onPreKill(PreKillEvent event) {
    if (isInSafeZone(event.getVictim())) {
        event.setCancelled(true);   // the impostor keeps their cooldown; nothing happens
    }
}
```

## Roadmap

Pluggable world providers (slime worlds) and a custom special-roles API.
