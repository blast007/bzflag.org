---
name: Define
category: Other
description: Create a template that can be placed with th Group object
---

## Description

A definition block, created by using the define object, allows creating a template that can be placed by the
[Group](../group/) object. This is often used for symmetrical worlds, such as two or four team Capture The Flag worlds.

A definition is created by starting a line with `define` followed by a space and the name of the definition. Unlike some
other objects, the name attribute is not used to name a definition block. A definition block is ended by using `enddef`
on a separate line. Between the define and enddef lines, any supported objects can be added. These objects will then be
placed when the group definition is referenced by a Group object.

A group definition block can include any object **except** for:
* define
* dynamicColor
* link
* material
* transform
* physics
* textureMatrix
* waterLevel
* weapon
* world
* zone

## Syntax Examples

Here is a basic example of a definition block:
```
define Base
    box
        position 0 0 0
        size 20 20 10
    end

    base
        position 0 0 10
        size 10 10 0
    end
enddef
```

See the [Group](../group/) object for more examples of using the Define object.
