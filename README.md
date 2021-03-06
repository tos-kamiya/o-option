o-option
========

Add -o (save to file) option to any command. 

## What? Why?

Have you ever had trouble with interference between command-invoking command and redirect?

For example, a command line:

```sh
ls *.txt | xargs -I {} head -n 3 {} > {}-head.out
```

does NOT create `*-head.out` file for each of the `*.txt` files but creates one file `{}-head.out` containing outputs of all `head` command executions.

The command `o-o` is here to help!

You can now run as follows:

```sh
ls *.txt | xargs -I {} o-o -o {}-head.out head -3 {}
```

## Usage

```
Spawn a command line and save output to file.

Usage:
  o-o [options] [-e ERRFILE|--eo] [--] <commandline>...

Options:
  -o OUTFILE   File to write the stdout.
  -e ERRFILE   File to write the stderr.
  --eo         Redirect the stderr to the stdout.
  -i INPFILE   File to read as the stdin.
  --dry-run    Show equivalent command line in POSIX shell.

Example:
  o-o -o lsoutput.txt ls
```

## Installation

To install, copy a file `o-o` in any directory on PATH, e.g. `~/bin`.

To uninstall, remove the file `o-o`.

## License

Unlicense (Public Domain).

