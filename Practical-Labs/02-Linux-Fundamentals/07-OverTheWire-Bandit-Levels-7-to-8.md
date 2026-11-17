# OverTheWire – Bandit Level 7 to 8

**Platform:** OverTheWire  
**Wargame:** Bandit  
**Difficulty:** Beginner  
**Status:** Completed  
**Category:** Linux Fundamentals  
**Topics:** Text Searching, grep, Pipes, Command-Line Filtering

---

## Overview

In this challenge, I practiced searching for specific text within a file using Linux command-line tools.

The objective was to locate a password stored in a text file called `data.txt`, next to the word `millionth`.

Instead of manually reading through the entire file, I used text-searching commands to identify the relevant information.

## What I Learned

### 1. Searching Text Using `grep`

The `grep` command is used to search text for lines matching a specified pattern.

It is commonly used to search through text files, command outputs, and system logs.

Basic syntax:

```bash
grep [options] "pattern" filename
```

**Example:**

```bash
grep "error" application.log
```

This searches `application.log` and displays lines containing the word `error`.

The command is case-sensitive by default.

### 2. Understanding Regular Expressions

The name `grep` originates from the historical editor command *g/re/p*, meaning "global regular expression print".

Regular expressions (regex) allow more advanced text matching.

For example:

```bash
grep "^ERROR" application.log
```

The `^` character matches the beginning of a line, so this command displays lines starting with `ERROR`.

Another example:

```bash
grep -i "failed" application.log
```

The `-i` option performs a case-insensitive search.

### 3. Combining Commands Using Pipes (`|`)

A pipe allows the standard output of one command to become the standard input of another command.

Example:

```bash
cat application.log | grep "warning"
```

**How it works:**

1. `cat` outputs the contents of the file.
2. The pipe operator (`|`) forwards that output to the next command.
3. `grep` filters the received text and displays matching lines.

This allows multiple commands to work together without creating temporary files.

### 4. Direct File Searching vs. Pipes

There are different ways to search for text.

**Direct searching:**

```bash
grep "warning" application.log
```

**Searching through a pipe:**

```bash
cat application.log | grep "warning"
```

Both commands can produce the same result.

However, direct searching is generally simpler when examining a single file.

Pipes become especially useful when filtering output from commands such as `ps`, `ls`, or other tools.

### 5. Useful `grep` Options

| Option | Description |
|---|---|
| `-i` | Ignores uppercase/lowercase differences |
| `-n` | Displays matching line numbers |
| `-v` | Displays lines that do not match |
| `-c` | Counts matching lines |
| `-r` | Searches recursively through directories |
| `-E` | Enables extended regular expressions |

## Cybersecurity Relevance

Text searching is an important skill in cybersecurity because many systems produce large amounts of logs and diagnostic information.

The `grep` command can help with:

- **Log Analysis:** Finding error messages and suspicious activity.
- **Security Monitoring:** Searching for failed login attempts.
- **Incident Investigation:** Filtering large text files for relevant events.
- **System Administration:** Locating specific configuration values.
- **Automation:** Combining commands to process and filter information.

## Challenges Encountered

The main challenge was identifying specific information within a text file.

Rather than manually examining every line, I used `grep` to filter the content based on a known keyword.

I also learned how the pipe operator can connect multiple commands and make text processing more efficient.

## Key Takeaways

1. `grep` is a powerful tool for searching text using patterns.
2. Regular expressions support more advanced searches.
3. Pipes connect the output of one command to the input of another.
4. Direct searching is often simpler than piping `cat` into `grep`.
5. Text filtering is an essential skill for Linux administration and cybersecurity investigations.

**Next Challenge:** OverTheWire – Bandit Level 8 to 9

*This documentation focuses on learned concepts and does not include passwords or full challenge solutions.*
