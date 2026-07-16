# The game loop

## Lobby → countdown → running

Players join via `/sc join <arena>`, the browser (`/sc games`), or as a
[party](parties-settings.md). Everyone waits at the arena's waiting spot, picks a
color, and the host tweaks settings via the **Customize** item. The countdown
starts at the configured minimum; at zero, roles are assigned (big
IMPOSTOR/CREWMATE reveal titles — impostors also learn their partners), tasks are
dealt, and everyone teleports to the spawn circle.

## Vision

The killer feature: **per-viewer vision culling**. The living see only players
within their vision radius *and* in line of sight — nametags never render through
walls, so positions can't leak. Crew radius is short; impostors see further; the
lights sabotage shrinks crew vision drastically. Ghosts see everyone. Held items
are hidden from others (the kill sword doesn't give impostors away).

## Kills

Impostors right-click near a crewmate with the kill item (cooldown per party
settings, fresh after each meeting). The victim becomes a ghost; a **packet
corpse** drops at the spot (MC 1.20.2+ renders the sleeping body; the corpse wears
the victim's crew color). Impostors can never kill impostors. Guardian-Angel
shields block kills silently.

## Deaths stay secret

Nobody is told about a death — no chat message, no tab change. The dead become
invisible ghosts who roam freely, chat only with other ghosts, and keep completing
tasks. Deaths become public **only when a meeting starts**, in the meeting reveal:

> ☠ Dead: **Red** Alex, **Cyan** Bob

## Meetings & voting

Meetings start from the **emergency button** (limited uses + cooldown per player)
or by **reporting a body** (a report also cancels a reactor/O2 crisis — vanilla
rule). Everyone teleports to the spawn circle, living players are frozen and chat
opens for the discussion, then the voting GUI: click a player or skip. Ties and
skip-majorities eject no one. With *confirm ejects* on, the ejection card reveals
whether they were an impostor and how many remain.

## Winning

- **Crew** — complete every task, or eject all impostors.
- **Impostors** — reach parity (impostors ≥ living crew), or let a critical
  sabotage (reactor/O2) run out.

Victory/defeat titles show per player; XP is awarded from your
[progression settings](../reference/config.md), and everyone returns to the hub.

## Disconnects & leaving

Leaving (`/sc leave`), quitting, or being teleported out of the game world by any
other plugin removes you cleanly (inventory restored — everyone is told you left).
On [network mode](../network.md) game servers, a mid-game disconnect keeps your
roster slot for a grace window: reconnect and you resume as a ghost with your tasks
and end-of-game XP intact.
