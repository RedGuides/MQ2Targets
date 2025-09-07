---
tags:
  - plugin
resource_link: "https://www.redguides.com/community/resources/mq2targets.2619/"
support_link: "https://www.redguides.com/community/threads/mq2targets.83780/"
repository: "https://github.com/MMOBugs/MQ2Targets"
config: "MQ2Targets.ini"
authors: "Drunkendwarf, htw, Knightly, PeteSampras"
tagline: "Spawn tracker with optional notify and run-time modifiable HUD display."
acknowledgements: "MQ2-internal functions, MQ2SpawnTracker, MQ2Buffblock, and probably 1 or 2 others."
---

# MQ2Targets

<!--desc-start-->
MQ2Targets is a HUD Display-type spawn tracker with syntax similar to [/where](../macroquest/reference/commands/where.md). Can track specific targets or all targets matching certain criteria (all npc clerics level 53-55 closer than range 100 for example).
<!--desc-end-->
### Features
* Search strings are saved per zone
* Replace "add" with "notify" and it will do a popup for each spawn matching your search string
* Can add as many search strings per zone as needed
* Each HUD spawn matching the search shows by default Name, Level, Class, Distance, an arrow showing relative direction, and a Compass heading
* Use MQ2HUD-type syntax strings to determine HUD display elements to completely customize the HUD display for each spawn
* Default is 5 spawns show, can modify using "/watch count `<num>`"
* HUD will highlight spawn if it's the current target
* Guild members highlighted in HUD
* HUD list sorted by distance ascending

## Commands

<a href="cmd-watch/">
{% 
  include-markdown "projects/mq2targets/cmd-watch.md" 
  start="<!--cmd-syntax-start-->" 
  end="<!--cmd-syntax-end-->" 
%}
</a>
:    {% include-markdown "projects/mq2targets/cmd-watch.md" 
        start="<!--cmd-desc-start-->" 
        end="<!--cmd-desc-end-->" 
        trailing-newlines=false 
     %} {{ readMore('projects/mq2targets/cmd-watch.md') }}

## Settings

!!! tip "All sound files must be placed in the resources folder"

```ini
[Settings]
NumDisplayed=20 
HUDXStart=400 
HUDYStart=500 
HUDYIncrement=14 
HUDColor=FFEA08 
GuildHUDColor=FF00FF 
DeadHUDColor=007777 
TargetHUDColor=FF0000 
HUDString=&clr${Target.CleanName}(${Target.PctHPs}%) ${Target.Level} ${Target.Class.ShortName} ${Target.Distance}&arr(${Target.HeadingTo}) 
NotifyHUDString=${Target.CleanName}(${Target.Level} ${Target.Class.ShortName}) 
UseMQ2Chat=1
MP3Length=3000
WavLength=0
UseTimeStamp=1
TimeStampFormat=[%H:%M:%S]
UseChatReport=1
NotifyChatString=${Target.CleanName} (${Target.Level} ${Target.Class.ShortName}) ${If[${Target.Guild.NotEqual["NULL"]},in ${Target.Guild},]}${If[${Target.Guild.NotEqual["NULL"]},${If[${Target.GuildStatus.NotEqual["member"]}, (${Target.GuildStatus}),]},]}
UseAllZone=1
UseConColor=yes
Verbose=no
HUDSortType=distance
HUDSortOrder=normal
SortType=priority
SortOrder=normal
HUDFontSize=4
UpdateInBackground=off
PopupColorAdd=lightgreen
PopupColorRem=red
ChatColorAdd=009933
ChatColorRem=CC0033

[Sounds]
1=nosound
2=nosound
3=nosound
4=doh.wav
5=whohoo.wav
6=nosound
7=nosound
8=nosound
9=fox.mp3

[Plane of Knowledge]
spawn0=guild
spawn1=paladin pc range 70 80
spawn2=pc range 10|notify|sound|4

[Iceclad Ocean]
spawn0=lodizal npc|notify|sound|5 
spawn1=fabled lodizal npc|notify|sound|5
spawn2=stormfeather npc|notify|sound|5 
spawn3=fabled stormfeather npc|notify|sound|5
spawn4=dire wolf stalker npc|notify|sound|5
```

## See also

- [/where](../macroquest/reference/commands/where.md)
- [HUD](../macroquest/plugins/core-plugins/hud/README.md)
- [Boxhud](../aqo/boxhud/README.md)

## Top-Level Objects

## [Targ](tlo-targ.md)
{% include-markdown "projects/mq2targets/tlo-targ.md" start="<!--tlo-desc-start-->" end="<!--tlo-desc-end-->" trailing-newlines=false %} {{ readMore('projects/mq2targets/tlo-targ.md') }}

## DataTypes

## [Targ](datatype-targ.md)
{% include-markdown "projects/mq2targets/datatype-targ.md" start="<!--dt-desc-start-->" end="<!--dt-desc-end-->" trailing-newlines=false %} {{ readMore('projects/mq2targets/datatype-targ.md') }}

<h2>Members</h2>
{% include-markdown "projects/mq2targets/datatype-targ.md" start="<!--dt-members-start-->" end="<!--dt-members-end-->" %}
{% include-markdown "projects/mq2targets/datatype-targ.md" start="<!--dt-linkrefs-start-->" end="<!--dt-linkrefs-end-->" %}
