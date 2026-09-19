---
name: Cone
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
---

## Description

A cone is an object with a regular polygon for base with all the points of the base extending to a single point.


Default values:

| Attribute      | Value    |
|----------------|----------|
| divisions      | 16       |
| size           | 10 10 10 |
| texsize        | -8 -8    |
| angle          | 360      |
| edge texture   | boxwall  |
| edge bottom    | roof     |
| edge startside | wall     |
| edge endside   | wall     |


## Attributes

%attributes%

## Syntax Examples

Here is a basic cone:
```
cone
    position 50 50 0
    size 10 10 40
end
```
