---
author: miker
date: 2013-01-16 03:48:24+00:00
draft: false
title: Struggles With the Arduino Due
slug: struggles-with-the-arduino-due
tags:
- alarm clock
- arduino due
- arduino uno
- embedxcode
- intellij
- xcode
---

One of the things I knew going into this project was that I wanted the alarm clock to be compatible with Arduino. Ideally I'm going to expose as many of the Arduino's pins on the final product in an accessible way so people can slap on shields and extend the clock to make it better.

This then begs the question: which Arduino? I have both a [Uno](http://arduino.cc/en/Main/ArduinoBoardUno) and a [Due](http://arduino.cc/en/Main/ArduinoBoardDue). While I like the simplicity, support and cost of the Uno, the Due seems more future proof. My [ST7575](http://www.adafruit.com/products/250) already takes up over half the available pins on an Uno, and I haven't even added any clocks, GPS, wakeup lights or the million or so other things this clock is going to do to it. Plus I'm sure the extra speed on the Due will come in handy. So Due it is.

Next step was to setup the skeleton of my project to give me a place to start putting code. I started this, as one naturally would, in the Arduino IDE. What a mistake. The Arduino IDE has to be the worst programming environment I've ever used. I'm a little spoiled in this respect as I use the wonderful [IntelliJ IDE](http://www.jetbrains.com/idea/) fro JetBrains as my main IDE, but trust me, the Arduino IDE is especially terrible. Shift-Tab barely works half the time, there is no static analysis on any type, it doesn't seem to support unit tests. It's a shit show.

Luckily, a guy called Rei Vilo has built out some templates for Xcode called [embedXcode](http://embedxcode.weebly.com) that supports a bunch of embedded systems, including the various Arduinos. And though Xcode isn't as good as IntelliJ, it's a hell of a lot better then the abomination that is the Arduino IDE.

Unfortunately, because the Due is so new, embedXcode's support for it wasn't quite working. Compiling for the SAM core didn't work: Rei Vilo was able to get that to work. Of course, then uploading didn't work. It turns out that the Due uses a different uploader then previous AVR based boards. After digging into what the shitty Arduino IDE was doing, I figured out the correct option and was able to the Makefiles of embedXcode to do the right thing.

And now, thankfully, I don't have to use the Arduino IDE for anything. If you'd like to take a look at my code, it's available on [Github](https://github.com/ecopoesis/delorean).
