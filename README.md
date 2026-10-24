# Polaris Client

A modular client for **Minecraft Java 26.3 and 26.2** (Fabric) with an arctic look: more than 60 render, HUD, camera, movement
and utility modules, its own menu with search, configuration profiles and a HUD editor.

> Polaris Client is closed-source software: this repository only publishes the compiled builds
> ([Releases](https://github.com/RaulDevStack/polaris-client/releases)). The source code is not public.

## Requirements

| | Minecraft 26.3 | Minecraft 26.2 |
|---|---|---|
| Polaris Client file | `polaris-client-0.1.7_26.3.jar` | `polaris-client-0.1.0.jar` |
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

**Movement** — Fly · Elytra Fly · Boat Fly · Bhop · Crawl · Auto Sneak · Moonwalk

**Player** — God Mode · No Fall Damage · Sit · Auto Tool · Auto Eat · Auto Elytra · Auto Totem · Auto Refill · Player Bot

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
its own path (A*): it jumps up blocks, swims, climbs ladders and vines, opens and closes wooden doors and fence gates,
and avoids lava, fire, cactus, long falls and hostile mobs. When there is no other way it places blocks to climb up
(pillar) or to cross a gap (bridge), using your scaffold blocks or any plain block (never ores, valuable blocks or
wood), and moves them from your inventory to the hotbar if needed. If it makes no progress for a few seconds
(*Stuck Timeout*) it looks for a different path that avoids that spot.

If a log or ore is too high to reach, it builds up with a couple of blocks instead of hitting it while jumping.

Movement is meant to look natural: it walks in straight lines instead of zigzagging between blocks, turns smoothly
(fast at first, easing in) and looks a little ahead along its path.

With **Self Defense** on, the bot fights back during a task, then carries on with it. Once a fight starts it finishes
it first (no mining between hits):
- It hits hostile mobs that come close with your best weapon (most damage per second, counting Sharpness), timing
  full-strength **critical hits**.
- If something shoots you (a skeleton, for example), the shooter becomes its main target: it goes after it and kills it
  first, even in the middle of another fight.
- **Dodge Arrows**: it predicts where arrows and other projectiles will land and steps aside from the ones that would
  hit you.
- **Creepers**: it sprint-hits them for extra knockback, backs off, and runs away if one starts to swell.
- **Groups**: when more than 2 hostile mobs are close (configurable), it stops fighting and runs toward the task's
  destination along a path that keeps away from them. If the task has no destination, it runs to a safe spot away from
  the group. It keeps the same spot instead of changing its mind every step, and it only stops running once the mobs
  are well behind.

| Task | What it does |
|---|---|
| **Auto Walk** | Walks to coordinates (`x y z` or `x z`, `~` for your current one), to a waypoint (also from the **▶** button in the waypoints menu) or to where the Free Camera is (it can keep following the camera). |
| **Auto Chop** | Finds the nearest tree, walks to it, cuts every log, picks up the wood and replants a sapling. Then goes for the next tree. For tall trees it climbs up by placing blocks and removes them afterwards. |
| **Semi Chop** | Break the first log of a tree and the bot cuts the rest. Moving cancels it. |
| **Auto Mine** | Looks for the ores you choose (diamond, iron, gold… or any block id), digs a tunnel to them, mines the whole vein and picks up the drops. |
| **Vein Mine** | Mine one ore and the bot mines the rest of the vein. Moving cancels it. |
| **World Edit** | Builds or breaks simple shapes between two corners: a rectangle or a circle, filled, outline only (*Walls*) or hollow with floor and roof (*Shell*). With corners at different heights the shape is 3D (a box or a cylinder). Press the *Corner Key* (G) once for corner 1 and again for corner 2, at the block you look at, with a live preview as you move. A third press clears both. Then press the *Start Key* (H) or the **Start / Stop** button. *Build* places the chosen *Material* from your inventory, bottom to top; *Break* breaks every block of the shape, top to bottom. The preview shows the corners and the blocks still to build or break. |
| **Auto Combat** | For leaving your character AFK: it does no task, it stays where it is and only defends itself with the Self Defense rules (creepers, shooters, groups…), always holding your best weapon (taken from the inventory if needed). It never goes farther than *Max Distance From Spot* (12 blocks by default) and ignores mobs outside that area. When health gets low it runs to the safest spot inside that area, keeps an eye on the mobs, and eats to regenerate (golden apples first). Against a skeleton it decides whether to kill it first or eat first: if it can kill it quickly and still have health to spare, it fights; otherwise it eats behind cover, out of the skeleton's sight. It always finishes a bite once it starts, then walks back to its spot. |

It picks the best tool in your hotbar, doesn't break blocks next to water or lava or under sand and gravel, and never
breaks chests or other blocks with contents. It stops when your health is low or your inventory is full, and pauses
while you press a movement key (*Manual Override*). The planned path can be drawn on screen.

### Auto Elytra, Auto Totem and Auto Refill

- **Auto Elytra**: when you fall more than *Fall Height* blocks, it puts on the elytra from your inventory (swapping out
  your chestplate) and opens it. After landing (even after crashing into a wall) it puts your chestplate back on (*Swap Back*).
- **Auto Totem**: always keeps a totem of undying in your offhand. When one is used up, it puts in the next one.
- **Auto Refill**: when a hotbar stack (or your offhand) runs out, it refills the slot with another stack of exactly
  the same item, never a different one. It takes it from your inventory or, if the only other stack is in the hotbar,
  from there. A broken tool or weapon is replaced with another of the same kind
  (*Refill Tools*).

### Elytra Fly and Boat Fly

**Elytra Fly** gives elytra a new, free control while gliding. You fly where you look with W (up or down too, like
normal elytra), S and A/D move backward and sideways, jump rises and sneak descends. Let go of the keys and you stop
and hover in place instead of falling. Speed follows your keys smoothly, so it still feels like gliding
(*Responsiveness*). With *Auto Start* you start gliding as soon as you fall with elytra on.

**Boat Fly** keeps any boat you ride floating in the air: jump makes it rise and the sprint key makes it descend (sneak
still gets you out). W, S, A and D steer it as usual.

**Orbital Camera** uses the same pathfinding for *Smart Movement*: you steer with the movement keys and your character
jumps up blocks, steps around small obstacles, opens doors and stops at the edge of long drops instead of falling.
Without Smart Movement it walks the same way (turning smoothly toward where you steer and always moving forward, which
servers handle better) but goes straight where you point, with no automatic jumps or avoiding.

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
