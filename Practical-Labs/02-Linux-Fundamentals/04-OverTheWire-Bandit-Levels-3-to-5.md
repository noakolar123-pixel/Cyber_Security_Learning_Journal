# OverTheWire – Bandit Levels 3 to 5

**Platform:** OverTheWire  
**Wargame:** Bandit  
**Difficulty:** Beginner  
**Status:** Completed  
**Category:** Linux Fundamentals  
**Topics:** Hidden Files, Directory Navigation, File Identification

---

## Overview

In these two challenges, I continued developing my Linux command-line skills by exploring directories, identifying hidden files, and analyzing different file types.

The main objective was to understand how Linux organizes files and how to locate useful information when file names or file contents are not immediately obvious.

## Level 3 → Level 4: Hidden Files in Linux

### What I Learned

In this challenge, I practiced navigating through directories and locating hidden files.

**Hidden Files**

- In Linux, files and directories whose names begin with a dot (`.`) are considered hidden.
- Hidden files are not displayed by the standard `ls` command.
- The `-a` option allows the `ls` command to display all entries, including hidden files.
- Hidden files are frequently used to store application settings, configuration files, and user preferences.

It is important to understand that **hidden does not mean protected**. A hidden file is simply excluded from ordinary directory listings. Access to the file still depends on Linux permissions.

### Commands Practiced

| Command | Description |
|---|---|
| `ls` | Lists visible files and directories |
| `ls -a` | Lists all entries, including hidden files |
| `ls -la` | Displays hidden entries with detailed file information |
| `cd` | Changes the current directory |
| `cat` | Displays the contents of a file |

### Key Takeaway

I learned that a directory may contain files that are not visible through a standard directory listing.

This is important in cybersecurity because configuration files, hidden directories, and other system information can be relevant when examining a Linux environment.

---

## Level 4 → Level 5: Identifying File Types

### What I Learned

In this challenge, I explored a directory containing multiple files with similar names.

The main difficulty was determining which files contained readable information and which contained other types of data.

**The `file` Command**

The Linux `file` command examines a file and attempts to identify its type based on its contents and other characteristics.

For example:

```bash
file example.txt
```

Depending on the file, the output may identify:

- ASCII or UTF-8 text
- Binary data
- Executable files
- Images
- Compressed archives

Unlike Windows, Linux does not require a filename extension to identify many file types.

For example, a file without `.txt` can still contain readable text.

### Human-Readable vs. Binary Files

**Human-readable text files** contain information that can generally be interpreted directly by a person using a text editor or terminal.

**Binary files** may contain executable instructions, encoded information, multimedia content, or other structured data.

Not every binary file can be meaningfully displayed using `cat`.

Although `cat` can output the contents of both text and binary files, displaying binary data directly in a terminal may produce unreadable characters or affect terminal behavior.

This is why identifying a file before examining its contents is useful.

### Commands Practiced

| Command | Description |
|---|---|
| `ls` | Lists files in a directory |
| `cd` | Navigates between directories |
| `file` | Identifies file types |
| `cat` | Displays file contents |
| `file *` | Attempts to identify each non-hidden entry matched by the wildcard |

### Key Takeaway

I learned that filenames and extensions do not always reveal the actual type of data stored in a file.

Using the `file` command allows me to inspect unfamiliar files and determine which tools may be appropriate for further analysis.

---

## Cybersecurity Relevance

These two challenges introduced several useful concepts for cybersecurity:

- **System Enumeration:** Exploring directories and identifying available files is an important part of understanding a system.
- **Configuration Analysis:** Hidden files may contain settings that influence application or system behavior.
- **File Identification:** Recognizing file types helps determine how unfamiliar data should be analyzed.
- **Linux Fundamentals:** Understanding the filesystem and command-line tools provides a foundation for security analysis, system administration, and penetration testing.

All exercises were performed in the authorized OverTheWire training environment.

## Key Takeaways

After completing these challenges, I improved my understanding of:

1. How Linux handles hidden files and directories.
2. Why hidden files are not necessarily secure files.
3. How to navigate directories and inspect their contents.
4. How the `file` command identifies file formats.
5. The difference between human-readable text and binary data.
6. Why file inspection and system enumeration are useful cybersecurity skills.

**Next Challenge:** OverTheWire – Bandit Level 5 → Level 6

*This documentation focuses on learned concepts and does not include passwords or challenge solutions.*
