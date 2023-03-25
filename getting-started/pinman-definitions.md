---
description: Overview of the basic design and terminology of PinMan
---

# PinMan Definitions

PinMan is designed to be extremely flexible and customizable for your specific configurations. Almost everything about the tool is data-driven, controlled through a configuration file that you can change to meet your needs and adapt to future changes to pinball software, machine setup, and new types of games you add to your machine.

It's a good idea to become aware of the different components of PinMan since the vocabulary is used throughout this documentation and in screen messages. But don't worry, you do not necessarily need to know the details to use PinMan.

The following diagram illustrates the organization of PinMan. (Thick arrows indicate one-to-many, thin arrows for one-to-one).&#x20;

<figure><img src="../.gitbook/assets/objects-diagram 3.png" alt=""><figcaption><p>Architecture of the PinMan software</p></figcaption></figure>

On the left side of the diagram is a virtual pinball Machine, which has multiple Software projects installed. Each Software manages multiple Item Types (e.g., files and data). For example, Visual Pinball software, may be installed at `C:\vPinball\VisualPinball`, and has Item Types including a VPX file in its `Tables` subdir.

On the right size of the diagram is a Collection of Games. Each Game folder contains the specific files and data Items for the game. For example, its files may include `Twilight Zone (Bally 1993).vpx` table and `tz_94ch.zip` ROM. A Game also has a `game.manifest.yaml` file that identifies the things needed to run the game.&#x20;

The Config file (`pinman.config.yaml`) describes your setup, including the Machine(s) and Software you have.

Here are some useful definitions:&#x20;

* MACHINE - a virtual pinball system where you play your game tables. Can be a physical pinball cabinet, a Windows desktop, or VR platform. Machines are identified by a unique name and a root folder or network identifier. A Machine is configured with a list of its installed software. PinMan allows you to manage more than one Machine for your Collection.
* SOFTWARE - references a software project used on a virtual pinball machine and required to play a pinball table. A machine will have multiple Software installed. We're only concerned with software that has table-specific data. Each Software is configured with a list of Item Types it manages.
* ITEM TYPE - a table-specific data item managed by Software on a Machine. There are many different kinds of Item Types, including files, INI data, XMLdata, Windows registry data, SQLite database records, whole directories and more. Parameters of each ItemType are defined in the Config file. For example, for a VisualPinball game, there will be a `.vpx` file Item Type.
* CONFIG FILE - the config file defines the Machines, Runners, Software, and ItemTypes managed by PinMan, along with other settings. A default Config file (`pinman.config.yaml`) comes built-in to PinMan that covers many common virtual pinball installations, including that from BallerInstaller. As a YAML format text file, it is easily edited and updated to suit your needs.
* RUNNER - a list of Software required by a game to run on a machine. For example, you may have a Runner named `vpx-ss` that includes Visual Pinball, VPinMAME, PinUPSystem, and PinballY, and a separate Runner `fp` that includes the Future Pinball software instead.
* COLLECTION - a directory containing your Game folders.&#x20;
* GAME - a sub-directory under a Collection that contains the files and other data required to configure and play a game. Each Game folder must contain a Manifest file that defines properties of the game and its data/files.
* ITEM - a piece of data required by virtual pinball Software for a specific table (correlated to a Software ItemType). For example, the "Twilight Zone" VisualPinball game, may have the `Twilight Zone (Bally 1993).vpx` file. In addition to files, PinMan  also collects and installs table-specific data extracted from, for example, `DmdDevice.ini`, `B2STableSettings.xml`, and `PUPDatabase.db` files. All of these data are saved in the Game's folder.&#x20;
* MANIFEST FILE - each Game folder has a Manifest file that defines properties of the game and its data/files. It is a YAML-format text file named `game.manifest.yaml`. The Manifest defines which Runner the game uses, the Base file name (e.g. `Twilight Zone (Bally 1993)`), and other files and data Items that are part of the game (e.g the ROM name `tz_94ch`). PinMan provides tools to help automate building and updating the Manifest file, although it can also be edited directly with a text editor.&#x20;

This architecture help make PinMan extremely flexible and adaptable for managing your virtual pinball data.&#x20;
