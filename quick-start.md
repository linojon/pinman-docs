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

You'll be prompted to provide details about your system. For example, suppose you originally installed your virtual pinball software using the [Baller Installer](https://www.nailbuster.com/wikipinup/doku.php?id=baller\_installer) onto your C: drive (_C:\vPinball_). and you plan to keep your pinball tables collection in the folder _D:\vpinCollection,_ then you might answer the prompts as shown in the following session, beginning with defining the virtual pinball Machine where you play your gam tables::

{% code overflow="wrap" %}
```shell-session
Machines: a virtual pinball system where you play your game tables
Here is your list of Machines:
>> [Add]
>  OK?
Add Machine:
Machine name: MyPinball
Based on a template?
>> Baller
>  No template
Machine root location: C:\vPinball
Software on machine MyPinball:
>  dof: n/a
>  futurepinball: C:\vPinball\FuturePinball
>  pinupsystem: C:\vPinball\PinUPSystem
>  pinballX: n/a
>  pinballY: n/a
>  pinVol: n/a
>  visualpinball: C:\vPinball\VisualPinball
>  vpinmame: C:\vPinball\VisualPinball\VPinMAME
>  [Add]
>  OK? Y

Machines:
Here is your list of Machines:
>  MyPinball
>  [Add]
>  OK? Y
```
{% endcode %}

First, you're asked to define one (or more) Machines with a name, root location, and list of software installed on that machine. The most common virtual pinball software packages are pre-configured for you to choose from a list, including the standard Baller Installation. But you can change them or add more.&#x20;

If you have additional software packages on the machine, such as an alternative UI (like [PinballX ](https://www.pinballx.com/)or [PinballY](http://mjrnet.org/pinscape/PinballY.php)), [Direct Output Framework (DOF)](http://mjrnet.org/pinscape/dll-updates.html#GranderUnifider), and so on, please add these when prompted. For example,

```
Add a software to this machine
>> Direct Output Framework (DOF)
>  PinballX
>  PinballY
>  PinVol
>  [Add]
Direct Output Framework (DOF) root directory: D:\DirectOutput
Add a software to this machine? N
```

Next, you're asked to define one or more Runners that's simply a list of software names required to run each kind if game you play. Then you're asked to define one (or more) Collections by name and location.

```
Runners: set of software needed to run each kind of game you will be playing.
Here is your list of Runners: 
(please double check the software list on each runner).
>  vpx-em
>  vpx-ss
>  fp
>  [Add]
>  OK? Y

Collections: a directory containing your Game folders
Here is your list of collections
>> [Add]
>  OK?
Add Collection:
Collection name: vpinCollection
Collection root location: D:\vpinCollection
Collections:
>  vpinCollection: D:\vpinCollection
> [Add]
> OK? Y

Done.
PinMan default config file is located at: %APPDATA%\PinMan\pinman.config.yaml
You can modify this file using the "pinman config" coommand, 
or edit it in a text editor by running "pinman config --edit"
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



