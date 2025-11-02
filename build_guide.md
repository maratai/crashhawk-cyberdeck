CRASHHAWK CYBERDECK

Last update: 2025-11-02

Yoon Ha Lee (yoon@yoonhalee.com)

WIP build guide for a Raspberry Pi 4B-based cyberdeck/writerdeck with
bonus (?) Machineries of Empire in-joke. Notes for my own reference.
I don't offer support, sorry!

![cyberdeck build WIP](https://github.com/maratai/crashhawk-cyberdeck/blob/main/2025-11-01-rpi-02.jpg)

For my reference: [Markdown cheat sheet](https://www.markdownguide.org/cheat-sheet/)

# Introduction
My goal with this writerdeck/cyberdeck was to create something with the
following desiderata because I have ongoing health problems; on a bad
day, sitting upright is difficult and I'm confined to lying down
in bed. I also have wrecked hands (neuropathy) so some of the off-the-
shelf "type into your smartphone" solutions work poorly for me.

Also, I wanted to build a thing, so there's that. :3

-
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
- That supports a barebones text editor. I'm happy to work in nano! (I'm using micro.)
- That doesn't require soldering. I've never soldered; I'd like to
learn, but until then...

I'm up to a working proof of concept with all the components wired together
I'm now considering case design and construction. I'm *not* doing 3D
printing since I don't own a 3D printer and don't know how to create the
appropriate STL files etc (yet). Likewise, I regret that I'm not a
carpenter or woodworker.

I'll be using **Davey board or leather**;
bookbinding, allied cardboard box-making, leatherworking techniques
since I have supplies and tools on hand and for me that's a sunk cost (for me).

There's no case design (yet) as that's the current step,
but all the components are talking to each other.

**Nota bene**: Regrettably, I can't provide build support.
I have no prior experience in computer hardware.
I'm a hobbyist with a B.A. in math, limited "lite" coding experience
(BASIC, Turbo Pascal,  Java, LISP/Scheme/Dylan, Inform 6 and Inform 7,
Python, Lua, enough command line to get by).
I'm currently *learning* C, C++, and Forth, but I'm not a dev, sorry!

# Cost
Without battery or case, this is a build costing a bit north of $100 USD
not including shipping and/or tax as of this writing;
with battery, closer to $150 USD.

If you skip the smol keyboard and already have some USB-A or Bluetooth
keyboard or other components lying around etc, you may be able to spend 
less.

# Weight
Total weight/mass of everything (display + computer + keyboard + battery +
associated connectors etc) **without case**: about 13 oz (360 g).

Weight's a concern for me due to my wrecked hands (medical).

# Build List
**Nota bene:** some of these are Amazon links but I'm sure you can source
equivalents elsewhere. I'm based in the USA; all prices given in USD
unless otherwise indicated.

I wish to acknowledge the following inspirational and terrific cyberdeck
build by AlleyCat:
[ACOS Termyte Pocket Cyberdeck](https://www.printables.com/model/1347355-acos-termyte-pocket-cyberdeck-read-the-description),
although I ended up using different components!

## the computery bit
[Raspberry Pi 4B](https://www.raspberrypi.com/products/raspberry-pi-4-model-b/)

Mine is the 8 GB RAM version, which is overkill for my use case,
but this is what I inberited in handspun yarn barter from my
husband's coworker. **$80 USD** if I'd bought this specific model;
the base version (less RAM) is more like **$40 USD**. The linked site
also has documentation and specs.

Mine came with a microSD card from my husband's coworker, which
will set you back around **$10 to $15 USD** depending on specifics.

![art yarn barter](https://raw.githubusercontent.com/maratai/crashhawk-cyberdeck/refs/heads/main/2025-09-19-yarn.jpg)

## the display bit
[Hosyond 5 Inch Touchscreen IPS MIPI DSI Displa](https://www.amazon.com/dp/B0CXTFN8K9)

Compatible with Raspberry Pi 5/4/3, 800x480 pixels, no driver needed.

[Hosyond's documentation](https://hosyond.com/)

You want the **"5 inch DSI Display" link** (scroll down),
which will get you a downloadable PDF with instructions for wiring and
setup.

This was the easiest semi-affordable display I could get running
without trouble, after a prior failure to figure out a deprecated
dependency in the driver for a different, smaller, cheaper display.
The touchscreen is nice as an ad-hoc mouse substitute. About **$35 USD**.

Use the *longer* included FPC flexible cable to the rpi if
you're using a PiSugar battery (so you can accommodate it too).

## the portable rechargeable battery bit
[PiSugar S Plus](https://www.pisugar.com/products/pisugar-s-plus-raspberry-pi-ups)

[PiSugar documentation](https://docs.pisugar.com/docs/product-wiki/battery/ups-intro)

Use the *longer* of the
included FPC flexible cables to connect the Hosyond display to the rpi
if you're *also* connecting the PiSugar battery
to the rpi proper. **$30 USD**.

## the regular power supply with USB-C cable bit
I don't think you need a special one, but check the rpi 4B's power etc
requirements. The rpi 4B receives direct power over USB-C. I inherited
this from my husband's coworker. About **$5 to $10 USD**.

## the smol keyboard bit
[Serounder 2.4GHz Touchpad Keyboard,A8 Mini Rechargeable Keyboard](https://www.amazon.com/dp/B07S7BQMRY)

About **$20 USD**. The rpi 4B is happy to talk to a fuller size
2.4GHz wireless keyboard or, over USB-A, to a regular wired keyboard.
I *think* this touchpad keyboard is intended for GAMING console use.
I normally can't stand ortholinear keyboard layouts, but for
hunt-and-peck thumb or forefinger typing, it works great!

## other keyboard bits
For a full-sized-ish 2.4GHz travel folding keyboard + mouse + case
(optional, but I like having the option):

[ProtoArc Foldable Keyboard and Mouse, XKM01](https://www.amazon.com/Foldable-ProtoArc-Bluetooth-Rechargeable-Full-Size/dp/B0BTNMVJ43/https://www.amazon.com/Foldable-ProtoArc-Bluetooth-Rechargeable-Full-Size/dp/B0BTNMVJ43/v)

About **$80 to $90 USD&& so somewhat spendy. It is, however, a beautifully 
designed case that includes a phone/small tablet folding stand. The
USB-A dongle connects both mouse and keyboard over 2.4GHz wireless,
but you also have the option of Bluetooth. I don't know how to connect
to Bluetooth from Raspberry Pi OS command line (yet) hence going with 
the USB-A dongle for 2.4GHz wireless. Recharges over USB-C. 
Key action is crisp although, as expected with a lighter folding
keyboard, extremely shallow.

For a non-folding very slim/lightweight USB-A wired keyboard
(optional), I like

[Vilros 15 Inch USB Keyboard with Touchpad](https://www.amazon.com/Vilros-Inch-Keyboard-Touchpad-Great-Raspberry/dp/B08PW3LR3W/)

About **$35 USD**. The touchpad works fine as a lightweight mouse
substitute. But I'm sure you have your own favorites!

# WIP - thoughts toward a case design and build

![scribbled preliminary design thoughts for a case](https://raw.githubusercontent.com/maratai/crashhawk-cyberdeck/refs/heads/main/IMG_0219.jpeg)

**To-do:** Prototype case form factor (etc) in cheap cardboard.

I'm making the case with random Davey Board, bookbinding, leatherworking
I have lying around. There are probably better 3D printed case
solutions but bookbinding/cardboard box-making techniques are
something I can prototype at home without having to learn how
to STL (yet).

I'm a hobbyist, not a professional; by "leatherworking" I mean
"it's functional but made from a discounted C-grade double shoulder for
learning/hobby purposes." The real bottleneck to learning leatherworking
is, unfortunately, the cost of *leather*; some of the tools are not
cheap either, depending on what you're doing. I discovered the hard
way that it's cheaper per unit of "area" to grimly save up for a sale
on lower-grade double shoulders or similar larger cuts (to practice on,
since I am not daft enough to ruin fancy leather on a learning project)
rather than buying the smaller cuts, especially since I enjoy hobbyist
leatherworking on and off. (I'm told the "better" way to get started,
if possible, is make some friends who will give you their off-cuts to
get started! Goodness knows I've only been doing this a couple years
and I already have a small stash of off-cuts.)

I would like to work out a version that runs off the **Raspberry Pi
Pico 2W** (under **$10 USD**) *and* a **smaller, cheaper display**.
Ideally, this would result in a less expensive, lighter weight build.
Unfortunately, I'm desperately confused by the display + connector +
working driver situation (I lack the expertise to code or debug display
drivers myself at this point in time) so that may or may not happen.

# Software
These aren't recommendations as such and I haven't written any of this
software. But these are all **free/open source** for easy downloading.

[Raspberry Pi OS](https://www.raspberrypi.com/software/operating-systems/)

Flashed to microSD card.

[Dusk OS](https://duskos.org/)

My goal is to mess with coding in Forth. I'm running this on top
of Raspberry Pi OS. I'd like to try a baremetal Dusk OS build someday,
but I need to suss out the display situation as I definitely don't know
how to write display drivers this (alas).

[micro](https://micro-editor.github.io/)
Text editor for writing. Really excellent.

Git for backup and version control.

# Getting Files off the Device
Fortunately, the rpi 4B supports

- **Wi-fi**, so I can physically print to either of my networked printers
at home for hardcopy, or otherwise use the internet. I'm currently
using **git** for offsite backup of one project.
- **USB-A ports**, so I can copy files over to a thumb drive. Two are occupied by USB-A dongles (2.4GHz wireless), but there are still two left!
