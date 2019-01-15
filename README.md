SoftFloat-3e for OpenJDK
========================

This is a [SoftFloat-3e](http://www.jhauser.us/arithmetic/SoftFloat.html)
library with additional build files targetting Linux armel.
The intent behind this repository is to make building SoftFloat for
OpenJDK on `arm-sflt` ABI easier.

Why
---
Software floating point math implementation on Linux on ARM
slightly prefers performance over precision of calculations.
This presented an issue for Java JCK - these imprecisions were
detected. The solution chosen by Java developers was to use
SoftFloat-2b library for the problematic operations.

This repository provides an updated SoftFloat-3e library for new
versions of OpenJDK, where SoftFloat support is added once again.
(see [JDK-8215902](https://bugs.openjdk.java.net/browse/JDK-8215902)).

How to use
----------
1. Install a suitable Linux ARM compiler and ensure that `arm-linux-gnueabi-gcc` executable exists.
2. Go to `build/Linux-ARM-VFPv2-GCC-OpenJDK`.
3. Run `make`
4. Run `make DESTDIR=... install`
5. Configure OpenJDK with `--with-sflt=...` pointing to DESTDIR.
