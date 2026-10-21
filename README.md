# Polaris Client

A modular client for **Minecraft Java 26.2** (Fabric) with an arctic look: more than 60 render, HUD, camera, movement
and utility modules, its own menu with search, configuration profiles and a HUD editor.

> Polaris Client is closed-source software: this repository only publishes the compiled builds
> ([Releases](https://github.com/RaulDevStack/polaris-client/releases)). The source code is not public.

## Requirements

| | Version |
|---|---|
| Minecraft Java | 26.2 |
| [Fabric Loader](https://fabricmc.net/use/) | 0.19.5 or newer |
| [Fabric API](https://modrinth.com/mod/fabric-api) | 0.161.0+26.2 or newer |
| Java | 25 |

## Installation

1. Install Fabric Loader for Minecraft 26.2.
2. Download `polaris-client-<version>.jar` from the latest [release](https://github.com/RaulDevStack/polaris-client/releases).
3. Put the `.jar` and Fabric API in the `mods` folder of your Minecraft installation.
4. Launch the game with the Fabric profile.

## Usage

- **Right Shift** opens the menu (the key can be changed in *Settings*). There is also a **✦ Polaris** button on the
  title screen and the pause screen.
- Start typing with the menu open to search for a module. Click a row to configure it; click the switch or right-click
  the row to toggle it. Every module can have its own key (toggle or hold).
- **HUD editor**: *Settings* → *Edit HUD Layout*. Drag elements around, use the mouse wheel to resize them and
  right-click to send them back to their automatic position.
- **Waypoints**: **N** opens the waypoints menu and **B** creates a quick waypoint with a name and a color (both keys
  can be changed).
- Settings are stored in `config/polarisclient/` and support multiple profiles.

## Modules

**Combat** — Kill Aura · Target Focus · Damage Indicators · Attack Through Grass

**Movement** — Fly · Bhop · Crawl · Auto Sneak · Moonwalk

**Player** — God Mode · No Fall Damage · Sit · Auto Tool · Auto Eat

**Render** — Entity ESP · Entity Hitbox · Fullbright · No Fog · No Particles · Custom Block Highlight · Ore ESP ·
Ore Borders · Xray · Clouds · Custom Skybox (day and night skies) · Waypoints · Light Level Overlay · Chunk Borders ·
Nametags · Item Physics · Liquid Flow · Weather · Clear Water · Wavy Water · Wavy Plants · Wavy Leaves · Bushy Leaves ·
Connected Glass

**World** — Fast Place · Fast Break · Auto Replant

**Camera** — Free Camera · Orbital Camera · Zoom

**HUD** — FPS · Coordinates · Speed · CPS · Day Counter · Clock · Compass · Crosshair · Ping · Module List · Armor Status ·
Potion Effects · Held Item Info · Block Info · Target HUD · Keystrokes

**Misc** — Notifications · Inventory Sorter · Chat Utilities · Chat Animations

Visual effects (Bushy Leaves, Connected Glass, Wavy…) use whatever textures you have loaded, so they work with any
resource pack.

## Compatibility

- Terrain effects (Xray, Connected Glass, Bushy Leaves, Wavy Leaves/Plants/Water, Clear Water) rely on Fabric's renderer
  and Minecraft's terrain shader: **they don't work together with Sodium or Iris**, nor with resource packs that replace
  the terrain shaders.
- Movement, combat and world modules act the way a player would; on third-party servers they may be forbidden or
  detected by an anticheat. Use them in your own worlds or where they are allowed.

## Issues and suggestions

Open an [issue](https://github.com/RaulDevStack/polaris-client/issues) with the client version, the Minecraft version
and, for bugs, your `logs/latest.log` file.

## License

© 2026 RaulDevStack. All rights reserved. See [LICENSE](LICENSE).
