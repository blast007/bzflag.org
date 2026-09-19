---
name: Zone
category: Other
description: Creates a rectangular zone that can be used for player spawns or flag spawns, and can be used with plugins.
attributes:
    - "@object"
    - location_position
    - location_size
    - location_rotation
    - zone_flag
    - zone_zoneflag
    - zone_team
    - zone_safety
---

## Description

Zones are rectangular areas that can be used to control flag spawns, player spawns, and team flag safety zones.

Both the flag and zoneflag attributes cause flags of specific types to spawn within them. The difference is that the
flag attribute only applies to flags added using the server options -f or -s/+s. The zoneflag attribute will add the
specified quantity of flags to the world and spawn them within that specific zone.

The team attribute will control where tanks of a given team are allowed to spawn. This can be very useful for worlds
with team base structures to force players to spawn inside their respective base.

When a team flag is dropped in an unsafe location, such as over a pyramid or other angled surface, it will fly to the
nearest safety zone. By default, without any safety zones explicitly defined in the world, a safety zone at 0, 0, 0 is
created for each team. If all safety zones are covered by solid obstacles, the team flag will instead fly back to the
team base.

## Attributes

%attributes%

## Syntax Examples

```
# Add some Guided Missile and ShockWave flags, and 10 other random good flags (except for Stealth)
options
    +f GM{5}
    +f SW{5}
    -s 10
    +s 10
    -f ST
    -f bad
end

# Tell good flags to spawn here
zone
    position 50 0 0
    size 10 10 0
    flag good
end

# Add and spawn some Stealth flags here
zone
    position -100 0 0
    size 0 0 0
    zoneflag ST 10
end
```
