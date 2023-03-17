---
description: Basic concepts and terminology
---

# Concepts

Virtual pinball software, as awesome as it is, is actually an assembly of multiple separate software projects cobbled together over many years. One flaw of this ad hoc architecture, in my opinion, is that your data files (pinball tables, table-specific configurations, media, etc.) reside in the same directories as the code that runs them. _Imagine you had to keep all your Word docs in the same folder as the Microsoft Office installation files?_ PinMan is an attempt to solve this problem by letting you maintain a collection of pinball games separate from the machine and software that runs them.

### Features

PinMan is designed to be extremely flexible and customizable for your specific configurations. Almost everything about the tools is data-driven, controlled through a configuration file (pinman.config.yaml) that you can change to meet your needs and adapt to future changes, including software updates and new projects you add to your machine.

### Architecture

The following diagram illustrates the architecture of PinMan:

<figure><img src=".gitbook/assets/objects-diagram.png" alt=""><figcaption><p>Architecture of the PinMan software</p></figcaption></figure>

With PinMan, you have a Machine where your various virtual pinball Software is installed. And you have a Collection of Game folders, each containing the files and data (Items) for a specific version of a pinball table.&#x20;

As usual, to run and play a table all the Game files must be installed on the Machine, distributed into the specific Software directories and data stores as needed. But now, with PinMan, you can more easily automate this process. All the stuff associated with a specific table is kept in one place, its Game folder. Those can then be Installed onto the Machine Software with a single command.

Likewise, you will continue to use the existing vpin tools to configure your setup, including screen layouts, PinUP media, game settings, and so on. Then, with PinMan you can use a single command to Collect all the files and settings that may have changed for a given table back into its Collection Game folder.

### Definitions

The following objects are configured and managed by PinMan, making it extremely flexible and adaptable for managing virutla pinball data. Please refer to the preceding "Architecture" diagram.

* MACHINE - a virtual pinball system where you play your game tables. Can be a physical pinball cabinet, or a Windows desktop. Machines are identified by a unique name and a root folder or network identifier. A Machine is configured with a list of its installed software. PinMan allows you to manage more than one Machine for your Collection.
* SOFTWARE - a software project used on a virtual pinball machine and required to play a pinball table. A machine will have multiple software installed. We're only concerned with software that has table-specific data. Each software project is configured with a list of item types it manages.
* ITEM TYPE - a table-specific data item managed by Software on a Machine. The are many different item types, including files, ini data, xml data, registry data, SQLite database records, whole directories and more. Parameters of each ItemType are defined in the config file.
* CONFIG FILE - the config file defines the Machines, Runners, Software, and ItemTypes managed by PinMan, and other settings. A default config file (pinman.config.yaml) comes built-in to PinMan that covers many common virtual pinball installations (including one using BallerInstaller). As a YAML format text file, it is easily edited and updated to suit your needs.
* RUNNER - a list of Software required by a game table to run on a machine. For example, you may have a Runner named "VPX-EM" that includes Visual Pinball, PinUPSystem, and PinballY, and a separate Runner "VPX-SS" that adds VpinMAME for ROM-based VPX tables.
* COLLECTION - a directory containing your Game folders.&#x20;
* GAME - a sub-directory under a Collection that contains the files and other data Items required to configure and play a game. Each Game folder must contain a Manifest file that identifies the Items for the paritcular game.
* ITEM - a piece of data required by vpin Software for a specific table. For VisualPinball, Items include the .vpx and maybe .directb2s and rom.zip files. PinMan can also collect and install table-specific data, for instance, from the DmdDevice.ini, B2STableSettings.xml, and PUPDatabase.db files saved in the Game folder.&#x20;
* MANIFEST FILE - each Game folder has a Manifest file that defines properties of the game needed to Collect from and Install to a machine. It is a YAML-format text file named game.manifest.yaml. The Manifest defines which Runner the game uses, the Base file name (e.g. "Twilight Zone (Bally 1993)"), and other files and data Items that are part of the game (e.g the ROM name " tz\_94ch"). PinMan provides tools to help automate building and updating the Manifest file, although it can also be edited directly with a text editor.&#x20;





