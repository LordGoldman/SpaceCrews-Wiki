# FAQ & troubleshooting

## The arena shows "not set up" / won't start

`/sc info <arena>` prints the checklist — playable needs the world loaded,
a waiting spot, at least one spawn, and min ≤ max. If the world isn't loaded at
boot, SpaceCrews loads arena worlds itself (and re-resolves when world managers
load them late) — check the folder name matches `world:` in the arena yml.

## Players don't get colored skins

Crew colors need **Mojang-signed** textures — fill `skins.yml`
([guide](setup/skins.md)). Colors without textures still work as identity slots.
Note: you always see your **own** original skin; others see your crew color.

## Max players is lower than I set

The number of configured colors in `skins.yml` is a hard cap — colors are unique
per game. Add more colors to raise the ceiling.

## Somebody got teleported out / used another plugin's command mid-game

Leaving the game world by any means removes the player from the game cleanly
(inventory restored, "left" broadcast). That's intentional — no phantom roster
members.

## The kill sword shows in players' hands

It shouldn't — held items are hidden at the packet level. If they show, PacketEvents
failed to hook; check the boot log for the PacketEvents version line and update it.

## Meetings reveal deaths too early / too late

Deaths are secret by design until a meeting starts, then the colored death list
prints. Vitals/cameras/admin can reveal information earlier — that's their job;
don't install other plugins that broadcast quit/death messages inside game worlds.

## Corpses don't appear

Packet corpses need clients on **MC 1.20.2+**. Kills still work on older clients —
there's just no body to report, so crews rely on vitals and absence.

## Can I run multiple games on one map at once?

Yes — every game clones the template world into its own instance and deletes it
afterwards. Never build in `spacecrews_*` worlds; they're disposable clones.

## Players can't open chests / doors / beds on my map

By design — inside a game **every vanilla block and entity interaction is locked**
(chests, furnaces, levers, beds, shulkers, doors, armor stands, item frames,
pressure plates…). Only SpaceCrews stations react to clicks, so decorated maps are
grief-proof and clicks never have side effects. Build consequences:

- use **open archways** for passage (or [door groups](setup/sabotage-doors.md#doors)
  for closable ones) — wooden doors won't open for players,
- decorate freely: containers, frames, and stands are safe from players,
- task stations placed ON levers/buttons won't toggle them — only the minigame opens.

## Reload safety

`/sc reload` re-reads arenas. For plugin updates, restart the server — jar hot-swaps
are not supported (packet listeners and world clones don't survive them).

## Where do I report bugs / ask for help?

You can join the discord server where you can contact me directly: https://discord.gg/geWNKWA9VJ
