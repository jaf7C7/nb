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
	ls [<pattern>]
		List all notes with id matching `<pattern>'
	rm <id>
		Delete note matching `<id>'
	show <id>
		Open note matching `<id>' in PAGER
	edit <id>
		Open note matching `<id>' in EDITOR
	search <option> <query>
		Search for notes matching `<query>' and print results
		to stdout
SEARCH OPTIONS
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
$ nb search -i red hat
20230817154917:# Renew (Re-register) Red Hat Developer Subscription (Free tier)
20230817154917:2. Use your Red Hat login ID to sign in to the site.
20230817154917:4. Log out of all Red Hat sites and close your browser(s).
20230817154917:6. You should now see a new Red Hat Developer for Individuals Subscription on your account.

$ nb -t foo
20230817154941: This is foo, the frobinator, the frobulant

$ nb ls
20230817154917: Renew (Re-register) Red Hat Developer Subscription (Free tier)
20230817154941: This is foo, the frobinator, the frobulant
20230719124339: This is another test note
20230710093302: This is a test note

$ PAGER=cat nb show 20230817154941
# This is foo, the frobinator, the frobulant

This is END


$ nb rm 202307\*
delete `20230719124339: This is another test note'? [y/N] y
delete `20230710093302: This is a test note'? [y/N] y

