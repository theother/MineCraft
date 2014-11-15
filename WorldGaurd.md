WordGaurd
=========
+ [Home Page](http://wiki.sk89q.com/wiki/WorldGuard/Regions)

---
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
    
####Claiming Regions
+ `/region claim <id>`
Allows a regular user to claim a plot of land and be set as its areas owner.

###### Command List
+ `region list` - will list all the regions
    * Will only list the regions in the particular world you are currently in
    * `region info` - will show you all the infromation about a region
+ `region delete <name>` - will delete a certian region
