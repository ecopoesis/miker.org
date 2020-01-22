---
author: miker
date: 2013-01-22 01:39:17+00:00
draft: false
title: ST7565 and the Arduino Due
slug: st7565-and-the-arduino-due
tags:
- alarm clock
- arduino due
- st7565
---

I've spent the last several days unsuccessfully trying to get the [ST7565](http://www.adafruit.com/products/250) to work with the [Arduino Due](http://arduino.cc/en/Main/ArduinoBoardDue). I've been trying to port [ladyada's ST7565 library](https://github.com/adafruit/ST7565-LCD) to the SAM core without much luck.

{{< img src="st7565-uno.jpg" cmd="Resize" opt="250x jpg" float="right">}}
Using the ST7565 with Uno and the library works with no issues, as would be expected, so I didn't fuck up soldering or anything easy to diagnose like that.

Getting the code to run on the Due is not as easy. Changes I had to make to get the code to compile where:

* Replace the AVR pgmspace code with a [stubbed out implementation](https://github.com/ecopoesis/delorean/blob/master/delorean/pgmspace.h) that for SAM
* Fix up calls to random()
* Replace calls to the `_BV(x)` macro with `(1 << x)``
* Remove references to `util/delay.h`
* Change calls to `_delay_ms(x)` to `delay(x)`
* Remove the `freemem()` function and calls to it since it requires macros that don't exist on SAM

I've also wired the ST7565 directly to the Due, instead of level shifting it through the 4050 that adafruit supplies with it since the Due is 3.3v already.

{{< clear >}}

{{< img src="st7565-due.jpg" cmd="Resize" opt="250x jpg" float="left">}}
Of course, this doesn't work and I'm note sure why. My guess is the speed of the Due is messing with things, but honestly I'm not sure where to even start with debugging this.

{{< clear >}}
