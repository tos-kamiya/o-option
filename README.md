ooption
=======

Add -o (save to file) option to any command. 

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

