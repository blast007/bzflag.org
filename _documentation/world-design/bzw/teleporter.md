---
name: Teleporter
category: Primitive
description: Portals that can be linked together for quick transportation
attributes:
- object_name
- location_position
- location_size
- location_rotation
- obstacle_drivethrough
- obstacle_shootthrough
- obstacle_passable
- obstacle_ricochet
- teleporter_border
- teleporter_horizontal
---

The teleporter object creates a portal gate that can be linked to another gate to provide quick transportation. Each
side of a teleporter may be independently linked. If a link does not exist for the side of a teleporter, it is possible
to shoot or drive through the teleporter.

TODO: CHECK THESE NUMBERS AND CHECK IF WE LEAVE SIZE OUT

## Default sizes

Teleporters have a default size. This is used when the size attribute is left out and for randomly generated worlds.

| Dimension    | Calculation for default size | Default calculated size |
|--------------|------------------------------|-------------------------|
| X            | 0.5 * _teleporterWidth       | 0.56                    |
| Y            | _teleporterBreadth           | 4.48                    |
| Z            | 2.0 * _teleporterHeight      | 20.16                   |
| Border Width | X * 2.0                      | 1.12                    |

## Referencing teleporters

By default, a teleporter doesn't link anywhere else (other than the other side, technically). To link a teleporter to a
destination, a link object must be created.
Teleporters can optionally include a name. If you decide to name your teleporters, you must use that name when creating links. The numeric indexes do not work for
named teleporters.

## Attributes
The teleporter object supports the following attributes:

%attributes%

When using drivethrough, shootthrough, passable, and/or ricochet, keep in mind that this will only apply to the border
of the teleporter. The actual portal will still behave as normal. Also, when drivethrough or passable is used, there is
still collision at the edge of the portal. (TODO: CHECK IF THE TOP HAS COLLISION SO YOU COULD SIT ON TOP, AND CHECK FROM
DIFFERENT ANGLES)

## Syntax Examples

Here is a simple example of two teleporters with a single link, using index referencing (meaning, no named teleporters).

```
teleporter
    position 20 0 0
end

teleporter
    position -20 0 0
end

link
    from 0
    to 2
end
```
