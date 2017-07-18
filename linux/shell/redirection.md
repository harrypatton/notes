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

### Uniq
The command is used in conjunction with `sort`.

```
ls /bin /usr/bin | sort | uniq | less
ls /bin /usr/bin | sort | uniq -d | less
```

the first command is to remove dupe. The second one with option `-d` is to see the duplicates.
