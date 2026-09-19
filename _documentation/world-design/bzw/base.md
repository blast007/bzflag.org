---
name: Base
category: Primitive
description: A rectangular team based, used in Capture the Flag
attributes:
- location_position
- location_size
- location_rotation
- obstacle_drivethrough
- obstacle_shootthrough
- obstacle_passable
- obstacle_ricochet
- base_color
- base_oncap
---

The base object is used in Capture the Flag (CTF) games modes. The base is associated with one team, either red, green,
blue, or purple. Team flags of the same color will spawn in the center of a matching team base by default.

If multiple bases for a given team are added, only one of the bases will spawn a team flag by default. If you want a
team flag on each base, you will need to add more flags. One thing to note is that when you add team flags, it does not
automatically add the first flag. So, if you want two team flags instead of one team flag, you actually need to add two
flags to the configuration. So, for example, if you have two team bases for each of the four teams, and wanted a team
flag at each base, you would add this to your world:

```
option
    +f R*{2} +f G*{2} +f B*{2} +f P*{2}
end
```

Team flags for a given team do not show up unless there are at least one player from that team joined to the server. If
all the players for a given team leave, all team flags for that team will disappear, unless they are being held by a
player. In that case, the flag will stay until it is captured or dropped.

When a server is not run in CTF mode, team bases are turned into normal boxes of the same size.

## Attributes
The pyramid object supports the following attributes:

%attributes%

## Syntax Examples

This creates a team base with the center of the bottom positioned at x = 10, y = 10, z = 10. Keep in mind that the
Z axis is up, so this base will be positioned on the ground. **Another important note is that the X and Y sizes are
doubled**, so this base will be 20 units wide in the X direction, 40 units wide in the Y direction, but only 10 units
high.

```
base
    position 10 10 0
    size 10 20 10
    color 1
end
```
