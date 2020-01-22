---
author: miker
date: 2013-01-12 23:02:43+00:00
draft: false
title: Learning to Solder
slug: learning-to-solder
tags:
- alarm clock
- solder
- st7565
---

One of this things I knew I need to learn to build the world's best alarm clock was how to solder. And I was right: one of the first things I needed to do was solder wires to the [ST7565](http://www.adafruit.com/products/250) display I got from adafruit so I could hook it up to the Arduino at the heart of the clock.

Problem 1: I don't have a soldering iron. Some quick Googling show that there are a lot of cheap soldering irons out there, and that you can probably get away with using them if you're not doing a ton of work. But everyone seems to agree that the [Hakko FX-888](http://www.amazon.com/gp/product/B004M3U0VU/ref=as_li_qf_sp_asin_tl?ie=UTF8&tag=mikerorg-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=B004M3U0VU) is the best there is.

I generally like to buy the best tools I can get. Cheap tools are just frustrating, I've found it better to spend a little more up front to have the pleasure of using a well designed, well made product. Hell, that's why I'm building a my own alarm clock. So rather then cheap out, I got the FX-888. I also read through [adafruit's excellent guide to soldering](http://learn.adafruit.com/adafruit-guide-excellent-soldering) which was as excellent as described. It convinced me to get their [Helping Third Hand Magnifier](http://www.adafruit.com/products/291) which was extremely helpful in seeing little things. I also picked up a [clip on LED light](http://www.amazon.com/gp/product/1933622717/ref=as_li_qf_sp_asin_il_tl?ie=UTF8&tag=mikerorg-20&linkCode=as2&camp=1789&creative=9325&creativeASIN=1933622717) from Amazon since my workspace is a little dim.

{{< img src="helping-hand.jpg" float="right">}}
That done, it was down to soldering. Here's what my soldering station looks like all set up, with me about halfway through attaching all the wires to the ST7565. The FX-888 worked like a champ: it heats up quickly, the iron is light weight and its handle doesn't get hot and even a newbie like me can us it.

{{< clear >}}

{{< img src="soldering.jpg" float="left">}}
Here's the final product. I'm not completely happy with it: There's defiantly too much solder on some of the connections, but according to my multimeter the pins on the wires are connected to the solder pads on the back of the LCD's PCB, so it's obviously good enough.

Now to plug this in to an Arduino and make it work.

{{< clear >}}
