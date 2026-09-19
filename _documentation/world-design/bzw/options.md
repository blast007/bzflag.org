---
name: Options
category: Other
description: Set command line options for the BZFlag server
---

## Description

The options block can be used to specify most BZFlag server command line options.  This is useful for defining a set of
normal options that a world may require, such as allowing jumping or ricochet, adding flags, setting shot limits, or
loading necessary server plugins.

## Disallowed command line options

The following options are *not* allowed in the options block of a world file.

* -badwords
* -ban
* -banfile
* -cache
* -cacheout
* -conf
* -d
* -filterCallsigns
* -filterChat
* -filterSimple
* -groupdb
* -helpmsg
* -i
* -noMasterBanList
* -masterBanURL
* -p
* -passwd
* -pidfile
* -publicaddr
* -publiclist
* -publickey
* -q
* -recbuf
* -recbufonly
* -recdir
* -replay
* -reportfile
* -reportpipe
* -ts
* -UPnP
* -utc
* -userdb
* -w
* -world

## Syntax Examples

Here is an example that enables jumping (-j), ricochet (+r), adds some flags (+f), sets the maximum simultaneous shots
to 5 (-ms), sets the tank speed to 200, and defines maximum acceleration settings (-a).

```
options
    -j
    +r
    +f WG{9}
    +f GM{4}
    +f good
    -ms 5
    -set _tankSpeed 200
    -a 50 38
end
```
