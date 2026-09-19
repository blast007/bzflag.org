---
name: Pyramid
category: Primitive
description: A square pyramid
attributes:
- "@obstacle"
- "@material"
- pyramid_face
- common_texsize2
- common_texoffset2
- common_phydrv
---


One of the oldest supported objects, pyramids are used in the vast majority of worlds to create obstacles, shot
deflectors, and structures. BZFlag 2.0 added materials, physics drivers, per-face settings, and the ability to control
the texture size and texture offset. When any of those new 2.0 attributes are used, the pyramid becomes what is known as
a "new" pyramid or a "meshified" pyramid (not to be confused with the meshpyr).

When driving through a pyramid with Oscillation Overthruster or a zoned Phantom Zone flag, the visual effects look
different in the old pyramid compared to either the new pyramid or the meshpyr. The old pyramid makes the side of the
pyramid transparent, dims the screen a bit, and shows colored triangles inside the pyramid. Both the new pyramid and the
meshpyr instead make the walls semi-transparent and show a solid bottom. (TODO: CHECK IF THIS IS RIGHT)


| Type                   | Inside with OO or Zoned PZ         |
|------------------------|------------------------------------|
| Old pyramid            | Old style with triangle particles  |
| New pyramid            | Transparent sides with solid floor |
| [Meshpyr](../meshpyr/) | Transparent sides with solid floor |


## Attributes
The pyramid object supports the following attributes:

%attributes%

## Syntax Examples

This creates an old style pyramid with the center of the bottom positioned at x = 10, y = 10, z = 10. Keep in mind that
the Z axis is up, so this pyramid will be positioned on the ground. **Another important note is that the X and Y sizes
are doubled**, so this pyramid will be 20 units wide in the X direction, 40 units wide in the Y direction, but only 10
units high.

```
pyramid
    position 10 10 0
    size 10 20 10
end
```

