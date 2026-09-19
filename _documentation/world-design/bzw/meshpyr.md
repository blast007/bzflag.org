---
name: Mesh Pyramid
category: Primitive
description: Something
attributes:
    - "@obstacle"
    - cone_divisions
    - cone_angle
    - common_texsize2
    - common_phydrv
    - common_smoothbounce
    - common_flatshading
    - "@material"
    - cone_side
    - pyramid_flipz
---

## Description

The mesh pyramid, by default, creates an object with a square base and 4 triangled sides forming a peak.

The mesh pyramid object is technically a cone with, so most of the cone options also work here. The default
number of divisions is set to 4, causing the pyramid to have a square base. This can be adjusted with the divisions
option. The default X and Y size is controlled by the _pyrBase BZDB variable and the default height is controlled by the
_pyrHeight variable. The default texture applied to all faces (edge, bottom, startface, and endface) is the bundled
pyrwall texture.

The one option available with mesh pyramids but not with cones is the flipz option, which flips the mesh pyramid upside
down. Tanks can drive on the flat square base when the pyramid is inverted.

## Attributes

%attributes%

## Syntax Examples

Something
