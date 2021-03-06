# Linux file Command
-------------------
### Command Introduction (命令介绍)
> **SYNOPSIS**
### Command Format and Options (命令格式和选项)
```
#file --help
Usage: file [OPTION...] [FILE...]
Determine type of FILEs.

      --help                 display this help and exit
  -v, --version              output version information and exit
  -m, --magic-file LIST      use LIST as a colon-separated list of magic
                               number files
  -z, --uncompress           try to look inside compressed files
  -b, --brief                do not prepend filenames to output lines
  -c, --checking-printout    print the parsed form of the magic file, use in
                               conjunction with -m to debug a new magic file
                               before installing it
  -e, --exclude TEST         exclude TEST from the list of test to be
                               performed for file. Valid tests are:
                               ascii, apptype, compress, elf, soft, tar, tokens, troff
  -f, --files-from FILE      read the filenames to be examined from FILE
  -F, --separator STRING     use string as separator instead of `:'
  -i, --mime                 output MIME type strings (--mime-type and
                               --mime-encoding)
      --apple                output the Apple CREATOR/TYPE
      --mime-type            output the MIME type
      --mime-encoding        output the MIME encoding
  -k, --keep-going           don't stop at the first match
  -l, --list                 list magic strength
  -L, --dereference          follow symlinks (default)
  -h, --no-dereference       don't follow symlinks
  -n, --no-buffer            do not buffer output
  -N, --no-pad               do not pad output
  -0, --print0               terminate filenames with ASCII NUL
  -p, --preserve-date        preserve access times on files
  -r, --raw                  don't translate unprintable chars to \ooo
  -s, --special-files        treat special (block/char devices) files as
                             ordinary ones
  -C, --compile              compile file specified by -m
  -d, --debug                print debugging messages

Report bugs to http://bugs.gw.com/
```
### Command Example (命令范例)
```

  file

  Determine file type.

  - Give a description of the type of the specified file. Works fine for files with no file extension:
    file filename

  - Look inside a zipped file and determine the file type(s) inside:
    file -z foo.zip

  - Allow file to work with special or device files:
    file -s filename

  - Don't stop at first file type match; keep going until the end of the file:
    file -k filename

  - Determine the mime encoding type of a file:
    file -i filename


```
