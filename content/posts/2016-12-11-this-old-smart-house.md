---
author: miker
date: 2016-12-11 04:35:42+00:00
draft: false
title: This Old Smart House
slug: this-old-smart-house
tags:
- airport
- alexa
- caseta
- echo
- fios
- haiku
- homekit
- hue
- hue tap
- lutron
- mini-split
- moca
- myq
- nest
- pico
- siri
- sonos
---

Our house is old. City records show it was built in 1910, but that's just the age the city assigned to all the houses older then that. Our neighbors, who have a house that started life as a mirror image of ours, have found old newspapers in their attic from the 1870s making that our best guess for the age.

In some cases having an old house is great: structurally the house is solid. Big chunks of our house were built with old-school dimensional lumber from the era when a 2x4 was actually 2 inches by 4 inches. We have walls with 8x10 angled beams in them. Our basement has 2 foot thick field stone walls. In the 19th century folks built things to last.

Of course, an ~145 year old house also has its issues. The house is on at least its fourth heating fuel source (I know where my coal chute is, do you?). The house wasn't built with electricity in mind, and is on its third rewire. Some of our lights still have gas lines going to them.

All this old infrastructure makes adding some intelligence to the house a difficult task. A full rewire is out of the question, so we've tackled the process has a bunch of independent, incremental upgrades that can work together.

{{< clear >}}

{{< img src="airport.jpg" cmd="Resize" opt="250x jpg" float="right" >}}
For our internet connection, we're lucky enough to have Verizon Fios. If you can get Fios, you should. It just works and always gives the speed your pay for. We don't use Verizon's crappy router. In its place we use Apple Airports. They also just work, and it's disappointing that Apple is no longer going to make them. I've used the last three generations of Airports, and I've never once had to reboot them to make the internet work.

The house is big enough that we need two Airports to get good coverage. Luckily, the previous owners ran some Ethernet, all terminating in our electrical panel's cabinet in the basement. This is the same place the Fios ONT lives, so the primary base station lives there. Using one of the existing Ethernet runs, we have the other base station at the other end of the house on the second floor. This combo gives us good coverage.

Rather then rely on WiFi for TV streaming, we use Actiontec MoCA bridges over an existing coax run (the previous owners ran coax to every room in the house) to connect our TV and its various devices.

{{< clear >}}

{{< img src="haiku.jpg" cmd="Resize" opt="250x jpg" float="left" >}}
One of the big problems we had was a lack of light switches in our kitchen and great room. The main lights in these rooms were cheap Home Depot ceiling fans with pull cords. I hate crappy ceiling fans. They make noise, they wobble, they just generally suck. We replaced these three fans with Big Ass Fans Haiku fans. These are quite expensive, but are well worth it. The Haikus are silent. Literally no motor noise. The fans work with our Nest thermostats to keep the house at the right temperature. And they're motion activated, which solved our missing switch problems. The fans also have an iOS app (we're an Apple oriented house) that I never use because I never need to adjust anything.

I liked the Haiku fans so much we used two Haiku lights in our basement bathroom renovation. They're great because that part of our house is an extension of the original basement, and has a low concrete ceiling, so there's no room for a traditional in-ceiling light. Here, we use the Haiku wall switch to control the lights via WiFi. It works perfectly, with no delay I've ever noticed.

We use four Nest thermostats to run our various zones (two heating only, and two heating + cooling). We've turned off all the learning stuff Nest has that doesn't really work, and instead just set a schedule of what we'd like the temperature to be if we were home. We set the away temperature higher or lower (depending on season) and use the Skylark app on our phones to autoset home and away when our phones connect or disconnect from the house WiFi or when they go in or out of the geofence. This works really well and we don't have to go through the hassle of setting or keeping updated a schedule on the Nests. One of Nests is hooked up to a Mitsubishi mini-split that acts as the basement's cooling system with an adapter that Mitsubishi makes (PAC-US444CN-1). This is great because we don't have to use Mitsubishi's crappy remote, and it keeps all our HVAC unified.

We've replaced all our smoke detectors with Nest Protects. Because of the house's age, there were no hardwired connections between the existing smoke detectors, so if one went off none of the other did. Nest Protects fix this by using radio to connect to each other. Nest also have a nice app, so when one Protect has a low battery, you can figure out which it is (assuming you remember what you named them) and not stand around in the middle of the night trying to identify what direction the beep is coming from.

{{< clear >}}

{{< img src="hue-tap.png" cmd="Resize" opt="250x png" float="right" >}}
Our living room also doesn't have a light switch, or built in lights at all. Here we reused some Philips Hue bulbs we had from our old house with a Hue Tap switch. This works pretty well, though the Tap is sometimes hard to activate because in attempt to be cool it does without a battery and uses the energy of the click to power itself. We have the second-generation Hue Hub, which lets it work with HomeKit so we can use Siri to control things. We also use Hue bulbs in my daughter's room as nightlights. I do use this app every day putting my daughter to bed, so she can pick the color of her nightlight. Of course she chooses green every night, probably because she's a leet hacker.

{{< clear >}}

{{< img src="switch-box.jpg" cmd="Resize" opt="250x jpg" float="left" >}}
Everywhere else has light switches, though in some cases the switch and the light are several rooms apart. As part of a replacing all the outlets before we moved in (the previous outlets were a mishmash of styles and colors, and many were worn out and wouldn't hold a plug tightly) we also replaced all the switches with Lutron Caseta dimmers or switches. Caseta is awesome. The dimmers work well with a variety of lighting loads (we've switched to all LED) and the basic Caseta dimmer is a drop in replacement for a single pole switch-- no neutral needed. In a few places I've used the with neutral options Lutron makes, once to get dimmer LEDs in our theatre, and once because a crappy circuit just didn't work without the neutral.

{{< clear >}}

{{< img src="caseta-remote.jpg" cmd="Resize" opt="100x jpg" float="right" >}}
The Caseta line is nice, because it lets you remove any three-way circuits and switch them back to simple single pole switches. You can then use Pico remotes at the remote locations. Lutron makes an adapter that attaches the Pico to regular workbox, so any replaced three-ways will look nice. You can also use the adapter without a workbox, just sticking it right to the wall, which is handy for us because our dining room's light is controlled by a switch two rooms away. The Caseta hub also connects to Nest, so if the Protects go off, they turn on all the lights in the house, which seems like it'd be useful in an emergency.

{{< clear >}}

{{< img src="caseta-plug.jpg" cmd="Resize" opt="250x jpg" float="left" >}}
The Caseta line can work without a hub, but then you can't control it with your phone. We use the second-generation Caseta hub which added HomeKit compatibility. Even using the hub the switches and remotes respond instantly. It also let's us set useful schedules like turning the outside lights on at sundown. We also use a Lutron plugin dimmer for our Christmas Tree. Annoyingly, even in when off the plugin dimmer lets through a small amount of voltage, which is enough to turn on the first few green bulbs on the LED string. A great workaround I found in the Lutron forums was to plug a crappy USB charger into the other side of the plugin dimmer. The charger draws enough power so off really becomes off.

{{< clear >}}

{{< img src="sonos.png" cmd="Resize" opt="250x png" float="right" >}}
We also have a lot of Sonos-- fifteen rooms worth (it's nice when your wife works there). Mostly we just have standalone speakers or pairs, but in our basement kitchen we reused some existing in ceiling speakers with a Connect Amp. We also use a basic Connect to drive our theatre sound system. Sonos comes in real useful in our living room. With a Playbar, a Sub and a pair of Play 1s we get 5.1 surround sound without having run wires through our horsehair plaster walls. Only three of our twenty-one Sonos devices are plugged in to the wired network, the rest use the Sonos mesh to connect to the network.

Lutron makes an Audio Pico remote which works with Sonos. We use one of these in our basement kitchen so we can control its volume without having to open the Sonos app. Everywhere else just using the buttons on the speakers works well.

{{< clear >}}

{{< img src="echo.jpg" cmd="Resize" opt="100x jpg" float="left" >}}
Our main method of controlling all this is with Amazon Echo. We have a single Echo and six Echo Dots. For now, we control the Sonos stuff with Caseta scenes, which is a crappy hack, though my wife assures me that Echo integration is coming soon.

This works surprisingly well and it has become everyone's main way of interacting with the lights.

{{< clear >}}

{{< img src="breaker-box.jpg" cmd="Resize" opt="250x jpg" float="right" >}}
We also have a few random smart things not connected to Echo. Our garage door opener is a Chamberlain MyQ that connects to a little internet gateway. It nicely sends a push alert to our phones when we've forgotten to close the door. We use Schlage keypads on all our doors. Three of them are the old Zwave ones, no longer hooked to any hub. For our front door, we use the newer BLE one that is HomeKit compatible and connects via the Apple TV. It's handy for setting temporary codes for contractors or guests.

Using a bunch a disparate systems may seem insane, but it actually works really well. Other then the Echos, everything we have works with their corresponding cloud services are down. It also means that if one of the companies we rely on shuts down, we can just replace that piece of our house's stack and everything else will still work. All this was also 100% installed by us. The most technical piece is changing out the light switches which just isn't hard.

Plus, all this crazy tech lets us live in the Star Trek future. Sure, I might have to say "Alexa" or "Siri" instead of "computer", but the lights still change and the music still plays. Living in the future is very, very cool.

{{< clear >}}
