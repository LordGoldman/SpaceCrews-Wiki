# Parties & settings

## Parties

```
/sc party invite <player>     # 60s invite
/sc party accept | deny
/sc party leave | disband
/sc party info
```

The **leader picks the game** — joining any arena or browser entry brings every
online member along, and a party is never split across games (capacity is checked
for the whole group). On [networks](../network.md), the whole party travels between
servers together and survives members being away in a game.

## The lobby Customize menu

Every player in a game lobby gets the **Customize** item (name tag, slot 5):

- **Colors page** — pick any free crew color (taken ones show who has them).
- **Party settings page** — all game options; visible to everyone, editable only
  by the **host** (first player in, needs `spacecrews.host`). Left-click raises,
  right-click lowers, toggles flip.
- **Roles page** — enable/configure the nine [special roles](roles.md).

## Settings highlights

The per-arena yml sets defaults; hosts adjust per game:

| Group | Options |
|---|---|
| Core | impostor count, min/max players (capped by color count), countdown |
| Kills | kill cooldown, kill distance |
| Meetings | discussion time, voting time, emergencies per player, emergency cooldown, confirm ejects, anonymous votes |
| Movement | player speed, crew/impostor vision radius, lights-sabotage vision |
| Vents | vent max stay, re-vent cooldown |
| Sabotage | sabotage cooldown, critical timer |
| Tasks | common/short/long counts, visual tasks on/off, task-bar updates (always/meetings/never) |
| Extras | spawn pick after meetings, game mode (classic / Hide n Seek + its knobs) |

## The games browser

`/sc games` lists joinable games (with live player counts) and playable arenas —
click to join or start fresh. On network lobbies it shows every server's games and
auto-picks the least-loaded server for new games.
