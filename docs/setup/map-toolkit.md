# Map toolkit

Movement and map mechanics beyond the basics: vents, ziplines, the gap platform,
decontamination corridors, and post-meeting spawn picking.

## Vents

```
/sc addvent <id>         # look at the vent block (trapdoors look great)
/sc linkvent <a> <b>     # connect two vents (repeat to build the network)
/sc unlinkvent <a> <b>   /  /sc removevent <id>
```

Impostors right-click a vent to slip inside (invisible to the living, hotbar items
navigate between linked vents). Anti-camp: a max stay (`ventMaxSeconds`) auto-ejects,
and re-venting has a cooldown — both party settings. Engineers get limited crew-side
vent access when that role is enabled; in Hide n Seek vents become hider "Hide" spots.

The **Clean Vent** task ([placement](tasks.md#placement-guidelines)) flushes out and
blocks its bound vent while someone cleans it.

## Ziplines

```
/sc addzip <id>          # look at endpoint A's block, run it, look at endpoint B's, run again
/sc removezip <id>
```

Anyone right-clicks an endpoint to glide the line — **downhill rides twice as
fast** (build sloped lines for asymmetric escapes). Riders are pinned, kill-immune,
and can't kill until they land; meetings drop them off safely.

## Gap platform

```
/sc addplatform <id>     # same two-endpoint capture
/sc removeplatform <id>
```

The Airship-style ferry: **one rider at a time**. The platform docks at whichever
side it last traveled to — calling it from the far side costs the empty travel-back
wait, in the open, in full view. There is no physically moving block; decorate the
gap however you like (a floating disc, a gondola).

## Decontamination corridors

```
/sc adddecon <id>                                  # stand at two opposite corners of the corridor
/sc bindecon <id> <doorGroupA> <doorGroupB> [seconds]
/sc removedecon <id>
```

Create the two door groups with `/sc adddoor` first — one per end of the corridor.
When a living player enters the region, **both doors seal**, the spray runs
(default 3s, clouds + hiss), then they reopen (5s cooldown). The classic
chase-breaking airlock between map sections.

!!! warning
    Don't reuse decon door groups as sabotage doors.

## Post-meeting spawn picking

```
/sc addpickspawn <name>      # stand on the spot (one per room/area)
/sc removepickspawn <name>
```

With **2+ pick spawns** and the party setting *Spawn Pick After Meetings* enabled,
living players get an 8-second "Where to?" menu after each meeting — pick a room or
close it to stay at the meeting spawns.
