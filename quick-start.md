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

You'll be prompted to provide details about your system. For example, suppose you originally installed your virtual pinball software using the [Baller Installer](https://www.nailbuster.com/wikipinup/doku.php?id=baller\_installer) onto your C: drive (`C:\vPinball`). and you plan to keep your pinball tables collection in the folder `D:\vpinCollection`_,_ then you might answer the prompts as shown in the following session, beginning with defining the virtual pinball Machine where you play your gam tables::

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

As shown, we are adding a machine giving it the name `MyPinball`, its root location, and list of software installed on that machine. The most common virtual pinball software packages are pre-configured for you to choose from a list, including the standard Baller Installation, alternative user interfaces (like [PinballX ](https://www.pinballx.com/)or [PinballY](http://mjrnet.org/pinscape/PinballY.php)), the [Direct Output Framework (DOF)](http://mjrnet.org/pinscape/dll-updates.html#GranderUnifider), and so on. You can change them or add more.&#x20;

{% hint style="info" %}
At this time, to add Software definitions to the configuration you must edit the config file directly using a text editor. See the [PinMan Config File](reference/pinman-config-file.md) documentation for details or contact us for assistance. This will be added to the CLI interactions in the future.
{% endhint %}

Next, you're asked to define one or more Runners. A Runner is simply a list of software names required to run each kind if game you play.&#x20;

```
Runners: set of software needed to run each kind of game you will be playing.
Here is your list of Runners: 
(please double check the software list on each runner).
>  vpx-em
>  vpx-ss
>  fp
>  [Add]
>  OK? Y
```

Lastly, you're asked to define one (or more) Collections by name and location.

```
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

For more information see the [**init** command](reference/cli-reference/init.md) documentation.

## Create a game folder - "build"

Let's create your first game folder. Run the following command, replacing `<gamename>` with the name of the Game folder you want to create.

```
pinman build <ganename>
```

{% hint style="info" %}
The game name here is just a folder name, it does not affect how the table is displayed in your virtual pinball software. If your game name contains spaces or special characters, surround it quotes, such as `"Twilight Zone"`
{% endhint %}

For example, suppose you have a Twilight Zone game, you could run

```
pinman build TwilightZone
```

You'll be prompted to answer questions about the game files, such as:

{% code overflow="wrap" %}
```
Game file name: Twilight Zone (Bally 1993).vpx
Select a runner for this game:
>  vpx-em
>> vpx-ss
ROM name: tz_94ch
DMD name:
Music name prefix:

Done.
Game folder D:\vpinCollection\TwilightZone has been created, with game.manifest.yaml file.
```
{% endcode %}

Because I'm specifying a game that has already been installed (and thus is found in the PinUPSystem database) the command knows it's a solid-state game with a ROM, thus suggests the `vpx-ss` runner and knows the ROM name.&#x20;

A new Game folder is created, containing only the new `game.manifest.yaml` file.&#x20;

For another example, suppose you have an electro-mechanical Big Indian game:

{% code overflow="wrap" %}
```
$ pinman build BigIndian
Game file name: Big Indian.vpx
Select a runner for this game:
>> vpx-em
DMD name:
Music name prefix:

Done.
Game folder D:\vpinCollection\BigIndianhas been created, with game.manifest.yaml file.
```
{% endcode %}

In this case, the command suggests the `vpx-em` runner and does not prompt for a ROM name.

You can now add files downloaded from the Internet (using the **add** command), or **collect** files from a machine that already has this game installed.

## Collect the game files for an installed table - "collect"

Suppose you have already installed the Twlight Zone game in your virtual pinball machine. You can now collect those files into the Game folder we just created, with the **collect** command. For example,

```
pinman collect TwilightZone
```

This will find all the files and data for that game and save copies in the Game folder within your Collection (for example, `D:\vpinCollection\TwilightZone`). The command will output its progress, such as,

```
```

## Next Steps

To install a new pinball table from downloaded files, see the [User Guide: Downloading and installing a VPX table and media](examples-and-guides/downloading-and-installing-a-vpx-table-and-media.md) tutorial.&#x20;

To run these commands without interactive prompts, giving the parameters on the command line, see the [CLI Reference](reference/cli-reference/).

To customize the PinMan configuration for your system and preferences, see the [Config command](reference/cli-reference/config.md), the [PinMan Config File](reference/pinman-config-file.md) documentation, and [User Guide: Customizing PinMan for your system and preferences](examples-and-guides/customizing-pinman-for-your-system-and-preferences.md).&#x20;
