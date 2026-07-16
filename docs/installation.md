# Installation

## Requirements

| | |
|---|---|
| Server | Spigot or Paper **1.16+** (Paper recommended) |
| Java | 8+ (whatever your MC version requires) |
| Required plugin | [PacketEvents](https://www.spigotmc.org/resources/packetevents-api.80279/) (free) |
| Optional | PlaceholderAPI · Multiverse (or any world manager) · Redis + Velocity/Bungee for [network mode](network.md) |

!!! info "Why PacketEvents?"
    Vision culling, corpses, crew-color skins, and camera body doubles are packet
    tech. PacketEvents is GPL-licensed, so it ships as a separate free plugin rather
    than being bundled — exactly like plugins that require ProtocolLib.

## Install

1. Drop `SpaceCrews-x.y.z.jar` **and** PacketEvents into `plugins/`.
2. Restart the server (don't use plugin managers for first install).
3. Check the log for `SpaceCrews vx.y.z enabled` — the data folder
   `plugins/SpaceCrews/` now contains `config.yml`, `skins.yml`,
   `languages/messages_en.yml`, and `arenas/example.yml`.

## First-boot checklist

- **Template world**: every arena lives in a **dedicated world** (never the main
  world). Games run in throwaway clones of it, so the template stays pristine.
  SpaceCrews loads arena worlds itself — Multiverse is optional.
- **Skins**: paste crew-color textures into `skins.yml`
  ([how](setup/skins.md)) — colors work without textures, players just keep their
  own skins until then.
- **Storage**: defaults to SQLite. Networks should switch to MySQL
  ([config reference](reference/config.md)).

Next: the [Quickstart](quickstart.md).
