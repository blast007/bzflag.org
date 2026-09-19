---
name: Physics
category: Other
description: Applies physics to a tank
attributes:
    - "@object"
    - physics_linear
    - physics_angular
    - physics_radial
    - physics_slide
    - physics_death
---

## Description

Physics drivers can be assigned to most world obstacles (like boxes, pyramids, and mesh objects) and will then apply
different physics to a player's tank, such as moving them like they are on a conveyor belt or launching them into the
air, spinning the player, adding sliding (acting like ice for instance), or killing the player on contact.

## Attributes

%attributes%

## Syntax Examples

Here is one that creates a basic conveyor belt.

```
physics
    name conveyor
    linear 30 0 0
end
```

Here is another that creates a bounce pad.

```
physics
    name bounce
    linear 30 0 30
end
```

This will make a surface act like it's icy.

```
physics
    name ice
    slide 1.0
end
```

This one kills the player when they touch it.

```
physics
    name mine
    death Oops! You hit a mine!
end
```
