# nb

A POSIX compliant shell script for writing, searching and managing your
notes from the command line.

## Installation

Just clone this repository and either copy or symlink the `nb` executable
to a directory in your `PATH`.

## Usage

```
SUMMARY
	nb : Create and search a repository of notes
USAGE
	nb [new|rm|open|show|edit] <id>
	nb search <option> <query>
COMMANDS
	new
		Create a new note
	rm <id>
		Delete note matching `<id>'
	open <id>
		Open note matching `<id>' in BROWSER
	show <id>
		Open note matching `<id>' in PAGER
	edit <id>
		Open note matching `<id>' in EDITOR
	search <option> <query>
		Search for notes matching `<query>' and print results
		to stdout
OPTIONS
	-t : Search titles only
	-i : Search case-insensitively
	-l : Print results as markdown links
	-n : Print matching filenames only

   The default behaviour (with no non-option arguments) is to open
   a new note in EDITOR. If the first non-option argument is not one of
   `new', `rm',`edit', or `search', then `search' is assumed.

```

## Examples

```
$ nb search 'foo'
20231907124735:# This is foo, the frobinator, the frobulant
$ nb show 20231907124735
::::::::::::::
20231907124735
::::::::::::::
# This is foo, the frobinator, the frobulant

This is END

```
