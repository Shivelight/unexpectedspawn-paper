<p align="center">
<img src="https://raw.githubusercontent.com/Shivelight/unexpectedspawn-paper/master/assets/artwork.png">
<br>
<img src="https://img.shields.io/badge/Crafted%20in-Java-red?style=flat&logo=java">
<img src="https://img.shields.io/github/v/release/Shivelight/unexpectedspawn-paper?color=green">
</p>

**This is a [Paper](https://github.com/PaperMC/Paper) plugin!**

Simple plugin to randomize any player spawn point. Suitable for Hardcore / Anarchy server, or you just want people to be scattered in you server world.

Things that were added : 
- Global values for world that don't have custom config
- Toggle switch for random respawn on death
- Fixed the config keys, so it doesn't make plugin users confused
- Added per world config settings
- Added per world respawn world

## Minor Bug
You will respawn in the spawn point of Nether world if you are using the old version of Multiverse 4.2.2 and below and running a 1.16+ server.
To fix that just use the latest build or v 4.3.0 or higher where multiverse fixed that issue.

If you still have issues, please send it in Issues tab rather than sending it in spigot plugin page review.

Code Updated by : https://github.com/DeathGOD7


## Commands and Permissions

| Command                 | Alias         | Description          | Permission          |
| ----------------------- | ------------- | -------------------- | ------------------- |
| /unexpectedspawn        |  /uns         | Shows version         | -                   |
| /unexpectedspawn reload |  /uns reload  | Reload configuration | unexpectedspawn.use |

## Configuration

```yaml
# UnexpectedSpawn
# Authors : Shivelight, DeathGOD7
# Original : https://github.com/Shivelight/unexpectedspawn-paper
# Modified : https://github.com/DeathGOD7/unexpectedspawn-paper

global:
  # Random respawn area for global settings.
  x-max: 399
  x-min: -399
  z-max: 399
  z-min: -399

  #Sets the global respawn world unless set in custom config worlds.
  respawn-world: ''

  # Do you want to have random respawn than normal world respawn? By default it is enabled in all worlds. If you want to
  # disable it in specific world, then add that world name in below 'blacklisted-worlds'.
  random-respawn:
    # Do you want to have random respawn after user dies? If set to false then user will respawn in world spawnpoint.
    # or bed/respawn anchor spawnpoint.
    on-death: true
    # Checks if bed respawn is taken priority. If set to false then it will force user to random respawn
    # even if they have bed respawn point when they die.
    bed-respawn-enabled: true
    # Do you want to have random spawn when user joins for first time to prevent grief in spawn chunks? If set to false
    # then user will spawn in default world spawnpoint.
    on-first-join: false
    # Enable this if you want to have random respawn each time user joins the server. It's best for Anarchy type server.
    always-on-join: false

  # Specify any block where you don't want user to be teleported. You don't them to drown in lava/water or land on
  # someone else campfire, no?
  spawn-block-blacklist:
    - LAVA
    - WATER
    - CACTUS
    - FIRE
    - MAGMA_BLOCK
    - SWEET_BERRY_BUSH
    - CAMPFIRE


# If no worlds are specified, it will use global/default variables. Default Config (worlds: [])
# If you have added any world below, it will override the global settings.
# If it got missing parameters that is in global settings like "spawn-block-blacklist"
# but not in worlds world parameters then it will use global parameters.
# All the features are same as global ones.
# Please change "survival" to the name of your world and remove [] if you want to add worlds.

worlds: []
#  survival:
#    x-max: 500
#    x-min: -500
#    z-max: 500
#    z-min: -500
#    respawn-world: ''
#    random-respawn:
#      on-death: true
#      bed-respawn-enabled: true
#      on-first-join: false
#      always-on-join: false

# If you have any worlds here , then it will be excluded from having random spawn
# Even if you have set custom settings in above settings and you add that world to
# blacklist, it will be excluded. Default :[]
blacklisted-worlds: []
#  - bedwars
#  - creative
```

## Contributors
- Shivelight
- DeathGOD7
- Roshanxy