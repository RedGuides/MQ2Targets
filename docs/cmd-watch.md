---
tags:
  - command
---

# /watch

## Syntax

<!--cmd-syntax-start-->
```eqcommand
/watch [add|delete|notify target|n] [loc] <locname>
```
<!--cmd-syntax-end-->

## Description

<!--cmd-desc-start-->
Modify configurations for MQ2Targets, from targets that appear on the HUD to sounds that are played when triggered, and everything in between.
<!--cmd-desc-end-->

## Options

| Option | Description |
|--------|-------------|
| **`help`** | displays a helpful list of commands. |
| **`add ["<spawn search>"] [notify] [sound <#>] [nohud] [priority <#>] [/all]`** | Using *add* by itself will add your current target to the watch list. <br><br>When specifying a [Spawn Search](../macroquest/reference/general/spawn-search.md) string it's best enclosed in quotes, e.g. "npc loc 100 55 radius 30 kobold". <br><br>*notify* controls the popup window upon detection. <br><br>*sound &lt;#&gt;* specifies the sound # to play upon detection.  <br><br>*nohud* doesn't show the spawn in the hud, but keeps it available for the TLO:Targ. <br><br>*priority &lt;#&gt;* assigns priority for the spawn, useful for the TLO. <br><br>*/all* adds the entry to the [all] zones section. |
| **`{delete|remove} ["<spawn search>"] [<index #>] [/all]`** | *delete&#124;remove* with no options will remove your current target from the watch list. |
| **`list`** | Will show all entries in the watch list. |
| **`timestamp`** | Toggles the timestamp option. |
| **`mq2chat`** | Enables or disables output to [ChatWnd](../macroquest/plugins/core-plugins/chatwnd/README.md) |
| **`all`** | enables or disables using the [all] option in the config file. If disabled, only entries in labeled for specific zones will be used. |
| **`debug`** | additional output useful for bug tracking |
| **`limit <#>`** |  |
| **`{x|y} <loc>`** | sets the display coordinates of the HUD on your screen. In pixels, 0 being top/left |
| **`increment <#>`** | Sets spacing (in pixels) between entries in the HUD |
| **`popuptest <color>`** |  |
| **`color [hud|guild|dead|target|chatadd|chatrem] <RGB> | [popupdadd|popuprem] [<color name>]`** | Sets the color for the indicated option. RGB colors use web hex colors, and color name are normal names (e.g. blue). |
| **`font <#>`** | Change font size |
| **`show|hide`** | Toggle showing MQ2Targets HUD elements |
| **`hudstring [reload|show|<string>|&clr|&dst|&arr]`** | Modifies the display format for the HUD entries. e.g.<br>`/watch hudstring ${Target.CleanName} ${Target.Level}${Target.Class.ShortName} ${Target.Distance}&amp;arr`<br>Displays: **Bobby 75CLR 30.23**<br><br>Uses [HUD](../macroquest/plugins/core-plugins/hud/README.md) syntax. |
| **`notifyhudstring [reload|show|<string>|&clr|&dst|&arr]`** | Uses [HUD](../macroquest/plugins/core-plugins/hud/README.md) syntax. |
| **`notifychatstring [reload|show|<string>|&clr|&dst|&arr]`** | Uses [HUD](../macroquest/plugins/core-plugins/hud/README.md) syntax. |
| **`sortorder <order>`** | Changes the order of the spawn tracking array. Valid options: `normal reverse` |
| **`hudsorttype <type>`** | Changes the sort type of the hud sort type. Valid options: `priority distance level name none` |
| **`hudsortorder <order>`** | Changes the sort order of the hud. Valid options: `normal reverse` |
| **`sound [ list | stop | id <#> <filename>]`** | Add a sound to the config. Example, <br><br>`/watch sound id 5 shamanspawn.mp3` <br><br>assigns sound#5 to shamanspawn.mp3. Remember that sound files must be in your resources folder. |
| **`timeformat [reload|show|<string>]`** | Changes the format of the timestamp. e.g. *[%H:%M:%S]* |

## Examples

!!! tip "All sound files must be in the resources folder"

`/watch add paladin pc range 65 70`
: Show all Player character paladins between level 65 and 70 in current zone

`/watch add guild`
: Show everyone in your guild in current zone

`/watch add damlin lingering npc`
: Show when damlin in CoA pops (but not his corpse)

`/watch remove damlin lingering npc`
: Remove damlin from HUD tracking

`/watch list`
: Lists the current targets being watched for in current zone

`/watch show 10`
: Change the HUD display to track the 10 nearest targets

`/watch x 200`
: Display the leftmost edge of the HUD list at screen x position 200

`/watch y 50`
: Display the topmost edge of the HUD list at screen y position 50

`/watch increment 20`
: Change the spacing between spawns in the HUD to 20 pixels

`/watch notify hanvar`
: Pop up message if Hanvar spawns/despawns

`/watch remove 2`
: Removes search spawn criteria string #2 according to /watch list

`/watch sound id 5 spawn.mp3`
: Assigns sound#5 to spawn.mp3

`/watch sound 5 keldovan npc`
: Plays sound#5 (spawn.mp3) when keldovan spawns
