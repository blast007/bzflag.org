---
name: Box
category: Primitive
description: A rectangular box
attributes:
    - "@obstacle"
    - common_texsize2
    - common_texoffset2
    - common_phydrv
    - "@material"
    - box_side
---

## Description

One of the oldest supported objects, boxes are used in the vast majority of worlds to create obstacles, platforms, and
structures. BZFlag 2.0 added materials, physics drivers, per-face settings, and the ability to control the texture size
and texture offset. When any of those new 2.0 attributes are used, the box becomes what is known as a "new" box or a
"meshified" box (not to be confused with the meshbox).

Old style boxes allow a tank to drive over (a.k.a. "bump up") small height differences, dictated by the `_maxBumpHeight`
server variable, which defaults to 0.33. Both new boxes and meshboxes do not yet support this feature.

When driving through a box with Oscillation Overthruster or a zoned Phantom Zone flag, the visual effects look different
in the old box compared to either the new box or the meshbox. The old box makes the side of the box transparent, dims
the screen a bit, and shows colored triangles inside the box. Both the new box and the meshbox instead make the walls
semi-transparent and show a solid bottom.


| Type                   | Inside with OO or Zoned PZ         | Bump Up support |
|------------------------|------------------------------------|-----------------|
| Old box                | Old style with triangle particles  | Yes             |
| New box                | Transparent sides with solid floor | No              |
| [Meshbox](../meshbox/) | Transparent sides with solid floor | No              |


## Attributes
The box object supports the following attributes:

%attributes%

## Syntax Examples

This creates an old style box with the center of the bottom positioned at x = 10, y = 10, z = 10. Keep in mind that the
Z axis is up, so this box will be positioned on the ground. **Another important note is that the X and Y sizes are
doubled**, so this box will be 20 units wide in the X direction, 40 units wide in the Y direction, but only 10 units
high.

```
box
    position 10 10 0
    size 10 20 10
end
```
