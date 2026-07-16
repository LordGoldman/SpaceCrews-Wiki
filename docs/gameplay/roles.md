# Special roles

Nine optional roles layered on top of Crewmate/Impostor. All **default to off** —
the party host enables them per game in the lobby menu (count + assignment chance +
per-role options). Rolled at game start after base roles; each player gets a
private reveal.

## Crew roles

| Role | Ability |
|---|---|
| **Scientist** | A portable **Vitals** item — check everyone's alive/dead status anywhere, on a cooldown. |
| **Engineer** | Limited **vent access** (own cooldown + max uses) — the only crew who can vent. |
| **Noisemaker** | Dying triggers a loud alert + a flame beacon at the body — killers can't kill quietly. |
| **Tracker** | Tag a nearby player with the **Track** compass; a live action-bar shows their distance and direction for the duration. |
| **Detective** | Every kill freezes a **case file** (which room everyone was in at that moment). Touch a suspect to interrogate — limited charges per case. |

## Guardian Angel

A crew role assigned **after death**: eligible dead crew become the Guardian Angel
and can cast `/sc protect <player>` — a timed shield that blocks one kill.
The blocked impostor hears the shatter (their cooldown restarts at half); the
protection is announced at the next meeting, so the information game stays fair.

## Impostor roles

| Role | Ability |
|---|---|
| **Viper** | Kills dissolve the corpse after a delay — unreportable bodies. |
| **Phantom** | **Vanish** temporarily (invisible to living crew; impostors and ghosts still see them). Can't kill while vanished; sabotage and venting still work. Appearing/vanishing has a visible smoke tell. |
| **Shapeshifter** | **Shift** into any player's appearance (their crew color and name) for a duration — with a public portal-burst tell, and optional evidence husks left at shift spots. Meetings force everyone back to themselves. |

## Ghost play

Every dead player keeps contributing: ghosts see everyone, chat in the ghost-only
channel, and complete their remaining tasks via `/sc tasks` (clickable list near
the station). Dead impostors can still open the sabotage panel with `/sc sabotage`.
