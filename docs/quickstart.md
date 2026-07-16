# Quickstart

From zero to a playable game in about 15 minutes. You need a map built in a
**dedicated world** (import one with a world manager or drop the folder in and use
`/sc world <folder>`).

## 1. Set up an arena (guided)

```
/sc setup mymap
```

The wizard walks you through every point with clickable chat buttons:

1. **Waiting spot** — where players stand before the game starts
2. **Spawns** — 4+ meeting/gather points (players teleport here for meetings)
3. **Emergency button** — look at a floor block; a glass case with the red button
   is generated for you
4. **Eject spawn** — where ejected players spectate from
5. **Sabotage stations** (optional) — lights, reactor pads, O2, comms
6. **Vents** (optional) — look at each vent block; they auto-link into a chain
7. **Tasks** — add stations with `/sc addtask <type>` ([task library](reference/tasks.md))
8. **Save**

Prefer commands? Everything the wizard does has an expert command —
see [Arena setup](setup/arenas.md).

## 2. Verify

```
/sc info mymap      # per-point checklist + what's missing
/sc enable mymap
```

## 3. Test it solo

```
/sc testmode on     # solo start allowed, auto-win disabled
/sc join mymap
/sc start
```

You're always the impostor in solo test mode (best coverage: kill, vent, sabotage —
and you get real completable tasks). Try every task minigame without stations via
`/sc tasktest`. End with `/sc leave`, and **turn test mode off** afterwards.

## 4. Play for real

Players join with `/sc join mymap` or the browser (`/sc games`), group up with
`/sc party invite <name>`, pick colors and settings via the lobby **Customize**
item, and the countdown starts automatically at the configured minimum.

!!! tip
    Put a sign/NPC hub command in your lobby that runs `/sc games` — the browser is
    the friendliest entry point.
