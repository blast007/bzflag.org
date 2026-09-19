---
name: Sphere
category: Primitive
description: A sphere or hemisphere
attributes:
    - "@obstacle"
    - sphere_divisions
    - sphere_radius
    - sphere_hemisphere
    - common_texsize2
    - common_phydrv
    - common_smoothbounce
    - common_flatshading
    - "@material"
    - sphere_side
---

## Description

This creates a sphere. By default, the number of divisions is 4, the position is 0, 0, 10, the radius is 10, the edge
texture is boxwall, the bottom texture (used for hemispheres) is roof, and tahe texsize is -4.0.

## Attributes

%attributes%

## Syntax Examples

This creates a more detailed sphere elevated from the ground.

```
sphere
    divisions 10
    radius 30
    position 0 0 80
end
```
