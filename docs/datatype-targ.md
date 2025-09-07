---
tags:
  - datatype
---
# `Targ`

<!--dt-desc-start-->
Returns information on the spawns detected in MQ2Targets.
<!--dt-desc-end-->

## Members
<!--dt-members-start-->
### {{ renderMember(type='spawn', name='Spawn', params='name/#') }}

:   Access spawn information for the specified [spawn search](../macroquest/reference/general/spawn-search.md) or index.

### {{ renderMember(type='int', name='Count') }}

:   Return number of entries on the watch list starting at 1.

### {{ renderMember(type='int', name='Priority', params='name/#') }}

:   The priority of the spawn (via index or [spawn search](../macroquest/reference/general/spawn-search.md)). If nothing assigned, default is -1.

<!--dt-members-end-->

## Examples
<!--dt-examples-start-->
`/echo ${Targ.Spawn[1].Name}`

Returns name of the spawn in index 1.
<!--dt-examples-end-->

<!--dt-linkrefs-start-->
[int]: ../macroquest/reference/data-types/datatype-int.md
[spawn]: ../macroquest/reference/data-types/datatype-spawn.md
<!--dt-linkrefs-end-->
