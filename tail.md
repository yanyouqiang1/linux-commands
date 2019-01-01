# Linux tail Command
### Command Introduction (命令介绍)
-------------------
> **tail - output the last part of files**

### Command Format and Options (命令格式和选项)
```
#tail --help
Usage: tail [OPTION]... [FILE]...
Print the last 10 lines of each FILE to standard output.
With more than one FILE, precede each with a header giving the file name.
With no FILE, or when FILE is -, read standard input.

Mandatory arguments to long options are mandatory for short options too.
  -c, --bytes=K            output the last K bytes; or use -c +K to output
                             bytes starting with the Kth of each file
  -f, --follow[={name|descriptor}]
                           output appended data as the file grows;
                             an absent option argument means 'descriptor'
  -F                       same as --follow=name --retry
  -n, --lines=K            output the last K lines, instead of the last 10;
                             or use -n +K to output starting with the Kth
      --max-unchanged-stats=N
                           with --follow=name, reopen a FILE which has not
                             changed size after N (default 5) iterations
                             to see if it has been unlinked or renamed
                             (this is the usual case of rotated log files);
                             with inotify, this option is rarely useful
      --pid=PID            with -f, terminate after process ID, PID dies
  -q, --quiet, --silent    never output headers giving file names
      --retry              keep trying to open a file if it is inaccessible
  -s, --sleep-interval=N   with -f, sleep for approximately N seconds
                             (default 1.0) between iterations;
                             with inotify and --pid=P, check process P at
                             least once every N seconds
  -v, --verbose            always output headers giving file names
      --help     display this help and exit
      --version  output version information and exit

If the first character of K (the number of bytes or lines) is a '+',
print beginning with the Kth item from the start of each file, otherwise,
print the last K items in the file.  K may have a multiplier suffix:
b 512, kB 1000, K 1024, MB 1000*1000, M 1024*1024,
GB 1000*1000*1000, G 1024*1024*1024, and so on for T, P, E, Z, Y.

With --follow (-f), tail defaults to following the file descriptor, which
means that even if a tail'ed file is renamed, tail will continue to track
its end.  This default behavior is not desirable when you really want to
track the actual name of the file, not the file descriptor (e.g., log
rotation).  Use --follow=name in that case.  That causes tail to track the
named file in a way that accommodates renaming, removal and creation.

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
For complete documentation, run: info coreutils 'tail invocation'
```
### Command Example (命令范例)
-------------------
**Display the last part of a file.**

- Show last 'num' lines in file:

  ` tail -n num file`

- Show all file since line 'num':

  ` tail -n +num file`

- Show last 'num' bytes in file:

  ` tail -c num file`

- Keep reading file until `Ctrl + C`:

  ` tail -f file`

- Keep reading file until `Ctrl + C`, even if the file is rotated:

  ` tail -F file`