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
  o-o [options] [-o OUTFILE|-r OUTFILE|--ir INOUTFILE] [--] <commandline>...

Options:
  -o OUTFILE   Redirect the standard out to the file.
  -r OUTFILE   Redirect the standard out to a temp file and then rename the temp file to.
  -e ERRFILE   Redirect the standard out to the file.
  --eo         Redirect the stderr to the stdout.
  --ir INOUTFILE   Redirect both the standard in/out to the file (implicitly infers -r).
  --io INOUT   Alias of --ir.
  -q           Same as `-e /dev/null`.
  -i INPFILE   File to read as the standard input.
  --dry-run    Show equivalent command line in POSIX shell.

Example:
  o-o -o lsoutput.txt ls
```

In case the option -r is specified, the output file is not generated when the command line execution fails.

In case the option --ir is specified, the input file will not be overwritten when the command line execution fails.

## Installation

To install, copy a file `o-o` in any directory on PATH, e.g. `~/bin`.

To uninstall, remove the file `o-o`.

## License

Unlicense (Public Domain).

