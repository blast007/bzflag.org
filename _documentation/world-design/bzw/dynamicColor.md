---
name: Dynamic Color
category: Other
description: Animate the color channels of an object
attributes:
    - "@object"
---

## Description

The Dynamic Color object allows for animating the diffuse color channels of an object. It is added to a
[Material](../material/) object using the `dyncol` attribute, and then that material is added to an obstacle object with
the `matref` attribute. There are four color channels that can be manipulated: red, green, blue, and alpha. The alpha
channel controls the opacity. Other than for the `name` attribute, all attributes inside a dynamic color object must
have the color channel specified first.

Because of the way dynamic colors are implemented, it overrides the use of the `diffuse` or `color` material attribute.
Also, if you don't control a channel in the dynamic color definition, it will be set to 1.0. For example, if you create
a dynamic color that only controls the alpha channel, the red, green, and blue channels will all have a value of 1.0 and
the object will be white with varying amounts of opacity. If you wish to keep a color channel at a specific value, the
limits attribute can be used with the same value for the minimum and maximum.

There are 5 types of commands per channel: limits, sinusoid, clampup, clampdown, and sequence. Except for limits and
sequence, the commands are repeatable. If a sequence is used, the clampup and clampdown attributes have no effect. The
use of sequence, clampup/clampdown, and/or sinusoid will calculate a factor from 0 to 1, which is then used to scale the
color channel value from the minimum to the maximum value.

Each step in a sequence has one of three states: 0, 1, or 2.  The 0 state indicates a clamp down to the minimum value.
The 2 state indicates a clamp up to the maximum value. The 1 state does not clamp the value at all. When the 1 state is
used without any sinusoids on that color channel, it is equivalent to the 2 state. However, if there are any sinusoids
on that channel, they will then be used to calculate the factor when the sequence is currently in the 1 state.

With the clampup and clampdown attributes,

If there are no active clamps, but there are sinusoids, then those will run and compute the color channel factor. This
means that it is possible to combine sinusoids with either a sequence or with one or more clampup or clampdown, as long
as there is a time when the sequence uses a 1 (no clamps) state or when the clampup and clampdown attributes are both
in an inactive state at the same time.



## Attributes

%attributes%

## Syntax Examples

Here is an example using limits, clampup, and clampdown to create flashing emergency lights.

```
world
	size 800
end

dynamicColor
	name redflashinglight
	red limits 1 1
	blue limits 0 0
	green limits 0 0
	alpha limits 0.2 1.0
	alpha clampup 1 0 0.125
	alpha clampdown 1 0.125 0.125
	alpha clampup 1 0.25 0.125
	alpha clampdown 1 0.375 0.625
end

dynamicColor
	name blueflashinglight
	red limits 0 0
	blue limits 1 1
	green limits 0 0
	alpha limits 0.2 1.0
	alpha clampdown 1 0.000 0.500
	alpha clampup   1 0.500 0.125
	alpha clampdown 1 0.625 0.125
	alpha clampup   1 0.750 0.125
	alpha clampdown 1 0.875 0.125
end

material
	name redflashinglight
	dyncol redflashinglight
end

material
	name blueflashinglight
	dyncol blueflashinglight
end

material
	name car
	color grey
end

material
	name tire
	color black
end

box
	name body
	position 0 0 1
	size 4 2 1
	matref car
end

box
	name top
	position -0.75 0 2
	size 2 1.75 1
	matref car
end

box
	name bumperfront
	position 3.5 0 0.5
	size 0.5 2 0.5
	matref car
end

box
	name bumperback
	position -3.75 0 0.5
	size 0.25 2 0.5
	matref car
end

box
	name wheelfrontleft
	position 2.4 1.8 0
	size 0.4 0.2 0.8
	matref tire
end

box
	name wheelbackleft
	position -2.8 1.8 0
	size 0.4 0.2 0.8
	matref tire
end

box
	name wheelfrontright
	position 2.4 -1.8 0
	size 0.4 0.2 0.8
	matref tire
end

box
	name wheelbackright
	position -2.8 -1.8 0
	size 0.4 0.2 0.8
	matref tire
end

box
	name undercenter
	position 0 0 0.5
	size 3.5 1.5 0.55
	matref car
end

box
	name underleft
	position -0.2 1.75 0.5
	size 2 0.25 0.5
	matref car
end

box
	name underright
	position -0.2 -1.75 0.5
	size 2 0.25 0.5
	matref car
end

box
	name lightcenter
	position 0 0 3
	size 0.25 0.5 0.25
	matref car
end

box
	name lightred
	position 0 -1 3
	size 0.25 0.5 0.25
	matref redflashinglight
end

box
	name lightblue
	position 0 1 3
	size 0.25 0.5 0.25
	matref blueflashinglight
end
```
