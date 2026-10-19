# TryHackMe - Linux Fundamentals Part 1

## Overview

In this room, I was introduced to Linux, some basic differences between Linux and Windows, and the Linux terminal.

I practiced navigating the filesystem, reading files, searching for information and combining commands.

## Commands Learned

- `whoami` - Displays the current user.
- `echo` - Prints text to the terminal.
- `ls` - Lists files and directories.
- `cd` - Changes the current directory.
- `cat` - Displays the contents of a file.
- `pwd` - Shows the current working directory.
- `find` - Searches for files and directories.
- `grep` - Searches for specific text inside files.

Examples:

```bash
find -name passwords.txt
```

```bash
grep "password123" passwords.txt
```

## Command Operators

I also learned how Linux commands can be combined and how their output can be redirected.

- `&` - Runs a command in the background.
- `&&` - Runs the next command only if the previous command completes successfully.
- `>` - Redirects command output into a file and overwrites existing content.
- `>>` - Redirects command output into a file and appends to existing content.

Example:

```bash
ls > files.txt
```

## Key Takeaway

The Linux terminal allows me to navigate the filesystem, inspect and search files, and combine commands efficiently. These basic commands will be important for future cybersecurity labs.
