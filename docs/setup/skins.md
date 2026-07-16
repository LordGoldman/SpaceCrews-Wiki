# Crew-color skins

In a game every player wears a **crew color**: a colored crewmate skin (packet-based
— nothing changes outside the game) plus a color identity used in menus, meeting
reveals, and corpses. Colors are unique per game, and the number of configured
colors is the **hard player cap** per game.

## skins.yml

One entry per color:

```yaml
colors:
  red:
    display: "&cRed"
    material: RED_WOOL        # menu icon; empty = derived from the id
    from-player: ""           # copy a Mojang account's skin by name, OR:
    value: ""                 # paste a skin texture (base64), signed or not
    signature: ""             # its Mojang signature if you have one
```

Three ways to provide the texture — all cached back into the file automatically:

1. **`value` + `signature`** — a Mojang-signed pair (e.g. from
   [mineskin.org](https://mineskin.org)): used directly, works offline.
2. **`value` only** — an unsigned base64: sent to MineSkin for signing at boot
   (staggered for their rate limit; retried next boot on failure).
3. **`from-player`** — a Mojang account name whose current skin is fetched and
   signed.

!!! info "Why signatures?"
    Minecraft clients only render skin textures carrying a valid Mojang signature —
    even on offline-mode servers. That's why raw base64 alone can't be applied and
    MineSkin exists.

`/sc setskin <color> <onlinePlayer>` grabs a player's skin for a color live.

## Behavior

- Colors auto-assign on join (first free); players swap via the lobby
  **Customize** menu (1s cooldown). Renamed/custom color ids are fine — set
  `material:` for the menu icon.
- Corpses wear the color the victim died in; the meeting death reveal prints names
  in their colors.
- Colors without textures still work as identity slots — players keep their own
  skins until you add textures.
- The Shapeshifter and Mushroom Mixup reuse this engine for disguises/scrambles
  (Mixup needs textured colors).

!!! note "Self-view"
    Players see their **own** original skin (their client renders it locally);
    everyone else sees the crew color. This is a known cosmetic limitation.
