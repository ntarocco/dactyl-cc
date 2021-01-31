# My Dactyl-cc

A fun project to build your own custom keyboard without spending a fortune!

PHOTO

Here you can find a few tips to try to complete the various guides available on the Internet, to fill the gaps of what was not clear to me when building it.
I will not describe the entire process of cabling and assembling because this is very well covered in the link belows.

**How long did it take?**

At the beginning, I have spent quite some time to figure out what I needed to buy. Honestly, I went maybe too fast reading the various guides. It is a good idea to have understand first why you need each component :)
So after a few evenings and thanks to [my friend Pedro](https://github.com/pferreir/) who built the same keyboard before me, it took me:

* about 3/4 weeks to receive all the components
* about 2 *full* days to assemble it
* another day to fix assembling mistakes :)

Since this was a fun side project, outside my working hours, I was not in a hurry. It has been actually a great hobby during the confinement period that happened in France in 2020 because of the COVID pandemic.

In the end, it took me 2/3 months and I have spent about ~100 EUR in material.

**Let's start!**

The first reference link that you need to often get back to is the guide from [Michael Johns](https://github.com/mjohns): [A Dactyl like 3d printed keyboard written in C++](https://github.com/mjohns/dactyl-cc). This also because you can find there the STL files to 3D print the case. If you
are like me and you don't know much about 3D printing don't worry, I will share a few tips below :)

The second super useful guide is [Building a Dactyl Keyboard, Running QMK](https://www.joedevivo.com/2017-05-20-building-a-qmk-dactyl) (which is recommended in the one above). I do recommend to read it carefully because it contains many tips and lesson learned.
**WARNING:** do not follow exactly the cabling of the thumbs cluster as described there. That guide is for a Dactyl keyboard which has a slightly different thumbs cluster. I did that mistake and after programming the firmware I realized the issue and I had to fix the cabling (more on this below).

Similarly to this second guide, you can find [here](https://github.com/adereth/dactyl-keyboard/tree/master/qmk-guide) another similar one with some nice pictures and a schema of the **audio jack**, very useful!

## Shopping list (with explanations)

Below the list of components that I bought to assemble the keyboard.

### Case

I have used the STL files kindly shared by `mjohns` that you can find [in his repo](https://github.com/mjohns/dactyl-cc/tree/master/things). I think that they are great: the size of the case is perfect and the key switches are well blocked when inserted in each hole, they don't move.
I only found a bit hard to find a solution to close the bottom part of the case and to block the audio jack and USB connector, more on this later.

The hardest part was to get up to speed with 3D printing and different materials. I have watched lots of videos that explain the differences between materials to try to understand what was the most adapted for such project and to avoid to spend a fortune. I have also compared a few online website that 3D print things and in the end the best for me was [CraftCloud](https://craftcloud3d.com/).

* Material: **PLA**
* Color: **Black**
* Finishing: **Standard**
* Infill: **20%**

Basically I went for all the default and cheapest settings and I have to say that I am very happy with the result: the case is very solid, rigid, even the smallest parts, for example the small parts that blocks the key switches. I am also quite satisfied with the finishing, it looks brushed.

![Case 1](./pictures/case_1.jpg)

![Case 2](./pictures/case_2.jpg)

![Case 3](./pictures/case_3.jpg)

![Case 4](./pictures/case_4.jpg)

### Components

* 1 x [Teensy 2.0](https://www.pjrc.com/store/teensy.html): a microcontroller that where you will load the keyboard firmware and you will wire all keys. Will be in the right part of the keyboard and it will communicate with the left part via the audio jack.
* 1 x MCP23018: you will wire it to the keys of the left part of the keyboard and it will communicate with the Teensy via the audio jack.
* 1 x 28-pin DIP socket [OPTIONAL]: I have soldered all the cables to this socket and then plugged in the MCP. In this way you are sure not to overheat the MCP and you can eventually replace the socket in case of mistakes or damage.
* 68 x 1N4148 diodes: one per key switch, order a few spare ones because it is easy to do mistakes.
* 2 x 2.2K resistors: both wired to the audio jack on the right part, which is wired to the Teensy.
* 2 x TRRS Jack female: they will be wired in each side of the keyboard. Make sure that you buy TRRS ones, with 4 connections pins.
* 1 x TRRS Cable (male - male): cable to connect the 2 sides.
* 2 x TRRS extension cables (female - male) [OPTIONAL]: I have bought the shortest extension cables that I have found because the audio jack wiring is quite delicate and when plugging/unplugging the audio cable I broke multiple times the connections. With the extensions, I have glued the audio jack to the case so that it won't move and the audio cable will instead be plugged to the extensions.
* 1 x USB Mini-b male to USB b/c female: this needed to plug your keyboard to your PC. The Teensy 2.0 connection is a mini-b and you can choose the female connector.
* Spool of colored wire: it is suggested in many guides to use wire with 8 colors 30AWG. Honestly it is very thin and it will break many times while wiring but it is the right size when soldering all of them on the Teensy or MCP.
* M2.5 screws and brass nuts: I didn't find a better solution at the moment than fix the brass nuts in the case holes with some glue.

Soldering iron with a small tip, small tongs/nippers and hot glue are also very useful.

### Keys: switches and keycaps

Switches is easy: just order 68 switches as you like them. I have ordered the classic Cherry MX Brown.

Keycaps is a different story :)

TO BE CONTINUED

## Assembling

## Firmware
