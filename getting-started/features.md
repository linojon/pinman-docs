# Features

## Key Features: Install and Collect

With PinMan, you have a Machine where your various virtual pinball Software is installed. And you have a Collection of Games, organized as folders each containing the files and data for a specific version of a virtual pinball table.&#x20;

As usual, to run and play a pinball table, all the Game files must be installed on the Machine, distributed into the specific Software directories and data stores as needed. But now, with PinMan, you can more easily automate this process. A master copy of all the stuff associated with a specific table is kept in one place, its Game folder. You can then **Install** those onto a Machine with a single command.

Likewise, you will continue to use your existing virtual pinball software tools to setup and run your games, including screen layouts, PinUP media, game settings, and so on. Then, with PinMan you can use a single command to **collect** everything that may have changed for a given table, saving it back into its Game folder.

<figure><img src="../.gitbook/assets/collect-install (1).png" alt=""><figcaption><p>PinMan Install and Collect Commands</p></figcaption></figure>

Below is an example file folder structure of files installed on a machine, and the corresponding files collected into a game folder. This simplified example shows just a few of many files you'd really have for a paritcular pinball table.

<figure><img src="../.gitbook/assets/folder files (1).png" alt=""><figcaption></figcaption></figure>

The arrangement and names of the files can be configured to your needs and liking, especially in the Game folder. In this example, the `Twilight Zone` game folder has a `vpx` subdirectory with the Visual Pinball files, and a separate subdirectory, `vpm`, for the VPinMAME files, including a rom file that is named with the prefix `roms.` for easy readability when perusing your files.

To learn more about the **collect**, **install** and other commands, see the [CLI Reference](../reference/cli-reference.md) documentation. For tips and tutorials take a look at the [Examples and Guides](broken-reference) pages.

## Why use PinMan? Problems and Solutions

Some of the problems and complexity of virtual pinball systems that PinMan hopes to address include:

* SEPARATION OF DATA. It is common practice to keep application software and user data separate for better organization and accessibility. Virtual pinball generally violates this principle by requiring your game files live in the same directories as the installed software. With PinMan, the master copy of your games is stored in folders separate from the virtual pinball software.
* MANY FILES PER GAME. In virtual pinball, there are many downloads and files per game table, with lots of variation in file types, names, purposes, packaging (e.g. `zip`. `rar`), and versions. Keeping track and managing all the files associated with a specific game is difficult. With PinMan, all of the files and data for a game are stored together in its own collection game folder.
* COMPLEXITY. There are various pinball emulators, media players and other associated software, each with complex setups and unique folder structures that you need to remember and properly care for. With PinMan, your software setup is defined in one configuration file that knows all this, so you don't have to remember everything.&#x20;
* GAME INSTALLATION. Installing new games can be tedious and error prone. Yet the process is basically the same and repetitive for each game. PinMan knows which files go where. With PinMan, you can first add all the downloaded files for a game to its own game folder, and then **install** them to a machine with one command.&#x20;
* GAME VARIATIONS. If you want to try different versions of a game, experiment with configurations, script changes, or try alternative media files, it can be difficult to keep track of what-is-what and what-is-where. With PinMan you can **clone** games, making multiple variants of each table and choose to **install** or **uninstall** them as you wish.
* MULTIPLE MACHINES. Installing the same games to multiple machines requires setting up each individually. There has been no easy way to ensure the machines are consistent in the files and configurations for each game. With PinMan, you can **install** a given game to multiple machines, including desktops, physical vpin cabinets, or VR, from a single master collection.
* TROUBLESHOOTING. Existing virtual pinball setups tend to be "brittle", that is, subject to unexpected breakage and problems. Using PinMan to collect all the files and data for a given game into its own Game folder can help with troubleshooting. For example, you can **compare** changes in a game's configuration on a machine against a last known working version saved in its game folder to help diagnose issues.
* BACKUP AND RECOVERY. Rebuilding a virtual pinball machine after a disk crash or major upgrade requires having a full system backup. And not all data may have been preserved (e.g., Windows registry). It can require hours of restoration work. Also, it is nearly impossible to partially restore some but not all games to a machine. Because PinMan maintains each game and all its data in its own folder, you can more methodically restore a system if necessary.
* ORGANANIZING YOUR COLLECTION. Some folks keep a mirror image of their vpin files on another computer on their local area network, or an external USB drive, or perhaps just a USB memory stick. With PinMan, this storage can be organized in a way that makes sense to you rather than that dictated by the software.&#x20;
* SHARING GAMES. With PinMan's **archive** and **import** commands, you can package preconfigured tables (including settings and media) as a zip file to share with friends and family on their own pinball setups.

## Reasons to not use PinMan

For all its advantages, there may be reasons to not use PinMan and just stick with the conventional way of managing your virtual pinball tables. For instance,

* Leave well enough alone. If the way you currently do things is working for you, and you're not spending a lot of time managing your games collection, then learning new software like PinMan may just mean extra work without proportional benefits.&#x20;
* Doubles your storage requirements. PinMan doubles the storage needed for your pinball files, since there's your games collection in one place, and the running copies of those same files installed in the machine. Personally, I like to keep a master copy of my games collection on a separate PC, but you may not feel it's necessary or worth it.
* Backups are good enough. If you're primarily interested in PinMan for backups, and you've setup regular backups of your system, and are OK with doing an all-or-nothing restore (should it be necessary), then there may not be as much advantage to the incremental game management provided by PinMan.
