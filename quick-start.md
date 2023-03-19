---
description: How to install and setup PinMan
---

# Quick Start

## Download and run the installer

TBD

TBD

## Initialize PinMan -"init"

In a terminal window, run the following command

```
pinman init
```

You'll be prompted to provide details about your system. For example, suppose you originally installed your virtual pinball software using the [Baller Installer](https://www.nailbuster.com/wikipinup/doku.php?id=baller\_installer), installed onto your C: drive. And you plan to keep your pinball tables collection in the folder D:\vpinCollection:

```
```

## Build a game folder - "build"

Let's create your first game folder. Run the following command, replacing \<gamename> with the name of the Game folder you want to create.

```
pinman build <ganename>
```

{% hint style="info" %}
The game name here is just a folder name, it does not affect how the table is displayed in your virtual pinball software.&#x20;
{% endhint %}

For example, suppose you have a Twilight Zone game, you could run

```
pinman build TwilightZone
```

You'll be prompted to answer questions about the game files, such as:

```
```

{% hint style="info" %}
If your game name contains spaces or special characters, surround it quotes, such as "Twilight Zone"
{% endhint %}

## Collect the game files for an installed table - "collect"

Suppose you have already installed a game in your virtual pinball software before using PinMan. You can now collect those files into the Game folder with the collect command. For example,

```
pinman collect TwilightZone
```

This will find all the files and data for that game and save copies in the Game folder within your Collection (for example, D:\vpinCollection\TwilightZone\\). The command will output its progress, such as,

```
```

## Next Steps

To install a new pinball table from downloaded files, see the [User Guide - First time download and install a VPX table and Popper](user-guides/usage-scenarios/first-time-download-and-install-a-vpx-table-and-popper-media.md) media tutorial.&#x20;

To run commands without interactive prompts, giving the parameters on the command line, see the [CLI Reference](reference/cli-reference/).

To customize the PinMan configuration for your system and preferences, see the [Config command](reference/cli-reference/config.md) and/or the [PinMan Config File](reference/pinman-config-file.md) documentation.&#x20;



