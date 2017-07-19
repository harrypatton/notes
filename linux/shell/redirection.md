## Pipelines
A standard output of a command can be *piped* as an input of another command.

```
ls -l /usr/bin | less
```

use `less` to show the content of `ls` command.

Note: be careful about `>` which is to save the output to a file. Misusing it can cause damage to existing files.
E.g, `ls -l /usr/bin > less` may overwrite the `less` program on the machine.

The correct format should be

```
command1 > file1
command1 | command2
```

### Filters
use multiple pipelines to put several commands together. E.g., 

```
ls /bin /usr/bin | sort | less
```

### uniq
The command is used in conjunction with `sort`.

```
ls /bin /usr/bin | sort | uniq | less
ls /bin /usr/bin | sort | uniq -d | less
```

the first command is to remove dupe. The second one with option `-d` is to see the duplicates.

### wc
The command is used to print out line, word and byte counts.

### grep
It is `global regular expression pattern`. E.g., `ls /bin | grep zip`.

### head / tail
Print First / Last Part Of Files. `tail` has an option `-f` to monitor a file content. E.g., it could be very useful to monitor the log file.

### tee
read from stdin and output to both files and stdout. The tee program reads standard input and copies it to both standard output (allowing the data to continue down the pipeline) and to one or more files. This is useful for capturing a pipeline's contents at an intermediate stage of processing.
