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
+ http://www.minecraftworldmap.com/
+ LtJim007
+ 


Import Schematic's
------------------

1. Place said schematic file in the root file of worldEdit
2. SSH to file file location and `sudo cp [filename] [/schematics]`
3. This will then allow you to use worldEdit to import the file into said worlds

WorldEdit
---------
__Selction Tool__

1. Use wand via the `//wand` command
2. Select point one with your crosshair using the `//pos1` command
3. Select point to using `//pos2`

__Copying to Schematics__

1. Make your selection (reffer to selection tool) and copy it with `\\copy`
2. Save it with `\\schem save mcedit filename`

Plugin Segestions
https://clients.mcprohosting.com/knowledgebase/22/Recommended-Minecraft-Plugins.html


MineCraft
=========

Amazon EC2
=========
+ Running on a EC2 instance
+ The elactic ip in the adress you use to access the server


Useful Tools
===========
+ Putty - Will allow you to shh into the server
+ [YAML Phaser](http://yaml-online-parser.appspot.com/)
    * In case you ever runing into a pharser error, run your code through the above phaser which will find and spacing errors for you to fix.


Plugins - On the server
======================
### Admin
+ EssentialsGroupManager
+ [Admin Pannel](http://dev.bukkit.org/bukkit-plugins/administration-panel/)
    * Allows for admin commands without comand line prompts
    * Command `/ap` will bring up menu
    * Comman `/ap <player>` will allow you to open the adminpanel to interact with that given player


### World Editors
+ [Flat World Generator](https://github.com/nvx/CleanroomGenerator/wiki)
    * Just creates a completely flat world to play around with, I am currently using this as my spwan point seed.
+ [World Editior](http://www.enginehub.org/worldedit)
    * Allows you to edit your world more freely


### Vault
+ Common Dependency – it is a permissions, chat and economy API to give plugins easy hooks into these systems without needing to hook or depend on each individual plugin themselves. *Most plugins will need this.


### ClearLagg
+  Optimization - It's made to remove all entities to prevent/clear lag. This plugin can help with server performance.

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
To remove a world use:
+ /mvremove `world_name`

__List World__
To get a list of your current world use:
+ `mv list`

__Teleportaion__
+ `/mv tp [PLAYER] {WORLD}`
    * `/mv tp world` -- Admin teleport
    * `/mv tp Rigby90 world_nether` another plater teleport


Import Schematic's
------------------

1. Place said schematic file in the root file of worldEdit
2. SSH to file file location and `sudo cp [filename] [/schematics]`
3. This will then allow you to use worldEdit to import the file into said worlds

WorldEdit
---------
__Selction Tool__

1. Use wand via the `//wand` command
2. Select point one with your crosshair using the `//pos1` command
3. Select point to using `//pos2`

__Copying to Schematics__

1. Make your selection (reffer to selection tool) and copy it with `\\copy`
2. Save it with `\\schem save mcedit filename`





Group Manager
------------
### Things you need to do
##### If you add a new world
1. You need to go into the config file and add the new settings to mirror the other world setting to keep your permisions in-line
```YAML
  mirrors:
        world:
          world_nether:
          - users
          - groups
          world_the_end:
          - users
          - groups
          all_unnamed_worlds:
          - users
          - groups

          #This would be the new world added    
          NEWWORLD
          - users
```

##### Groups
+ Groups are defined in the `GroupManager\worlds\world` folder under `groups.yml`
+ This is where you will find groups such as `defult` which is the group any new player will be added to.
```YAML
Default:
    default: true
    permissions:
    - -bukkit.command.kill
    inheritance:
    - g:groupmanager_default
    - g:bukkit_default
    - g:essentials_default
    - g:towny_default
    #Added builder as defult since the player which will be able to log into
    #the server will be trusted
    - g:essentials_builder
    info:
      #Controls the name color + prefix
      prefix: '&e'
      #alternitively I you can turn build to true
      build: false
      suffix: ''
```
+ `Inheritance` permissions are located in the root `gloablgroups.yml` file

__To create a new Group__
```YAML
  Pro:
    default: false
    permissions:
    - -bukkit.command.kill
    inheritance:
    - g:groupmanager_default
    - g:bukkit_default
    - g:essentials_default
    - g:towny_default
    - g:essentials_builder
    info:
      prefix: '&3[Pro]'
      build: true
      suffix: ''
```

##### Users
+ Any time a user logges into the server there name will be added to the `GroupManager\worlds\world\users.yml`
+ In there you can change there status and a permissions
```YAML
users:
  ElgarL:
    #Can edit the group with player are apartof
    group: Moderator
    subgroups: []
    permissions:
    - groupmanager.noofflineperms
  KHobbits:
    group: Moderator
    subgroups: []
    permissions:
    - groupmanager.noofflineperms
  
  #Lets say you want a player just to be able to use the time command
  #And the time set command add it to the permissions to the users group
  snowleo:
    group: Builder
    subgroups: []
    permissions: [essentials.time, essentials.time.set]
    - groupmanager.noofflineperms
```

##### Commands
+ To move players from Minecraft: `/manuadd <plater> [group]` 
+ To revert to defualt `/manudel <player>`




Permissions
-----------





Multiverse-Portals
-----------------
+ Using the `wand` command `mvp wand` select the cornor of one portal and then select the cornor of the other portal.
+ `mvp create`





World Gaurd
-----------
#### Block Structures
+ Using the `wand` select the bottom most corrnor and the top most corrnor
+ Defind the region `/region define <name>`
    * To manually expand the region you can use `//expand 2 up` which will expand the protected region up two blocks
    * `//expand vert` will expand all the way to the sky
+ You can test to see if you have a defined region if you use a `leather` and left click the region it will tell you if you can build or not

#### Flags
Flags will allow you to set certian paramaters as in no-pvp, monster spawns, ect.
+ Define a region
    * `region flag <name> flag` will list all the posible flag you can use

#### Adding Members of Groups to regions
+ `/region addmember <region name> <player name>` - to add a player
    * `/region addmember <region name> <player name>` - to remove a player

#### Global Regions
Global Regions protect entire world regions no matter how big or small
+ `/region info __GLOABL__` - will list global region info
+ `/region flag __GLOBAL__ <name of flag> <deny or allow>` - will set global flag

#### Parenting Regions
Basically regions within othe regions, so lets say you have a pvp battle zone based on region priority level
+ Create two regions - one region within another region
+ `/region setpriority <name of region> <prority level>`
    * Higher number overide
+ `/region setparent <child region> <parent region>` - will ensure all the flags are correct

#### Region Modes
You basically have two options, block or poly. With a block region you are limited to square regions while with poly you have more options but it does take up more resorces.
+ To change modes you use the command `//sel poly`
    * Left click to add a start point followed by right clicks where ever you think there shold be another point. Basically just follow the outline.
    * `//sel` will reset the defined area 

#### Spwan region
__Flag List__
+ Deny
    * build
    * mob-spawning
    * enderman-grief
    * enderperal
    * snow-fall
    * ice-form
    * ice-melt
    * leaf decay
    * potion-splash
    * pvp
    * tnt
    


###### Command List
+ `region list` - will list all the regions
    * Will only list the regions in the particular world you are currently in
    * `region info` - will show you all the infromation about a region
+ `region delete <name>` - will delete a certian region





+ http://www.minecraftworldmap.com/
+ LtJim007
