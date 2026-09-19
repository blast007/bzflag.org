---
name: Group
category: Other
description: Something
attributes:
    - "@object"
    - group_team
    - group_tint
    - group_phydrv
    - group_matref
    - group_matswap
# TODO: Cover group objects being nested inside another definition
---

## Description

After creating a definition block using the [Define](../define/) object, the group object is used to place the template
of objects somewhere in the world. It also makes it possible to swap teams and materials, add a tint, and apply a
physics driver.

## Attributes

%attributes%

## Syntax Examples

This is an example of a 4 team Capture The Flag (CTF) world that defines a team fort once and then places it four times
using group.
```
options
    -c
end

world
	size 200
end

define fort
	box
		position 125 75 0
		size 55 5 25
	end

	box
		position 75 130 0
		size 5 50 25
	end

	box
		position 85 85 11.5
		size 5 5 1
	end

	base
		position 110 110 0
		size 16 16 0.01
		color 1
	end

	pyramid
		position 75 75 25
		size 5 5 35
		passable
	end

	pyramid
		position 75 175 25
		size 5 5 25
		passable
	end

	pyramid
		position 175 75 25
		size 5 5 25
		passable
	end
enddef

group fort
end

group fort
	team 2
	spin 90 0 0 1
end

group fort
	team 3
	spin 180 0 0 1
end

group fort
	team 4
	spin 270 0 0 1
end
```
