---
description: Overview of the basic design and terminology of PinMan
---

# Core Concepts

Virtual pinball software, as awesome as it is, is actually an assembly of multiple separate software projects cobbled together over many years. One flaw of this ad hoc architecture, in my opinion, is that your data files (pinball tables, table-specific configurations, media, etc.) reside in the same directories as the code that runs them. _Imagine you had to keep all your Word docs in the same folder as the Microsoft Office installation files?_ PinMan is an attempt to solve this problem by letting you maintain a collection of pinball games separate from the machine and software that runs them.

## Key Features: Install and Collect

With PinMan, you have a Machine where your various virtual pinball Software is installed. And you have a Collection of Games, organized as folders each containing the files and data for a specific version of a virtual pinball table.&#x20;

As usual, to run and play a pinball table, all the Game files must be installed on the Machine, distributed into the specific Software directories and data stores as needed. But now, with PinMan, you can more easily automate this process. A master copy of all the stuff associated with a specific table is kept in one place, its Game folder. You can then **Install** those onto a Machine with a single command.

Likewise, you will continue to use your existing virtual pinball software tools to setup and run your games, including screen layouts, PinUP media, game settings, and so on. Then, with PinMan you can use a single command to **collect** everything that may have changed for a given table, saving it back into its Game folder.

<figure><img src=".gitbook/assets/collect-install (1).png" alt=""><figcaption><p>PinMan Install and Collect Commands</p></figcaption></figure>

Below is an example file folder structure of files installed on a machine, and the corresponding files collected into a game folder. This simplified example shows just a few of many files you'd really have for a paritcular pinball table.

<figure><img src=".gitbook/assets/folder files.png" alt=""><figcaption></figcaption></figure>

The arrangement and names of the files can be configured to your needs and liking, especially in the Game folder. In this example, the `Twilight Zone` game folder has a `vpx` subdirectory with the Visual Pinball files, and a separate subdirectory, `vpm`, for the VPinMAME files, including a rom file that is named with the prefix `roms.` for easy readability when perusing your files.

To learn more about the **collect**, **install** and other commands, see the [CLI Reference](reference/cli-reference/) documentation. For tips and tutorials take a look at the [Examples and Guides](broken-reference) pages.

## Problems and Solutions

Some of the problems and complexity of virtual pinball systems that PinMan hopes to address include:

* SEPARATION OF USER DATA. It is common practice to keep application software and user data separate for better organization and accessibility. Virtual pinball generally violates this principle by requiring your game files live in the same directories as the installed software. With PinMan, the master copy of your games is stored in folders separate from the virtual pinball software.
* MANY FILES PER GAME. In virtual pinball, there are many downloads and files per game table, with lots of variation in file types, names, purposes, packaging (e.g. `zip`. `rar`), and versions. Keeping track and managing all the files associated with a specific game is difficult. With PinMan, al the files and data for a game are stored in its own Collection Game folder.
* MULTIPLE SOFTWARES. There are various pinball emulators, media players and other associated software, each with complex setups and unique folder structures that you need to remember and properly care for. With PinMan, your software setup is defined a Config file that knows all this, so you don't have to remember everything.&#x20;
* GAME INSTALLATION. Installing new games can be tedious and error prone. Yet the process is basically the same and repetitive for each game. PinMan knows which files go where. With PinMan, you can first add all the download files for a game to a single Game folder, and then **install** them to a Machine with one command.&#x20;
* GAME VARIATIONS. If you want to try different versions of a game, experiment with configurations, script changes, or try alternative media files, it can be difficult to keep track of what-is-what and what-is-where. With PinMan you can have multiple variants of each table and choose to install or uninstall them as you wish. After making changes on a mahine, you can **collect** all the updates back to your Game folder.
* MULTIPLE MACHINES. Installing the same games to multiple machines requires setting up each individually. There is no way to ensure the machines are consistent in the files and configurations for each game. With PinMan, you can **install** a given Game to multiple machines.
* TROUBLESHOOTING. Existing virtual pinball setups tend to be "brittle", that is, subject to unexpected breakage and problems. Using PinMan to collect all the files and data for a given game into its own Game folder can help with troubleshooting. For example, you can compare changes in a game's configuration on a Machine against a last known working version saved in its Game folder.
* BACKUP AND RECOVERY. Rebuilding a virtual pinball machine after a disk crash or major upgrade requires having a full system backup. And not all data may have been preserved (e.g., Windows registry). It can require hours of restoration work. Also, it is nearly impossible to partially restore some but not all games to a machine. Because PinMan maintains each game and all its data in its own folder, you can more methodically restore a system if necessary.
* PORTABIITY AND SHARING. Some folks keep a mirror image of their vpin files on another computer on their local area network, or an external USB drive, or perhaps just a USB memory stick. With PinMan, this storage can be organized in a way that makes sense to you. Also, with PinMan's **archive** and **import** commands, you can share preconfigured tables (including settings and media) as a zip file with friends and family.

## Reasons to not use PinMan

For all its advantages, there may be reasons to not use PinMan and just stick with the conventional way of managing your virtual pinball tables. For instance,

* "If it ain't broke, don't fix it". If the way you currently do things is working for you, and you're not spending a lot of time managing your games collection, then learning new software like PinMan may just mean extra work without proportional benefits.&#x20;
* Doubles your storage requirements. PinMan at least doubles the storage needed for your pinball files, since there's your games collection in one place, and the running copies of those files installed in the machine. Personally, I like to keep a master copy of my games collection on a separate PC, but you may not feel it's necessary or worth it.
* Sufficient backup/restore procedures. If you've setup regular backups of your system and are OK with doing an all-or-nothing restore should it be necessary, then there may not be as much advantage to the incremental game management provided by PinMan.

## Architecture

PinMan is designed to be extremely flexible and customizable for your specific configurations. Almost everything about the tool is data-driven, controlled through a configuration file that you can change to meet your needs and adapt to future changes to pinball software, machine setup, and new types of games you add to your machine.

It's a good idea to become aware of the different components of PinMan since the vocabulary is used throughout this documentation and in screen messages. But don't worry, you do not necessarily need to know the details to use PinMan.

The following diagram illustrates the organization of PinMan. (Thick arrows indicate one-to-many, thin arrows for one-to-one).&#x20;

<figure><img src=".gitbook/assets/objects-diagram 3.png" alt=""><figcaption><p>Architecture of the PinMan software</p></figcaption></figure>

On the left side of the diagram is a virtual pinball Machine, which has multiple Software projects installed. Each Software manages multiple Item Types (e.g., files and data). For example, Visual Pinball software, may be installed at `C:\vPinball\VisualPinball`, and has Item Types including a VPX file in its `Tables` subdir.

On the right size of the diagram is a Collection of Games. Each Game folder contains the specific files and data Items for the game. For example, its files may include `Twilight Zone (Bally 1993).vpx` table and `tz_94ch.zip` ROM. A Game also has a `game.manifest.yaml` file that identifies the things needed to run the game.&#x20;

The Config file (`pinman.config.yaml`) describes your setup, including the Machine(s) and Software you have.

Here are some useful definitions:&#x20;

* MACHINE - a virtual pinball system where you play your game tables. Can be a physical pinball cabinet, or a Windows desktop. Machines are identified by a unique name and a root folder or network identifier. A Machine is configured with a list of its installed software. PinMan allows you to manage more than one Machine for your Collection.
* SOFTWARE - references a software project used on a virtual pinball machine and required to play a pinball table. A machine will have multiple Software installed. We're only concerned with software that has table-specific data. Each Software is configured with a list of Item Types it manages.
* ITEM TYPE - a table-specific data item managed by Software on a Machine. There are many different kinds of Item Types, including files, INI data, XMLdata, Windows registry data, SQLite database records, whole directories and more. Parameters of each ItemType are defined in the Config file. For example, for a VisualPinball game, there will be a `.vpx` file Item Type.
* CONFIG FILE - the config file defines the Machines, Runners, Software, and ItemTypes managed by PinMan, along with other settings. A default Config file (`pinman.config.yaml`) comes built-in to PinMan that covers many common virtual pinball installations, including that from BallerInstaller. As a YAML format text file, it is easily edited and updated to suit your needs.
* RUNNER - a list of Software required by a game to run on a machine. For example, you may have a Runner named `vpx-ss` that includes Visual Pinball, VPinMAME, PinUPSystem, and PinballY, and a separate Runner `fp` that includes the Future Pinball software instead.
* COLLECTION - a directory containing your Game folders.&#x20;
* GAME - a sub-directory under a Collection that contains the files and other data required to configure and play a game. Each Game folder must contain a Manifest file that defines properties of the game and its data/files.
* ITEM - a piece of data required by virtual pinball Software for a specific table (correlated to a Software ItemType). For example, the "Twilight Zone" VisualPinball game, may have the `Twilight Zone (Bally 1993).vpx` file. In addition to files, PinMan  also collects and installs table-specific data extracted from, for example, `DmdDevice.ini`, `B2STableSettings.xml`, and `PUPDatabase.db` files. All of these data are saved in the Game's folder.&#x20;
* MANIFEST FILE - each Game folder has a Manifest file that defines properties of the game and its data/files. It is a YAML-format text file named `game.manifest.yaml`. The Manifest defines which Runner the game uses, the Base file name (e.g. `Twilight Zone (Bally 1993)`), and other files and data Items that are part of the game (e.g the ROM name `tz_94ch`). PinMan provides tools to help automate building and updating the Manifest file, although it can also be edited directly with a text editor.&#x20;

This architecture help make PinMan extremely flexible and adaptable for managing your virtual pinball data.&#x20;
