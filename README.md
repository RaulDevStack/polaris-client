# Polaris Client

A modular client for **Minecraft Java 26.3 and 26.2** (Fabric) with an arctic look: more than 60 render, HUD, camera, movement
and utility modules, its own menu with search, configuration profiles and a HUD editor.

> Polaris Client is closed-source software: this repository only publishes the compiled builds
> ([Releases](https://github.com/RaulDevStack/polaris-client/releases)). The source code is not public.

## Requirements

| | Minecraft 26.3 | Minecraft 26.2 |
|---|---|---|
| Polaris Client file | `polaris-client-0.1.3_26.3.jar` | `polaris-client-0.1.0.jar` |
| [Fabric Loader](https://fabricmc.net/use/) | 0.20.1 or newer | 0.19.5 or newer |
| [Fabric API](https://modrinth.com/mod/fabric-api) | 0.164.0+26.3 or newer | 0.161.0+26.2 or newer |
| Java | 25 | 25 |

## Installation

1. Install Fabric Loader for your Minecraft version (26.3 or 26.2).
2. Download the Polaris Client `.jar` for that version from the [releases](https://github.com/RaulDevStack/polaris-client/releases)
   (see the table above).
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
  can be changed). The **▶** button next to a waypoint makes Player Bot walk there.
- **Player Bot**: pick a task in the module settings and turn it on (see below).
- Settings are stored in `config/polarisclient/` and support multiple profiles.

## Modules

**Combat** — Kill Aura · Target Focus · Damage Indicators · Attack Through Grass

**Movement** — Fly · Bhop · Crawl · Auto Sneak · Moonwalk

**Player** — God Mode · No Fall Damage · Sit · Auto Tool · Auto Eat · Player Bot

**Render** — Entity ESP · Entity Hitbox · Fullbright · No Fog · No Particles · Custom Block Highlight · Ore ESP ·
Ore Borders · Chest ESP · Xray · Clouds · Custom Skybox (day and night skies) · Waypoints · Light Level Overlay · Chunk Borders ·
Nametags · Item Physics · Liquid Flow · Weather · Clear Water · Wavy Water · Wavy Plants · Wavy Leaves · Bushy Leaves ·
Connected Glass

**World** — Fast Place · Fast Break · Auto Replant

**Camera** — Free Camera · Orbital Camera · Zoom

**HUD** — FPS · Coordinates · Speed · CPS · Day Counter · Clock · Compass · Crosshair · Ping · Module List · Armor Status ·
Potion Effects · Held Item Info · Block Info · Target HUD · Keystrokes

**Misc** — Notifications · Inventory Sorter · Inventory Tweaks · Shulker Preview · Chat Utilities · Chat Animations

### Player Bot

Player Bot does tasks for you by moving your character with normal keys, turns and clicks (no teleports). It finds
its own path (A*): it jumps up blocks, swims, and avoids lava, fire, cactus, long falls and hostile mobs.

| Task | What it does |
|---|---|
| **Auto Walk** | Walks to coordinates (`x y z` or `x z`, `~` for your current one), to a waypoint (also from the **▶** button in the waypoints menu) or to where the Free Camera is (it can keep following the camera). |
| **Auto Chop** | Finds the nearest tree, walks to it, cuts every log, picks up the wood and replants a sapling. Then goes for the next tree. |
| **Semi Chop** | Break the first log of a tree and the bot cuts the rest. |
| **Auto Mine** | Looks for the ores you choose (diamond, iron, gold… or any block id), digs a tunnel to them, mines the whole vein and picks up the drops. |
| **Vein Mine** | Mine one ore and the bot mines the rest of the vein. |

It picks the best tool in your hotbar, doesn't break blocks next to water or lava or under sand and gravel, and never
breaks chests or other blocks with contents. It stops when your health is low or your inventory is full, and pauses
while you press a movement key (*Manual Override*). The planned path can be drawn on screen.

Visual effects (Bushy Leaves, Connected Glass, Wavy…) use whatever textures you have loaded, so they work with any
resource pack.

## Compatibility

- Terrain effects (Xray, Connected Glass, Bushy Leaves, Wavy Leaves/Plants/Water, Clear Water) rely on Fabric's renderer
  and Minecraft's terrain shader: **they don't work together with Sodium or Iris**, nor with resource packs that replace
  the terrain shaders.
- Movement, combat, world modules and Player Bot act the way a player would; on third-party servers they may be forbidden or
  detected by an anticheat. Use them in your own worlds or where they are allowed.

## Issues and suggestions

Open an [issue](https://github.com/RaulDevStack/polaris-client/issues) with the client version, the Minecraft version
and, for bugs, your `logs/latest.log` file.

## License

© 2026 RaulDevStack. All rights reserved. See [LICENSE](LICENSE).
