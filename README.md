---
description: 'PinMan: Virtual Pinball Table File Manager'
---

# Introduction

<figure><img src=".gitbook/assets/asciiart-white (1).png" alt=""><figcaption></figcaption></figure>

## What is PinMan?

PinMan is virtual pinball table tool that lets you keep your collection of pinball games, including all their files, media, and settings, separate from the software that runs them.

Using PinMan, you can more easily install new games, maintain different versions of a table, perform backups and restores, distribute games to multiple machine, help with troubleshooting, and more.

Currently, PinMan is run as a command-line interface (CLI) from a terminal window. A desktop graphical interface (GUI) is planned.

## Requirements

TBD

## Quickstart

First you'll use the **init** command to initialize PinMan, for example, for a standard Baller-Installer system:

```
$ pinman init --variant=baller --root=C:\vPinball --collection=D:\MyCollection
```

Now, for example, suppose you want to collect all the current files, media, and settings for a game already installed on your vpin machine. The following **build** and **collect** commands gather the Leprechaun King files into its own folder named "Leprechaun" in your D:\MyCollection folder:

```
$ pinman build Leprechaun --table="Leprechaun King (Orbital 2020).vpx"
$ pinman collect Leprechaun
   visualpinball
✔  - vpx           Copied          Tables/Leprechaun King (Orbital 2020).vpx 
✔  - ultradmd      Copied          Tables/leprechaun.UltraDMD 
✔  Done:           2 items collected
```

In the following example, suppose we've downloaded the files we want for the Twilight Zone game into its own game folder. You can **install** the game to your vpin machine with one command:&#x20;

```
$ pinman install TwilightZone
   visualpinball
✔  - vpx           Copied          vpx/Twilight Zone (Bally 1993).vpx 
✔  - directb2s     Copied          vpx/Twilight Zone (Bally 1993).directb2s 
   vpinmame
✔  - rom           Copied          vpm/tz_94ch.zip 
✔  Done:           3 items installed 
```

This just scratches the surface of how you can use PinMan.
