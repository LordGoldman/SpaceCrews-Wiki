# Sabotage & doors

Impostors open the sabotage panel from their hotbar lever. Which sabotages appear
depends on what your arena has configured — a station missing from the map is
simply hidden from the panel.

## Fix stations

All set by **looking at the block** and running:

```
/sc setsabotage <lights | reactor-a | reactor-b | o2-a | o2-b | comms-a | comms-b>
```

| Sabotage | Stations | Effect | Fix |
|---|---|---|---|
| **Lights** | `lights` | crew vision shrinks hard | shared 5-switch panel — anyone can flip switches, including impostors re-flipping them covertly |
| **Reactor** | `reactor-a` + `reactor-b` (both required) | critical countdown — impostors win at zero | both pads held simultaneously |
| **O2** | `o2-a` (+ optional `o2-b`) | critical countdown | 4-digit code shown at the pad; with both pads, the same code on each (vanilla) |
| **Comms** | `comms-a` (+ optional `comms-b`) | task list/bar blackout, cameras/admin/vitals/doorlog disabled | radio-tune dial (both pads if two) |

Critical timers use the per-arena/party `criticalSabotageSeconds`. AU rules apply:
**reporting a body cancels a critical**, emergency meetings can't be called during
one, and the sabotage cooldown restarts **when fixed**, not when triggered.

## Doors

```
/sc adddoor <group> [sealBlock]     # look at one corner, run, look at the opposite corner, run again
/sc removedoor <group>
```

Each run of the two-step capture fills a cuboid wall region (repeat for L-shaped
doorways, ≤400 blocks per capture). Impostors seal a group from the panel for 10
seconds (30s per-group cooldown); blocks swap to `sealBlock` (default IRON_BARS)
and restore automatically — meetings pop everything open.

!!! warning
    Door groups bound to a [decontamination corridor](map-toolkit.md#decontamination-corridors)
    must **not** also be used as sabotage doors — the two systems would fight over
    the same blocks.

## Mushroom Mixup

No station needed — if your `skins.yml` colors have textures, the panel always
offers Mixup: every living player's color scrambles for 10 seconds.
