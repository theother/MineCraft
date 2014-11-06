MineCraft
=========

Mukwonago Minecraft - setup


Plugins Installed
=================
+ EssentialsGroupManager



How to become OP
================
`ops.json` is the file that need to be changed to become an OP, and need to formated in the following way.
```json
[
  {
    "uuid": "6266de27-82bc-4da7-b6bc-b814c9c14116",
    "name": "MukwonagoLibrary",
    "level": 4
  }
]
```
+ To generate the `uuid` go to: http://minecraft-techworld.com/uuid-lookup-tool
  * MukwonagoLibrary
  * `uuid` = 6266de27-82bc-4da7-b6bc-b814c9c14116
+ You can have various OP's with diffrent level of controll which is determined by the level. (1-4)




Sources
=======
__Essensial__
+ [Command Reference](http://wiki.ess3.net/wiki/Command_Reference)
+ [List of all items](http://minecraft-ids.grahamedgecombe.com/)   


Multi-Vers
----------
__Create__
+ /mvcreate `name_of_world` `type_of_world`
  * /mvcreate `name_of_world` `type_of_world` -g TerrainControl  (to use terrain control)

__Remove__
+ /mvremove `world_name`

__List World__
+ /mw create <world name> [generator] [seed]
  *  
+ /mw load
http://www.minecraftworldmap.com/
