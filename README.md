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

`ooption` is here to help!

You can now run as follows:

```sh
ls *.txt | xargs -I {} o-o {}-head.out head -3 {}
```

## Usage

```
Spawn a command line and save output to file.

Usage:
  o-o OUTFILE [--eo|-e ERRFILE] command-line...

Options:
  -e ERRFILE   File to save stderr of the command line.
  --eo         Redirect stderr to the same output file.

Example:
  o-o result.txt ls
```

## Installation

To install, put a file `o-o` in any directory on PATH, e.g. `~/bin`:

To uninstall, remove the `o-o` file:
