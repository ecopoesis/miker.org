---
author: miker
date: 2013-08-28 15:25:13+00:00
draft: false
title: I Want A Better Keyboard
slug: i-want-a-better-keyboard
tags:
- keyboard
- KHAN!!!!!
- lego
- vim
---

Over on Hacker News, there is a [discussion](https://news.ycombinator.com/item?id=6286735) about [Atwood's new keyboard](http://www.codinghorror.com/blog/2013/08/the-code-keyboard.html). It looks nice, but it's not my ultimate keyboard. So bored rich people out there, build me a better keyboard.

{{< img src="natural-keyboard.jpg" cmd="Resize" opt="250x jpg" float="right" >}}
First, it needs to be ergonomic. Microsoft has pretty much perfected this, so let's start by copying their natural keyboard design. The basic wave shape and key layout of the current natural keyboards is great, especially since they fixed the layout of the navigation (insert/delete) cluster. We'll drop the stupid silver buttons across the top: they're way too far to reach from the home row. We'll also need to nuke the zoom thing in the center. We're going to need that space for something else later.

{{< clear >}}

{{< img src="deathstalker.jpg" cmd="Resize" opt="250x jpg" float="left" >}}
Next, let's actually make it work with Macs properly. Atwood's idea of using dipswitches is nice, but we can do better. Razer includes a little display on some of their keyboards. We're going to copy that and use the display to setup the keyboard. Want a Mac modifiers with Colemak? Go nuts. It's just a menu option away.

A nice simple toggle button will switch the keyboard in and out of setup mode. The display will be up where all those useless silver buttons on the natural keyboard are. We'll build a nice, simple configuration system. This also gives us the advantage of not really needing drivers. Our keyboard is just going to send keystrokes. All its smarts live onboard.

We're also going to be awesome and include the alternate keycaps for both Mac and Windows layouts so the keyboard labels match reality.

Mechanical switches are a given. I like Cherry brown's, but being a high end keyboard, we should offer people their choice.

The keyboard also needs a backlight. Since LEDs are cheap, we're going to go with an RGB backlight that adjustable to whatever color people want. The light will also adjust to the brightness of the room like Apple keyboards do. The color will be settable in our awesome config program.

{{< clear >}}

{{< img src="space-cadet.jpg" cmd="Resize" opt="250x jpg" float="right" >}}
It needs to look good too. All black tends to be a little boring, but it's a start. We'll add some touchs of color to give it that space cadet look. The WASD keys should a nice red, since they're used for killing. The HJKL keys should be a rich purple, since they are used by programming royalty. Modifiers will be blue in the space cadet tradition, and the number pad green because that's where the money lives. Yes that makes it US-centric. No I don't care.

Since we have fancy color changing tech already for the backlight, each of the groups will have their own adjustable colors so you can still be awesome in the dark, like Batman.

Speaking of VIM, we need to add another escape key. The standard one is too far away. I think sticking another in the middle, just above the space bar, replacing the stupid zoom on the natural keyboard, would be a perfect place.

The keyboard also needs to be both wired and wireless. And when I say wireless, I mean Bluetooth— none of this proprietary shit. The keyboard will have a ton of rechargeable battery that will charge when it's plugged in. Its cord will be removeable on the keyboard side, so when I don't have to fuck around on the back of the computer when I want to go wireless. The connector on the keyboard side will be standard micro-USB, so when your cat chews it up, it's easy to find a replacement. Obviously the keyboard will switch between wired and wireless mode seamlessly.

The keyboard should also be heavy. Atwood's got a good idea with the steel back: we'll steal that. I should be able to kill zombies with this thing.

{{< clear >}}

{{< img src="khan.jpg" cmd="Resize" opt="250x jpg" float="right" >}}
The wrist rest should also be nice. The latest Microsoft natural keyboards have a kind of faux-leather which is actually pretty sweet. We're going to do one better though: Rich Corintian Leather. The wrist rest should also be removable, for those heathens who don't like them. But rather then use finicky plastic tabs that will just break, we're going to put awesome rare-earth magnets in the wrist rest. Since the base of the keyboard is steel, they'll hold on to each other nicely.
The keyboard should also be an Arduino, because that's just cool. It's going to need a microcontroller anyway to handle the config screen, might as well make it something standard and open-source. Any unused pins will be routed to a header on the back so folks can add whatever crazy features I haven't thought of. The firmware will be open source, because anything else is stupid.

{{< clear >}}

{{< img src="optimus.jpg" cmd="Resize" opt="250x jpg" float="left" >}}
I've also always liked the idea of programmable keys on the left side of a keyboard, like the king of keyboard vaporware, the Optimus, theoretically had. This little side keyboard will be optional. It'll attach to the main keyboard with magnets and pogo pins. Like the Optimus, these programmable keys will have little displays in them so I don't have to guess if I assigned iTerm to #1 or #5. This bit will be the only part that requires a driver.

{{< clear >}}

{{< img src="code-mediakeys.jpg" cmd="Resize" opt="250x jpg" float="right" >}}
Since we eliminated the media keys from the natural keyboard, we'll need to add them back somewhere. I really like Atwood's idea of reusing the navigation cluster, so we'll steal that idea too.

{{< clear >}}

{{< img src="lego-keyboard.jpg" cmd="Resize" opt="250x jpg" float="left" >}}
Keyboard feet are a contentious issue. Some people like the front of the keyboard up, some like the back up. And we need various heights for both. I think a simple solution is to use LEGO. A strip along the front and back of the keyboard 2 studs wide will give a place to snap on some LEGO and set the height to exactly what the user wants.

{{< clear >}}

So anyone out there know anything about manufacturing or electronics design? Let's make this thing a reality. Throw up a Kickstarter. I'd be willing to pay $400 for this keyboard, and I'm sure others would too.
