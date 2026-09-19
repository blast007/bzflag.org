---
name: Weapon
category: Other
description: This creates a world weapon that fires at the specified interval
attributes:
    - "@object"
    - location_position
    - location_rotation
    - weapon_initdelay
    - weapon_delay
    - weapon_type
    - weapon_color
    - weapon_tilt
    - weapon_trigger
    - weapon_eventteam
---

## Description

World weapons are weapons that are not fired by players. Instead, the game server itself fires them.

## Attributes

%attributes%

## Syntax Examples

```
weapon
    position 0 -15 10
    tilt -45
    initdelay 30
    delay 1 20
end

weapon
    position 0 0 10
    tilt -45
    initdelay 31
    delay 1 20
    type R
end

weapon
    position 0 15 10
    tilt -45
    initdelay 32
    delay 1 20
    type L
end
```
