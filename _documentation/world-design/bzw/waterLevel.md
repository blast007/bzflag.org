---
name: Water Level
category: Other
description: Defines a water level, below which tanks are destroyed.
attributes:
    - "@object"
    - waterlevel_height
    - "@material"
---

## Description

The water level object defines the height at which a water layer is created. Tanks that touch or go below this water
level will be destroyed.

If your intention is to have water that a tank is able to drive in or under, do not use this object. Instead, create
some drivethough objects and apply a material (and optionally a texture matrix) that makes it look like water.

## Attributes

%attributes%

## Syntax Examples

```
waterLevel
    height 10
end

box
    size 100 100 15
end
```
