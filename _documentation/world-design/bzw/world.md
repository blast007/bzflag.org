---
name: World
category: Other
description: Controls some attributes of the world, most of which can also be set via BZDB variables.
attributes:
    - "@object"
    - world_size
    - world_flagHeight
    - world_noWalls
    - world_freeCtfSpawns
---

## Description

The world block allows for setting some options for the world, such as the world size and changing Capture The Flag
spawns to spawn randomly instead of on team bases.

## Attributes

%attributes%

## Syntax Examples

```
world
    # Set the _worldSize to 400
    size 200
    # Turn off the outer wall generation because we have our own structure along the border
    noWalls
    # Spawn CTF players randomly every time instead of on their bases
    freeCtfSpawns
end
```
