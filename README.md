# Polaris Client

Cliente modular para **Minecraft Java 26.2** (Fabric) con estética ártica: más de 60 módulos de render, HUD, cámara,
movimiento y utilidades, un menú propio con buscador, perfiles de configuración y un editor del HUD.

> Polaris Client es software cerrado: este repositorio solo publica las versiones compiladas
> ([Releases](https://github.com/RaulDevStack/polaris-client/releases)). El código fuente no es público.

## Requisitos

| | Versión |
|---|---|
| Minecraft Java | 26.2 |
| [Fabric Loader](https://fabricmc.net/use/) | 0.19.5 o superior |
| [Fabric API](https://modrinth.com/mod/fabric-api) | 0.161.0+26.2 o superior |
| Java | 25 |

## Instalación

1. Instala Fabric Loader para Minecraft 26.2.
2. Descarga `polaris-client-<versión>.jar` de la última [release](https://github.com/RaulDevStack/polaris-client/releases).
3. Copia el `.jar` y Fabric API en la carpeta `mods` de tu instalación de Minecraft.
4. Abre el juego con el perfil de Fabric.

## Uso

- **Right Shift** abre el menú (la tecla se puede cambiar en *Settings*). También hay un botón **✦ Polaris** en la
  pantalla de título y en la de pausa.
- Escribe con el menú abierto para buscar un módulo. Clic en una fila para configurarlo, clic en el interruptor o clic
  derecho para activarlo. Cada módulo puede tener su tecla (pulsar o mantener).
- **Editor del HUD**: *Settings* → *Edit HUD Layout*. Arrastra los elementos, la rueda cambia su tamaño y el clic derecho
  los devuelve a su sitio automático.
- **Waypoints**: **N** abre el menú de waypoints y **B** crea uno rápido con nombre y color (teclas configurables).
- La configuración se guarda en `config/polarisclient/` y admite varios perfiles.

## Módulos

**Combat** — Kill Aura · Target Focus · Damage Indicators · Attack Through Grass

**Movement** — Fly · Bhop · Crawl · Auto Sneak · Moonwalk

**Player** — God Mode · No Fall Damage · Sit · Auto Tool · Auto Eat

**Render** — Entity ESP · Entity Hitbox · Fullbright · No Fog · No Particles · Custom Block Highlight · Ore ESP ·
Ore Borders · Xray · Clouds · Custom Skybox (cielo de día y de noche) · Waypoints · Light Level Overlay · Chunk Borders ·
Nametags · Item Physics · Liquid Flow · Weather · Clear Water · Wavy Water · Wavy Plants · Wavy Leaves · Bushy Leaves ·
Connected Glass

**World** — Fast Place · Fast Break · Auto Replant

**Camera** — Free Camera · Orbital Camera · Zoom

**HUD** — FPS · Coordinates · Speed · CPS · Day Counter · Clock · Compass · Crosshair · Ping · Module List · Armor Status ·
Potion Effects · Held Item Info · Block Info · Target HUD · Keystrokes

**Misc** — Notifications · Inventory Sorter · Chat Utilities · Chat Animations

Los efectos visuales (Bushy Leaves, Connected Glass, Wavy…) usan las texturas que tengas cargadas, así que funcionan con
cualquier paquete de texturas.

## Compatibilidad

- Los efectos que cambian el terreno (Xray, Connected Glass, Bushy Leaves, Wavy Leaves/Plants/Water, Clear Water) usan el
  renderizador de Fabric y el shader de terreno de Minecraft: **no funcionan junto a Sodium o Iris**, ni con paquetes de
  recursos que sustituyen los shaders del terreno.
- Los módulos de movimiento, combate y mundo actúan como lo haría el jugador; en un servidor ajeno pueden estar
  prohibidos o ser detectados por un anticheat. Úsalos en tus propios mundos o donde esté permitido.

## Problemas y sugerencias

Abre un [issue](https://github.com/RaulDevStack/polaris-client/issues) con la versión del cliente, la de Minecraft y,
si es un fallo, el archivo `logs/latest.log`.

## Licencia

© 2026 RaulDevStack. Todos los derechos reservados. Consulta [LICENSE](LICENSE).
