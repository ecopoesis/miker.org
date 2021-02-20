---
author: miker
date: 2019-02-18 23:07:37+00:00
draft: false
title: Building a better keyboard
slug: building-a-better-keyboard
thumbnail: "media/top-view.jpg"
tags:
- cadquery
- keyboard
- openscad
- vim
---

I [wanted a better keyboard](http://miker.org/i-want-a-better-keyboard/) but my plea to the industry had no effect. Since no one would make one for me I built the keyboard myself. My main goals were:  

* Standard split-QWERTY layout mirroring the Microsoft Natural Keyboards  
* No number pad  
* High quality mechanical switches  
* Bluetooth and USB-C connections  
* Plug and play (no-solder) microcontroller replacement

### Layout

Building a keyboard naturally starts with designing the key layout. I used the wonderful [Keyboard Layout Editor](http://www.keyboard-layout-editor.com) to build a tweaked version of the classic Microsoft Natural Keyboard layout.

{{< img src="layout.png" caption="NEK Type A layout" link="http://www.keyboard-layout-editor.com/##@_backcolor=%236b6767%3B&@_x:0.5&c=%23857eb1&p=R1&sm=cherry&sb=cherry&st=MX1A-G1Nx&a:7&w:1.75%3B&=esc&_x:0.5&c=%23c4c8c5%3B&=F1&=F2&=F3&=F4&_x:3%3B&=F5&=F6&=F7&=F8&_x:0.25%3B&=F9&=F10&=F11&=F12&_x:0.25&c=%23857eb1%3B&=%3Ci%20class%2F='kb%20kb-Multimedia-Mute-1'%3E%3C%2F%2Fi%3E&=%3Ci%20class%2F='kb%20kb-Multimedia-Volume-Down-2'%3E%3C%2F%2Fi%3E&=%3Ci%20class%2F='kb%20kb-Multimedia-Volume-Up-1'%3E%3C%2F%2Fi%3E%3B&@_y:0.25&c=%23929390&a:5%3B&=~%0A%60&_c=%23525554%3B&=!%0A1&=%2F@%0A2&=%23%0A3&=$%0A4&=%25%0A5&=%5E%0A6&_x:2.5&w:1.5%3B&=%2F&%0A7&=*%0A8&=(%0A9&=)%0A0&_c=%23929390%3B&=%2F_%0A-&=+%0A%2F=&_c=%2395bfe8&a:4&w:2%3B&=%0A%0A⌫%0Adelete&_x:0.25&p=R2&a:7%3B&=insert&_p=R1%3B&=home&_p=R3%3B&=page%20up%3B&@_p=R2&a:4&w:1.5%3B&=%0Atab&_c=%23525554&a:7%3B&=Q&=W&=E&=R&_w:1.5%3B&=T&_x:2.5%3B&=Y&=U&=I&=O&=P&_c=%23929390&a:5%3B&=%7B%0A%5B&=%7D%0A%5D&_w:1.5%3B&=%7C%0A%5C&_x:0.25&c=%2395bfe8&p=R1&a:4%3B&=%0A%0A⌦%0Adelete&_p=R2&a:7%3B&=end&_p=R4%3B&=page%20down%3B&@_p=R3&a:4&w:1.75&l:true%3B&=⇪%0Acaps%20lock&_c=%23525554&a:7%3B&=A&=S&=D&_n:true%3B&=F&_w:1.25%3B&=G&_x:2.5&w:1.25%3B&=H&_n:true%3B&=J&=K&=L&_c=%23929390&a:5%3B&=%2F:%0A%2F%3B&=%22%0A'&_c=%2395bfe8&a:4&w:2.25%3B&=%0A%0A%0Areturn%3B&@_y:-0.5&x:19.25&p=R4&a:7%3B&=↑%3B&@_y:-0.5&a:4&w:2%3B&=⇧%0Ashift&_c=%23525554&a:7%3B&=Z&=X&=C&=V&=B&_x:2.5&w:1.5%3B&=N&=M&_c=%23929390&a:5%3B&=%3C%0A,&=%3E%0A.&=%3F%0A%2F%2F&_c=%2395bfe8&a:4&w:2.75%3B&=%0A%0A⇧%0Ashift%3B&@_y:-0.5&x:18.25&a:7%3B&=←&=↓&=→%3B&@_y:-0.5&a:4&w:1.5%3B&=%0A%0A%5E%0Acontrol&_w:1.25%3B&=%0A%0A⌥%0Aoption&_w:1.5%3B&=%0A%0A⌘%0Acommand&_a:7&w:2.75%3B&=&_x:2.5&w:2.75%3B&=&_a:4&w:1.5%3B&=⌘%0Acommand&_w:1.25%3B&=⌥%0Aoption&_w:1.5%3B&=%5E%0Acontrol&_a:7&w:1.25%3B&=" >}}

The big changes I made were a larger escape key for ease of `vim` and dedicated volume control keys since those are the only media keys I have ever used. Sorry [Natural Keyboard Elite](https://en.wikipedia.org/wiki/Microsoft_ergonomic_keyboards#Natural_Keyboard_Elite) diehards: I kept the classic inverted T. I also added a blank key below the right-shift for future expansion but mostly because the keyboard looked unbalanced without it.

### Case design

Now that I had a layout I could design the case. Pretty early on I knew that I wanted the keyboard to be a CNCed aluminum case. I envisioned a "bottom-up" design: no exposed fasteners on the top but instead screwing up through a plate mount into the aluminum case with a rubber gasket for damping vibrations and locking the screws.

{{< imgraw src="stack-up.svg" caption="Physical keyboard stack" >}}

I used [swillkb's Plate and Case Builder](http://builder.swillkb.com/) to generate `SVG` and `DXF` files from Keyboard Layout Editor files. I made the plates a bit larger than necessary so I would have flanges to screw through. To simplify life I planned on only screwing through the plate: the PCB would only be attached to the switches with solder.

I first started building the case in [OpenSCAD](http://www.openscad.org) because I used it for some simple 3D printed designs before. Though great for simple designs working with multiple rotated planes is difficult in OpenSCAD. Also as I discovered late in the process OpenSCAD only generates `STL` files which is fine for consumer 3D printers but not what is needed for CNC machines which generally want `STEP` files.

{{< img src="openscad-final.png" caption="Final OpenSCAD iteration" link="https://github.com/ecopoesis/nek-type-a/blob/41905dad19aab60768523cb26840738a3dbb7f68/body.stl" >}}

I still wanted to use a programmatic CAD tool and found [CadQuery](https://github.com/dcowden/cadquery) which uses a FreeCAD as a backend and Python for the frontend. Running CadQuery in Docker was the simplest and most reproducible solution for me. I could edit my Python script and run `make` to get my `STL` and `STEP` files out: a very simple development loop. Using Python opened up a world of useful libraries like `NumPy`, `svgpathtools` and `pyclipper`. The last two were especially important because they let me easily manipulate the `SVG`s coming from swillkb's tool.

Thanks to CadQuery it's simple to pass the various angle of the keyboard (the split, the tilt and the tent) as runtime options and almost always get a working object.

{{< img src="cadquery-final.png" caption="Final CadQuery version" link="https://github.com/ecopoesis/nek-type-a/blob/1bc2ed3ca812d8c6d1e43641318b45254b60a80c/body/target/body.stl" >}}

### Electronics

With the case done it was now time to tackle the electronics. I wanted to develop three boards: one each for the left and right halves of the keyboard and then a center control unit connected to the halves with ribbon cables. I wanted to keep the halves with the keyswitches as simple as possible to make future upgrades just a matter of swapping out the center board.

I had no previous experience designing PCBs so I started with [Clueboard's Kalerator](https://kalerator.clueboard.co). This handy tool takes a layout from Keyboard Layout Editor and generates an [Eagle](https://www.autodesk.com/products/eagle/overview) script that gives you most of the layout. This was a very easy way to get the footprints of the keyswitches laid out perfectly. For the left and right boards my only mistake was forgetting about the clearance for the stabilizers on the left board: they overlapped with the diodes for those switches. Luckily its easy to put the diode on the other side of the board.


{{< img src="left-001-top.png" caption="Left PCB revision 001 top view" >}}
{{< img src="right-001-top.png" caption="Right PCB revision 001 top view" >}}

I wanted the keyboard to be able to use Bluetooth or USB connection. I also liked the idea of upgradability and a standardized form factor so I used an [Adafruit Feather 32u4 Bluefruit LE](https://www.adafruit.com/product/2829) as my microcontroller. Instead of soldering it directly to my PCB I would use headers so it is replaceable if I ever need more power. My center PCB is essentially a very weird Feather wing.

The Feather does not have enough pins to support my layout so I connected only my row pins (merging the left and right sides) and the left columns directly. The right columns are connected though a [MCP23017E-S/P](https://www.microchip.com/wwwproducts/en/MCP23017) I/O expander which connects to the Feather via the I2C bus.

I ended up needing to do a second spin of the center PCBs because I forgot about clearance for the three mounting holes and because I used the wrong footprint for the switch connector.

{{< img src="center-002-top.png" caption="Center PCB revision 002 top view" >}}

### Manufacturing

The keyboard was designed to be easily manufactured. The main components that need to be built and the manufacturer I used are:

* The aluminum CNCed case: [Xometry](https://www.xometry.com)  
* The rubber gaskets: [Big Blue Saw](https://www.bigbluesaw.com)  
* Steel plates: [Lasergist](https://lasergist.com)  
* Acrylic plate: [Big Blue Saw](https://www.bigbluesaw.com/)  
* PCBs: [OSH Park](https://oshpark.com)

### Software

[QMK](https://github.com/qmk/qmk_firmware) is a wonderful open-source keyboard firmware. It has baked-in support for 32u4 AVRs and supports the Feather (including Bluetooth). I did need to add add support for the IO expander and fork `matrix.c` to select columns via the expander. [My branch](https://github.com/ecopoesis/qmk_firmware/tree/nek_type_a) of QMK can be found on GitHub.

### Assembly

The first step in assembling a NEK Type A is to install the stabilizers on the PCB and then solder on the diodes.

{{< img src="left-pcb.jpg" caption="Left PCB with stabilizers and diodes" >}}

The next step is to install the keyswitches and the case. In the first keyboard I build I used Cherry MX Clears. It's easiest to start with the four corners so you get a good alignment between the plate and the PCB. After the corner switches are soldered up it's then just a matter of filling in the rest.

{{< img src="left-switches.jpg" caption="Left plate with corner switches" >}}

After all the switches for a plate are in place I like to add a set of temporary keycaps. I intentionally left a little slop for attaching the assembled plate to the case because I was unsure of the tolerances of the various manufacturing processes I used to create the sub-assemblies. Having the keycaps on makes lining things up easier.

{{< img src="left-keycaps.jpg" caption="Left plate with keycaps" >}}

Next is adding all the components to the center PCB. I generally go from flattest to tallest component when soldering because it makes it easy to use the table to support the component. Note that the I/O expander is intolerant of lot of heat so I use a socket to mount it.

{{< img src="assembled-center.jpg" caption="Assembled center PCB" >}}

Now it's time to put everything in the case. The assembled key plates mount with M5 screws with the laser cut rubber separating the steel and aluminum.

{{< img src="case-with-plates.jpg" caption="Case with plates mounted" >}}

The center PCB mounts with M3 standoffs and M3 screws.

{{< img src="center-mounted.jpg" caption="Center PCB mounted in case" >}}

Add some custom length ribbon cables, a panel mount USB-C cable, a USB-C to Micro USB adapter, an arcade switch for power, a battery, a laser-cut acrylic panel and some M5 feet and you have a completed keyboard.

{{< img src="bottom-view.jpg" caption="Bottom view of assembled keyboard" >}}

{{< img src="back-view.jpg" caption="Back view (port and switch) view of assembled keyboard" >}}

{{< img src="top-left-view.jpg" caption="Top-left view of assembled keyboard" >}}

{{< img src="top-view.jpg" caption="Top view of assembled keyboard" >}}

Full sources and detailed assembly directions can be found on [GitHub](https://github.com/ecopoesis/nek-type-a).
