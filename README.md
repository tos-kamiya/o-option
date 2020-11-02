ooption
=======

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
ls *.txt | xargs -I {} ooption -o {}-head.out head -3 {}
```

## Usage:

```
Spawn a command line and save output to file.

Usage:
  ooption [-o OUTFILE] [-e ERRFILE] command-line...
  ooption --eo FILE command-line...

Options:
  -o OUTFILE   File to save stdout of the command line.
  -e ERRFILE   File to save stderr of the command line.
  --eo FILE    File to save both stdout and stderr.

Example:
  ooption -o result.txt ls
```

