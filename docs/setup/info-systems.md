# Info systems

The crew's counter-intelligence: cameras, the admin table, vitals, and the door
log. All are disabled while **comms** is sabotaged.

## Security cameras

```
/sc setsecurity          # look at the console block
/sc addcamera <id>       # stand at the camera spot, LOOKING the way it should face
/sc removecamera <id>
```

Right-clicking the console lists cameras; picking one teleports the watcher into a
frozen first-person view at the camera point (body **and** head locked). While
watching:

- a **body double** stands at the console — killable, and killing it kills the
  watcher (they die at the console, like being caught at the screens),
- camera points blink flame particles, so alert crew can tell someone is watching,
- an impostor's kill cooldown **pauses** while they watch.

Hotbar items switch cameras or leave the view.

## Admin table

```
/sc setadmin             # look at the table block
/sc addroom <name>       # stand at two opposite corners (run twice)
/sc removeroom <name>
```

The admin GUI shows **living player counts per room** (live, updates while open).
Vented players count at their vent's room — the classic admin tell. Define rooms
generously; anything outside every room shows under "elsewhere". Rooms also power
the Detective's case files.

## Vitals

```
/sc setvitals            # look at the panel block
```

One entry per player: green OK / red DEAD. Deaths show here immediately — placing
vitals somewhere central makes body-camping riskier.

## Door log (MIRA-style)

```
/sc setdoorlog           # look at the log console
/sc addsensor <id>       # stand on the sensor point
/sc removesensor <id>
```

Living players crossing within 1.5 blocks of a sensor are logged (5s per-player
per-sensor cooldown, last 20 entries). The console prints
`[12s ago] Alex → hall-east`.
