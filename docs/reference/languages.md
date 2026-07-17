# Languages & translations

Every player-facing gameplay message is translatable, and **each player picks their own
language** — titles, death screens, meeting cards, task lists, and chat feedback resolve
per player. Admin/setup command feedback deliberately stays English.

## Adding a language

1. Create `plugins/SpaceCrews/languages/messages_<iso>.yml` — e.g. `messages_fr.yml`
   (the iso is free-form: `fr`, `de`, `pt_br`…). An empty file is fine.
2. Restart or `/sc reload`. The file **fills itself with the complete English
   catalog** — every key, ready to translate in place.
3. Translate the values you want. Anything left in English simply stays English —
   partial translations are fully supported (per-key fallback).

Set the server-wide default with `default-language: fr` in `config.yml`.

## Players switching

- `/sc lang` — clickable list of available languages, ✔ marks the current one.
- `/sc lang fr` — switches instantly, confirms in the picked language.
- Picks are **persisted** in the stats database: they survive relogs, and on
  [networks](../network.md) with shared MySQL they follow players across servers.

## Translator notes

```yaml
death.title: "&cVous êtes mort"
game.joined: "&e{0} &7a rejoint ({1}/{2})"
```

- `&`-codes color the text (`&c` red, `&l` bold…), exactly like most plugins.
- `{0}`, `{1}`… are placeholders filled in at runtime (names, counts, timers) —
  keep them in your translation, reorder freely.
- The `prefix` key rebrands the chat prefix for that language.
- Game-wide **broadcasts** (join/leave lines, vote announcements) use the *server
  default* language; everything sent to a specific player uses *their* pick.

## For developers

The [API](../api.md) exposes `getLanguages()`, `getLanguage(uuid)`, and
`setLanguage(uuid, iso)` — e.g. to sync the pick from your own menu or a hub plugin.
