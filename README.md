
# aradar v1.2

## Description

This addon for [GZDOOM](https://zdoom.org/index) provides an onscreen radar.
The radar is a recreation combining the features of _Earth Defense Force 4.1_, _Earth Defense Force 5_, and _Earth Defense Force: Iron Rain_.

The mod is designed to be universal, so simply load it alongside any other mods to begin using it.

## Credits

- All code in this mod falls under the attached [LICENSE](./LICENSE.md).
- All images in the _graphics/_ directory are by arookas.
- _alert.flac_ is by Yuke's and ripped from _Earth Defense Force: Iron Rain_.

This mod wouldn't be possible without these wonderful folks:

| **Greyfalll** | **Accensus** &bullet; **phantombeta** |
|:-:|:-:|
| support / testing | scripting help |

## Features

The radar provides various indicators and displays them relative to the player's view.
The player's position is at the center of the radar, with north in front of the player.

### Blips

A _blip_ is a colored circle representing a particular actor.
_Blips_ will usually appear once they enter line of sight for the first time;
for monsters, they also appear once the monster has woken up from gunfire.
If a _blip_ is beyond the visible distance of the radar, it will change into a pointed arrow along the edge.

The table below describes the various colors of _blips_:

| Default Color  | Target | Technical |
|-------:|:-------|-----------|
| Red    | Living monsters | Has `ISMONSTER` and `COUNTKILL` flags. |
| Blue   | Living allies  | Has `FRIENDLY` and `SHOOTABLE` flags. |
| Yellow | Key&nbsp;items / interactive&nbsp;objects | Derived from `Powerup` or `Key`, or has `USESPECIAL` or `BUMPSECIAL` flags. |
| Green  | Regular items | Derived from `Inventory` and has no `COUNTITEM` flag. |
| Magenta  | Collectible items | Derived from `Inventory` and has `COUNTITEM` flag. |
| White  | Objects | Has either `SHOOTABLE` or `FRIENDLY` flag (but not both). |

### Pips

In multiplayer, other players will be represented by _pips_ (**p**layer bl**ips**).
These are larger circles marked with the first letter of the player's name.
A _pip_ will display in the respective player's profile color.

### Blots

When a player dies, a light-red _blot_ will appear for a few seconds in the area where he or she died.

### Field of View

The bright region in the radar indicates the player's current field of view.
Any indicators such as _blips_ inside this region will be in front of the player in the 3D view.

### Altitude

When a particular indicator (_blip_, _pip_, or _blot_) is above or below the player, it will display higher or lower on the radar.
For _blips_ and _pips_, a vertical line will indicate the relative altitude.
This feature can be turned off in the [settings](#customization).

### Map Area

The edges of the map will be displayed as an outlined red box on the radar.

### Alert

When a notable amount of red _blips_ (monsters) appear in a short period of time, an audio indicator will play.
This indicator can be turned off and the volume adjusted in the [settings](#customization).

## Customization

This addon provides many options.
The settings are located in a dedicated submenu under _HUD&nbsp;Options_>_Radar&nbsp;Options_.
You can turn the radar on/off, change the appearance, and control specific features:

| Option | Description |
|-------:|-------------|
| _Display&nbsp;position_ | Controls which corner of the screen to display the radar, or turn off the radar entirely. |
| _Enable&nbsp;in&nbsp;deathmatch_ | Enables players to see the radar even in deathmatch. This is a host setting and cheats must be enabled to turn this on. |
| _Draw&nbsp;under&nbsp;HUD_ | Whether the radar displays under or over existing HUD elements. |
| _Radar&nbsp;scale_ | Global display scale of the radar and indicators. |
| _Radar&nbsp;transparency_ | Radar's transparency (alpha channel) to tune its intrusiveness. |
| _Radar&nbsp;X&nbsp;offset_ | Horizontal offset of the radar display, in screen pixels. Positive values move radar towards the center of the screen. |
| _Radar&nbsp;Y&nbsp;offset_ | Vertical offset of the radar display, in screen pixels. Positive values move radar towards the center of the screen. |
| _Blip&nbsp;types_ | Enables/disables specific radar blip types. |
| _Blip&nbsp;colors_ | Allow the user to customize colors for each blip type. |
| _Show&nbsp;blip&nbsp;altitude_ | Turn this off to hide [altitude indicators](#altitude). This is useful for smaller screens. |
| _Show&nbsp;respawned&nbsp;items_ | If `sv_itemrespawn` is enabled, items are allowed to reappear on the radar after respawning. Turning this off will keep the item's _blip_ hidden after being picked up the first time. This option can help clean up the radar for larger maps with lots of items. |
| _Alert&nbsp;volume_ | Changes the volume of the [alert sound](#alert). Set to zero to turn the feature off entirely. |
