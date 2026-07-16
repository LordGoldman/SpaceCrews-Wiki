# Stats, XP & levels

## Lifetime stats

Games, wins, kills, and tasks completed are recorded per player — SQLite by
default (`plugins/SpaceCrews/stats.db`), or a shared MySQL database for
[networks](../network.md). `/sc stats [player]` opens the profile GUI (head, level
+ XP progress bar, games, win rate, kills, tasks).

## XP & levels

XP is awarded when a game ends (aborted games award nothing):

| Source | Default XP |
|---|---|
| Playing a game | 20 |
| Winning | +40 |
| Per task completed | 5 |
| Per impostor kill | 10 |
| Per correct vote (you voted out a real impostor) | 5 |

Level costs grow linearly: level 2 costs 100 XP, each next level +25 more — all
tunable under `progression:` in [config.yml](../reference/config.md). Level-ups
flash a ⭐ title; the in-game chat shows a `[level]` prefix.

## Display surfaces

- `/sc stats` GUI and the meeting-lobby sidebar
- [PlaceholderAPI](../reference/placeholders.md) — `%spacecrews_level%`,
  `%spacecrews_wins%`, `%spacecrews_winrate%`… for scoreboards, tab plugins,
  holograms, chat formats
- The [Developer API](../api.md) exposes stats for custom leaderboards/rewards
