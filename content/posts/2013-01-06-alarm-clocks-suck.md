---
author: miker
date: 2013-01-06T18:31:17+00:00
draft: false
title: Alarm Clocks Suck
slug: alarm-clocks-suck
tags:
- alarm clock
---

{{< img src="sony-alarm-clock.jpg" float="right" caption="Crappy Sony Alarm Clock">}}
All current alarm clocks suck. Go look at Amazon and see what I mean. The best appear to be the Sony designs, which look unchanged from mid-90s. Piles of buttons, no auto-setting of time, no modern technology. If you want something built this decade, the best bet is the iHome crap. I'm sure you've seen these: the look like they're designed by a blind man, they only support iPhones and iPods, and still aren't all that high-tech.

Given the sorry state of alarm clocks, I've decided that if I want a good one, I'll have to build my own. Thankfully, the great wide world of open-source hardware makes that possible.

{{< clear >}}

Here's what my clock is going to have at a minimum:
* Dimmable RGB display for menu and time.
* Display dims according to ambient light.
* Menu interface controlled by iDrive-like controller.
* USB-host for iPhone and Android for charging and music playback.
* Multiple alarms: 1 day / 5 + 2 day / 7 day.
* Wakeup light.
* Auto DST based on zone info database.
* WiFi.
* Simple on-board website as alternative config.
* REST interface for integration.
* Time set automatically via NTP, WWVB or GPS.
* Arduino compatible.

Now I just need to learn to solder, and be an EE, and re-learn C, and learn to be a ME.

Should be simple.
