# Subcommand reference

All uses of `noted` require a subcommand. If one is not supplied, the default `create` subcommand is assumed. The subcommands are as follows.

## Contents

* [List of Subcommands](#list-of-subcommands)
    + [config](#config)
        - [Synopsis](#synopsis)
        - [Overview](#overview)
        - [Arguments & Flags](#arguments---flags)
        - [Examples](#examples)
    + [create](#create)
        - [Synopsis](#synopsis-1)
        - [Overview](#overview-1)
        - [Arguments & Flags](#arguments---flags-1)
        - [Examples](#examples-1)
    + [edit / view](#edit---view)
        - [Synopsis](#synopsis-2)
        - [Overview](#overview-2)
        - [Arguments & Flags](#arguments---flags-2)
        - [Examples](#examples-2)
    + [version](#version)
        - [Synopsis](#synopsis-3)
        - [Overview](#overview-3)
        - [Arguments & Flags](#arguments---flags-3)
        - [Examples](#examples-3)

## List of Subcommands

### config

Lists the current configuration for _noted_. This is the combination of default values plus whatever is found in `$HOME/.notedconfig`, where values
in `$HOME/.notedconfig` take precedence.

#### Synopsis

```shell
noted config  
```

#### Overview

The config subcommand will:

- Generate a quick view of the resulting configuration after applying the values in `$HOME/.notedconfig`

#### Arguments & Flags

N/A

#### Examples

View configuration:

```shell
noted config
```

### create

Create a new note.

#### Synopsis

```shell
noted create [Quoted text to use (optional)] [ALTERNATE_FILE_NAME (optional)] 
```

#### Overview

The create subcommand will:

- Look for a file named with today's date, and create it if it doesn't exist
- Append the note template to the file named with today's date, with the current timestamp
- Open the file named with today's date
- Position the cursor in the entry title field

> **Important:**
>
> We encourage users to omit `create` and use the alternate shorthand `noted` without the create keyword. The remainder
> of this documentation will use the shorthand.

#### Arguments & Flags

Both arguments are optional. When quoted text is included the text will automatically be appended to the entry and editing of the entry will be skipped. When
the `ALTERNATE_FILE_NAME` argument is supplied with a filename, then instead of using the automatic file (named with today's date), the file supplied will be
used.

#### Examples

Start a new entry:

```shell
noted
```

Add a new note with the text "This is a quick note" as the title and an empty body:

```shell
noted "This is a quick note"
```

Start a new entry in the file named `process.md`:

```shell
noted 'Some note' process.md
```

### edit / view

Open a specific note file, or today's file if no file is specified, in the default editor.

#### Synopsis

```shell
noted edit [FILE (optional)] 
```

```shell
noted view [FILE (optional)] 
```

#### Overview

Edit and view are interchangeable.

The edit / view subcommand will:

- Look for the file passed as an argument
- If no file is passed, then it will assume today's file
- Open the given file in the default editor

> NOTE:
> Edit is different than create. Create will also populate a new note entry into the given file using the template.
> Edit, on the other hand, will merely open the file.

#### Arguments & Flags

The `FILE` argument is optional. You should not include the extension. The Markdown extension `.md` is assumed.

#### Examples

Open today's file in the default editor.

```shell
noted edit
```

Open the file from 2021-10-01:

```shell
noted edit 2021-10-01
```

Open a file named `process.md`:

```shell
noted view process
```

### version

View the current version of `noted`.

#### Synopsis

```shell
noted version 
```

#### Overview

The version subcommand will print out the current version of `noted`.

#### Arguments & Flags

N/A

#### Examples

View the version:

```shell
noted version
```
