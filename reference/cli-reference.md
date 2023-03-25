# CLI Reference

## Usage

```sh-session
$ npm install -g pinman
$ pinman COMMAND
running command...
$ pinman (--version)
pinman/0.1.0 win32-x64 node-v16.17.0
$ pinman --help [COMMAND]
USAGE
  $ pinman COMMAND
...
```

## Commands

* `pinman build [GAME]`
* `pinman collect [GAME]`
* `pinman config`
* `pinman help [COMMANDS]`
* `pinman install [GAME]`

### `pinman build [GAME]`

Create or modify a game folder manifest

```
USAGE
  $ pinman build [GAME] [--protect | --interact | --force] [-p] [-C <value>] [-D <value>] [-m <value>] [-c
    <value>] [--intro] [--debug | --verbose | --brief | --quiet] [--testing] [--base <value>] [--runner <value>] [--rom
    <value>] [--dmd <value>] [--musicprefix <value>]

ARGUMENTS
  GAME  Game directory

FLAGS
  --base=<value>         Game file base <name> (with or without ext)
  --dmd=<value>          DMD prefix <name> (e.g. {name}.UltraDMD/ directory)
  --musicprefix=<value>  Music file name prefix <name> (only for VPX Music/ files)
  --rom=<value>          ROM file base <name>
  --runner=<value>       Use runner <name>

ENVIRONMENT FLAGS
  -C, --config=<value>      Use configuration file
  -D, --defaults=<value>    Use defaults configuration file
  -c, --collection=<value>  Use collection library <name>
  -m, --machine=<value>     Use target machine <name>

UI FLAGS
  -p, --dryrun     Report what will happen but dont do it
  --force          Force overwrite and changes
  --[no-]interact  Run command in interactive mode
  --protect        Never overwrite files or settings

LOGGING FLAGS
  --brief       Show minimal details only
  --debug       Show debug logs (aka log-level=debug)
  --[no-]intro  Show intro banner
  --quiet       Suppress all output except errors
  --testing     Console output for testing
  --verbose     Show progress details (default)

DESCRIPTION
  Create or modify a game folder manifest

EXAMPLES
  $ pinman build
```

_See code:_ [_dist/commands/build.ts_](https://github.com/linojon/pinman/blob/v0.1.0/dist/commands/build.ts)

### `pinman collect [GAME]`

Copy files from a machine to a table folder

```
USAGE
  $ pinman collect [GAME] [--protect | --interact | --force] [-p] [-C <value>] [-D <value>] [-m <value>] [-c
    <value>] [--intro] [--debug | --verbose | --brief | --quiet] [--testing] [--newer]

ARGUMENTS
  GAME  Game directory

FLAGS
  --[no-]newer  Allow overwrite newer items with older ones (default: --no-newer will protect newer items)

ENVIRONMENT FLAGS
  -C, --config=<value>      Use configuration file
  -D, --defaults=<value>    Use defaults configuration file
  -c, --collection=<value>  Use collection library <name>
  -m, --machine=<value>     Use target machine <name>

UI FLAGS
  -p, --dryrun     Report what will happen but dont do it
  --force          Force overwrite and changes
  --[no-]interact  Run command in interactive mode
  --protect        Never overwrite files or settings

LOGGING FLAGS
  --brief       Show minimal details only
  --debug       Show debug logs (aka log-level=debug)
  --[no-]intro  Show intro banner
  --quiet       Suppress all output except errors
  --testing     Console output for testing
  --verbose     Show progress details (default)

DESCRIPTION
  Copy files from a machine to a table folder

EXAMPLES
  $ pinman collect
```

_See code:_ [_dist/commands/collect.ts_](https://github.com/linojon/pinman/blob/v0.1.0/dist/commands/collect.ts)

### `pinman config`

Configuration settings

```
USAGE
  $ pinman config [--protect | --interact | --force] [-p] [-C <value>] [-D <value>] [-m <value>] [-c
    <value>] [--intro] [--debug | --verbose | --brief | --quiet] [--testing] [--dump] [--edit]

FLAGS
  --dump  Print all configuration settings to console (comments removed)
  --edit  Open the current configuration file in editor

ENVIRONMENT FLAGS
  -C, --config=<value>      Use configuration file
  -D, --defaults=<value>    Use defaults configuration file
  -c, --collection=<value>  Use collection library <name>
  -m, --machine=<value>     Use target machine <name>

UI FLAGS
  -p, --dryrun     Report what will happen but dont do it
  --force          Force overwrite and changes
  --[no-]interact  Run command in interactive mode
  --protect        Never overwrite files or settings

LOGGING FLAGS
  --brief       Show minimal details only
  --debug       Show debug logs (aka log-level=debug)
  --[no-]intro  Show intro banner
  --quiet       Suppress all output except errors
  --testing     Console output for testing
  --verbose     Show progress details (default)

DESCRIPTION
  Configuration settings

EXAMPLES
  $ pinman config
```

_See code:_ [_dist/commands/config.ts_](https://github.com/linojon/pinman/blob/v0.1.0/dist/commands/config.ts)

### `pinman help [COMMANDS]`

Display help for pinman.

```
USAGE
  $ pinman help [COMMANDS] [-n]

ARGUMENTS
  COMMANDS  Command to show help for.

FLAGS
  -n, --nested-commands  Include all nested commands in the output.

DESCRIPTION
  Display help for pinman.
```

_See code:_ [_@oclif/plugin-help_](https://github.com/oclif/plugin-help/blob/v5.2.8/src/commands/help.ts)

### `pinman install [GAME]`

Install a game to a machine

```
USAGE
  $ pinman install [GAME] [--protect | --interact | --force] [-p] [-C <value>] [-D <value>] [-m <value>] [-c
    <value>] [--intro] [--debug | --verbose | --brief | --quiet] [--testing] [--newer]

ARGUMENTS
  GAME  Game directory

FLAGS
  --[no-]newer  Allow overwrite newer items with older ones (default: --no-newer will protect newer items)

ENVIRONMENT FLAGS
  -C, --config=<value>      Use configuration file
  -D, --defaults=<value>    Use defaults configuration file
  -c, --collection=<value>  Use collection library <name>
  -m, --machine=<value>     Use target machine <name>

UI FLAGS
  -p, --dryrun     Report what will happen but dont do it
  --force          Force overwrite and changes
  --[no-]interact  Run command in interactive mode
  --protect        Never overwrite files or settings

LOGGING FLAGS
  --brief       Show minimal details only
  --debug       Show debug logs (aka log-level=debug)
  --[no-]intro  Show intro banner
  --quiet       Suppress all output except errors
  --testing     Console output for testing
  --verbose     Show progress details (default)

DESCRIPTION
  Install a game to a machine

EXAMPLES
  $ pinman install
```

_See code:_ [_dist/commands/install.ts_](https://github.com/linojon/pinman/blob/v0.1.0/dist/commands/install.ts)

* `pinman build [GAME]`
* `pinman collect [GAME]`
* `pinman config`
* `pinman help [COMMANDS]`
* `pinman install [GAME]`

### `pinman build [GAME]`

Create or modify a game folder manifest

```
USAGE
  $ pinman build [GAME] [--protect | --interact | --force] [-p] [-C <value>] [-D <value>] [-m <value>] [-c
    <value>] [--intro] [--debug | --verbose | --brief | --quiet] [--testing] [--base <value>] [--runner <value>] [--rom
    <value>] [--dmd <value>] [--musicprefix <value>]

ARGUMENTS
  GAME  Game directory

FLAGS
  --base=<value>         Game file base <name> (with or without ext)
  --dmd=<value>          DMD prefix <name> (e.g. {name}.UltraDMD/ directory)
  --musicprefix=<value>  Music file name prefix <name> (only for VPX Music/ files)
  --rom=<value>          ROM file base <name>
  --runner=<value>       Use runner <name>

ENVIRONMENT FLAGS
  -C, --config=<value>      Use configuration file
  -D, --defaults=<value>    Use defaults configuration file
  -c, --collection=<value>  Use collection library <name>
  -m, --machine=<value>     Use target machine <name>

UI FLAGS
  -p, --dryrun     Report what will happen but dont do it
  --force          Force overwrite and changes
  --[no-]interact  Run command in interactive mode
  --protect        Never overwrite files or settings

LOGGING FLAGS
  --brief       Show minimal details only
  --debug       Show debug logs (aka log-level=debug)
  --[no-]intro  Show intro banner
  --quiet       Suppress all output except errors
  --testing     Console output for testing
  --verbose     Show progress details (default)

DESCRIPTION
  Create or modify a game folder manifest

EXAMPLES
  $ pinman build
```

_See code:_ [_dist/commands/build.ts_](https://github.com/linojon/pinman/blob/v0.1.0/dist/commands/build.ts)

### `pinman collect [GAME]`

Copy files from a machine to a table folder

```
USAGE
  $ pinman collect [GAME] [--protect | --interact | --force] [-p] [-C <value>] [-D <value>] [-m <value>] [-c
    <value>] [--intro] [--debug | --verbose | --brief | --quiet] [--testing] [--newer]

ARGUMENTS
  GAME  Game directory

FLAGS
  --[no-]newer  Allow overwrite newer items with older ones (default: --no-newer will protect newer items)

ENVIRONMENT FLAGS
  -C, --config=<value>      Use configuration file
  -D, --defaults=<value>    Use defaults configuration file
  -c, --collection=<value>  Use collection library <name>
  -m, --machine=<value>     Use target machine <name>

UI FLAGS
  -p, --dryrun     Report what will happen but dont do it
  --force          Force overwrite and changes
  --[no-]interact  Run command in interactive mode
  --protect        Never overwrite files or settings

LOGGING FLAGS
  --brief       Show minimal details only
  --debug       Show debug logs (aka log-level=debug)
  --[no-]intro  Show intro banner
  --quiet       Suppress all output except errors
  --testing     Console output for testing
  --verbose     Show progress details (default)

DESCRIPTION
  Copy files from a machine to a table folder

EXAMPLES
  $ pinman collect
```

_See code:_ [_dist/commands/collect.ts_](https://github.com/linojon/pinman/blob/v0.1.0/dist/commands/collect.ts)

### `pinman config`

Configuration settings

```
USAGE
  $ pinman config [--protect | --interact | --force] [-p] [-C <value>] [-D <value>] [-m <value>] [-c
    <value>] [--intro] [--debug | --verbose | --brief | --quiet] [--testing] [--dump] [--edit]

FLAGS
  --dump  Print all configuration settings to console (comments removed)
  --edit  Open the current configuration file in editor

ENVIRONMENT FLAGS
  -C, --config=<value>      Use configuration file
  -D, --defaults=<value>    Use defaults configuration file
  -c, --collection=<value>  Use collection library <name>
  -m, --machine=<value>     Use target machine <name>

UI FLAGS
  -p, --dryrun     Report what will happen but dont do it
  --force          Force overwrite and changes
  --[no-]interact  Run command in interactive mode
  --protect        Never overwrite files or settings

LOGGING FLAGS
  --brief       Show minimal details only
  --debug       Show debug logs (aka log-level=debug)
  --[no-]intro  Show intro banner
  --quiet       Suppress all output except errors
  --testing     Console output for testing
  --verbose     Show progress details (default)

DESCRIPTION
  Configuration settings

EXAMPLES
  $ pinman config
```

_See code:_ [_dist/commands/config.ts_](https://github.com/linojon/pinman/blob/v0.1.0/dist/commands/config.ts)

### `pinman help [COMMANDS]`

Display help for pinman.

```
USAGE
  $ pinman help [COMMANDS] [-n]

ARGUMENTS
  COMMANDS  Command to show help for.

FLAGS
  -n, --nested-commands  Include all nested commands in the output.

DESCRIPTION
  Display help for pinman.
```

_See code:_ [_@oclif/plugin-help_](https://github.com/oclif/plugin-help/blob/v5.2.8/src/commands/help.ts)

### `pinman install [GAME]`

Install a game to a machine

```
USAGE
  $ pinman install [GAME] [--protect | --interact | --force] [-p] [-C <value>] [-D <value>] [-m <value>] [-c
    <value>] [--intro] [--debug | --verbose | --brief | --quiet] [--testing] [--newer]

ARGUMENTS
  GAME  Game directory

FLAGS
  --[no-]newer  Allow overwrite newer items with older ones (default: --no-newer will protect newer items)

ENVIRONMENT FLAGS
  -C, --config=<value>      Use configuration file
  -D, --defaults=<value>    Use defaults configuration file
  -c, --collection=<value>  Use collection library <name>
  -m, --machine=<value>     Use target machine <name>

UI FLAGS
  -p, --dryrun     Report what will happen but dont do it
  --force          Force overwrite and changes
  --[no-]interact  Run command in interactive mode
  --protect        Never overwrite files or settings

LOGGING FLAGS
  --brief       Show minimal details only
  --debug       Show debug logs (aka log-level=debug)
  --[no-]intro  Show intro banner
  --quiet       Suppress all output except errors
  --testing     Console output for testing
  --verbose     Show progress details (default)

DESCRIPTION
  Install a game to a machine

EXAMPLES
  $ pinman install
```

_See code:_ [_dist/commands/install.ts_](https://github.com/linojon/pinman/blob/v0.1.0/dist/commands/install.ts)
