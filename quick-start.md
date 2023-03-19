---
description: How to install and setup PinMan
---

# Quick Start

## Download and run the installer

TBD

TBD



## Initialize PinMan configuration -"init"

After installation, open a Terminal window and initialize the PinMan configuration by running the following command:

```
pinman init
```

You'll be prompted to provide details about your system. For example, suppose you originally installed your virtual pinball software using the [Baller Installer](https://www.nailbuster.com/wikipinup/doku.php?id=baller\_installer) onto your C: drive (_C:\vPinball_). and you plan to keep your pinball tables collection in the folder _D:\vpinCollection, then you might answer the prompts as follows_:

```shell-session
Define Machine:
Machine name: MyPinball
Based on a template?
>> Baller
>  [Add]
Machine root directory: C:\vPinball
Add a software to this machine? N
Add another machine? N

Define Collection:
Collection name: vpinCollection
Collection root directory: D:\vpinCollection
Add another collection? N

PinMan default config file is located at: %APPDATA%\PinMan\pinman.config.yaml
You can modify this file using the "pinman config" coommand, 
or edit it in a text editor by running "pinman config --edit"
Done.
```

If you have additional software packages on the machine, such as an alternative UI (like [PinballX ](https://www.pinballx.com/)or [PinballY](http://mjrnet.org/pinscape/PinballY.php)), [Direct Output Framework (DOF)](http://mjrnet.org/pinscape/dll-updates.html#GranderUnifider), and so on, please add these when prompted. For example,

```
Add a software to this machine? Y
>> Direct Output Framework (DOF)
>  PinballX
>  PinballY
>  PinVol
>  [Add]
Direct Output Framework (DOF) root directory: D:\DirectOutput
Add a software to this machine? N
```

For more information see the [init command](reference/cli-reference/init.md) documentation.

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



