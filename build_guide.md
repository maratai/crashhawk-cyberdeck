CRASHHAWK CYBERDECK

Last update: 2025-11-01

Yoon Ha Lee (yoon@yoonhalee.com)

WIP build guide for a Raspberry Pi 4B-based cyberdeck/writerdeck with
bonus (?) Machineries of Empire in-joke. Notes for my own reference.
I don't offer support, sorry!

![cyberdeck build WIP](https://github.com/maratai/crashhawk-cyberdeck/blob/main/2025-11-01-rpi-02.jpg)

For my reference: [Markdown cheat sheet](https://www.markdownguide.org/cheat-sheet/)

# Introduction
My goal with this writerdeck/cyberdeck was to create something with the
following desiderata because I have ongoing health problems; on a bad
day, sitting upright is difficult and I'm largely confined to lying down
in bed. I also have wrecked hands (neuropathy) so some of the off-the-
shelf "type into your smartphone" solutions work poorly for me.

Also, I wanted to build a thing, so there's that. :3

- Handheld form factor
- With a display I can actually read
- With a small physical keyboard for thumb- or forefinger-typing
- With the *option* of connecting a full(er) size keyboard over 2.4GHz
wireless dongle or directly via hard connection (USB-A or USB-C for
preference). I know Bluetooth exists, but I have iffy luck getting
Bluetooth peripherals to connect properly.
- That lets me get my files off the device for backup, whatever the
method. This was, incidentally, what sank the Alphasmart Neo for me,
terrific older devices that they are. At the point where getting a
10,000-word text file out over simulated keyboard mode over USB takes
*forty minutes*, this is no longer viable for production writing. (I'm
a novelist by profession. It pays the bills!)
- That works with some kind of stand for use as a small "regular"
computer on days when I can sit up without too much trouble.
- That supports a barebones text editor. I'm happy to work in nano!
- That doesn't require soldering. I've never soldered; I'd like to
learn, but until then...

I'm up to a working proof of concept with all the components and now
able to consider case design and construction. I'm *not* doing 3D
printing since I don't own a 3D printer and don't know how to create the
appropriate STL files etc (yet). I'll be using Davey board or leather
and bookbinding, box-making, leatherworking techniques since I have
supplies and tools on hand and for me that's now a sunk cost.

There's no case (yet) but all the components are talking to each other.

Total weight/mass of everything (display + computer + keyboard + battery +
associated connectors etc): about 13 oz (360 g).

Nota bene: Regrettably, I can't provide build support. I'm a hobbyist
with a B.A. in math, limited "lite" coding experience (BASIC, Turbo
Pascal,  Java, LISP/Scheme/Dylan, Inform 6 and Inform 7, Python, Lua).
I'm currently *learning* C, C++, and Forth, but I'm not a dev, sorry!
I have no prior experience in computer hardware.

# Build List
Nota bene: some of these are Amazon links but I'm sure you can source
equivalents elsewhere.

I wish to acknowledge the following inspirational cyberdeck build by
AlleyCat:
[ACOS Termyte Pocket Cyberdeck](https://www.printables.com/model/1347355-acos-termyte-pocket-cyberdeck-read-the-description)
although I ended up using different components!

the computery bit
[Raspberry Pi 4B](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/))
sMine is the 8 GB RAM version, which is overkill for my use case,
but this is what I inberited in handspun yarn barter from my
husband's coworker. $80 USD if I'd bought this specific model;
the base version (less RAM) is more like $40 USD. The linked site also
has documentation and specs.

Mine came with a microSD card from my husband's coworker, which
will set you back around $10 to $15 USD depending on specifics.

the display bit
[Hosyond 5 Inch Touchscreen IPS MIPI DSI Displa](https://www.amazon.com/dp/B0CXTFN8K9)
Compatible with Raspberry Pi 5/4/3, 800x480 Pixel, no driver needed
(Hosyond's documentation)[https://hosyond.com/]
You want the "5 inch DSI Display" link, which will get you a
downloadable PDF with instructions for wiring and setup.
This was the easiest semi-affordable display I could get running
without trouble, after a prior failure to figure out a deprecated
dependency in the driver for a different, smaller, cheaper  display.
The touchscreen is nice as an ad-hoc mouse substitute. About $35 USD.

the portable rechargeable battery bit
[PiSugar S Plus](https://www.pisugar.com/products/pisugar-s-plus-raspberry-pi-ups)
I also have a PiSugar3 UPS, which I suspect would work too.
[PiSugar documentation](https://docs.pisugar.com/docs/product-wiki/battery/ups-intro)
as of this writing. You'll probably want to use the *longer* of the
included FPC flexible cables if you're connecting the PiSugar battery
to the Raspberry Pi proper. $30 USD.

the regular power supply with USB-C cable
I don't think you need a special one, but check the rpi 4B's power etc
requirements. The rpi 4B receives direct power over USB-C. I inherited
this too from my husband's coworker. About $5 to $10 USD.

the smol keyboard bit
[Serounder 2.4GHz Touchpad Keyboard,A8 Mini Rechargeable Keyboard](https://www.amazon.com/dp/B07S7BQMRY)
About $20 USD. The rpi 4B is also happy to talk to a fuller size
2.4GHz wireless keyboard or, over USB-A, to a regular wired keyboard.
I *think* this touchpad keyboard is intended for GAMING console use.
I normally can't stand ortholinear keyboard layouts, but for something
used with  hunt-and-peck thumb or forefinger typing, it works great!

For a full-sized-ish 2.4GHz travel folding keyboard + mouse + case:
[ProtoArc Foldable Keyboard and Mouse, XKM01](https://www.amazon.com/Foldable-ProtoArc-Bluetooth-Rechargeable-Full-Size/dp/B0BTNMVJ43/https://www.amazon.com/Foldable-ProtoArc-Bluetooth-Rechargeable-Full-Size/dp/B0BTNMVJ43/v)
about $80 to $90 USD so somewhat spendy. It is, however, a beautifully 
designed case that includes a phone/small tablet folding stand. The
USB-A dongle connects both mouse and keyboard over 2.4GHz wireless,
but you also have the option of Bluetooth. I don't know how to connect
to Bluetooth from Raspberry Pi OS command line (yet) hence going with 
the USB-A dongle for 2.4GHz wireless. Recharges over USB-C. 
Key action is crisp although, as expected with a lighter folding
keyboard, extremely shallow.

For a non-folding very slim/lightweight USB-A wired keyboard, I like
[Vilros 15 Inch USB Keyboard with Touchpad](https://www.amazon.com/Vilros-Inch-Keyboard-Touchpad-Great-Raspberry/dp/B08PW3LR3W/)
about $35 USD. The touchpad works fine for a lightweight mouse
substitute. But I'm sure you have your own favorites!

Without battery or case, this is a build costing a bit north of $100 USD
not including shipping and/or tax; with battery, closer to $150 USD.
If you skip the smol keyboard and already have some USB-A or Bluetooth
keyboard lying around etc, you may need to spend less.

I'm making the case with random Davey Board, bookbindin, leatherworking
I have lying around. There are probably better 3D printed case
solutions but bookbinding/cardboard box-making techniques are
something I can readily prototype at home without having to learn how
to STL. I'm a hobbyist, not a professional; by "leatherworking" I mean
"it's functional but made from a discounted C-grade double shoulder for
learning/hobby purposes.""

I would like to work out a version that runs off the Raspberry Pi
Pico 2W (under $10 USD) *and* a smaller and less spendy display.
Ideally, this would result in a less expensive, lighter weight  build.
Unfortunately, I'm desperately confused by the display + connector +
working driver situation so that may or may not happen.

# Software
These aren't recommendations as such and I haven't written any of this
software. But these are all free/open source for easy downloading.

- [Raspberry Pi OS](https://www.raspberrypi.com/software/operating-systems/)
flashed to microSD card
- [Dusk OS](https://duskos.org/)
My main goal is to mess with coding in Forth. I'm running this on top
of Raspberry Pi OS.
- [micro](https://micro-editor.github.io/) text editor for writing
- git for backup and version control

# Getting Files off the Device
Fortunately, the rpi 4B supports
- Wi-fi, so I can physically print to either of my networked printers
at home for hardcopy, or otherwise use the internet. I'm currently
using git for one project.
- USB-A ports, so I can copy files over to a thumb drive
