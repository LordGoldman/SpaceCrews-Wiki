# PlaceholderAPI

Install [PlaceholderAPI](https://www.spigotmc.org/resources/placeholderapi.6245/)
and the expansion registers automatically (no ecloud download needed).

| Placeholder | Value |
|---|---|
| `%spacecrews_level%` | level (from XP + the configured curve) |
| `%spacecrews_xp%` | lifetime XP |
| `%spacecrews_xp_into%` | XP progressed into the current level |
| `%spacecrews_xp_needed%` | XP needed for the next level |
| `%spacecrews_games%` | games played |
| `%spacecrews_wins%` | wins |
| `%spacecrews_winrate%` | win rate (integer percent) |
| `%spacecrews_kills%` | impostor kills |
| `%spacecrews_tasks%` | tasks completed |
| `%spacecrews_ingame%` | current arena id, or `none` |

Stats resolve from an in-memory cache (loaded on join), so they're safe in
scoreboards, tab, chat formats, and holograms at any refresh rate.

!!! warning "No alive/dead placeholders"
    By design there is no "is alive" placeholder — deaths are secret until meetings,
    and exposing them would let other plugins leak the core information of the game.
