# OverTheWire – Bandit Level 6 to 7

**Platform:** OverTheWire  
**Wargame:** Bandit  
**Difficulty:** Beginner  
**Status:** Completed  
**Category:** Linux Fundamentals  
**Topics:** File Enumeration, Linux File Ownership, Groups, Filesystem Navigation, Output Redirection

---

## Overview

In this challenge, I had to locate a file stored somewhere on the Linux server.

Unlike previous challenges, the target file was not necessarily located in the current working directory.

The file had three specific properties:

- **Owner:** `bandit7`
- **Group:** `bandit6`
- **Size:** Exactly 33 bytes

The objective was to identify a file matching these properties by exploring the Linux filesystem.

## What I Learned

### 1. Linux File Ownership and Groups

Every Linux file has an associated user owner and group owner.

These properties help Linux manage access to files and directories.

- **User ownership:** Identifies the account that owns the file.
- **Group ownership:** Identifies the group associated with the file.
- **Permissions:** Define which operations the owner, group members, and other users are allowed to perform.

The `ls -l` command displays this information alongside file size and modification time.

For example:

```text
-rw-r----- 1 alice developers 33 Nov 11 14:00 example.txt
```

Here, `alice` is the owner, `developers` is the assigned group, and `33` is the file size in bytes.

### 2. Searching the Linux Filesystem

At first, I searched manually using commands such as:

- `ls -al` – Display detailed directory listings, including hidden files.
- `cd ..` – Move to the parent directory.
- `find` – Search for files based on specific properties.

My initial searches were unsuccessful because I was searching within directories that did not contain the target file.

I learned that the starting directory determines the scope of a `find` search.

For example:

```bash
find .
```

Searches the current directory and its subdirectories.

```bash
find /
```

Starts searching from the filesystem root, covering accessible paths throughout the filesystem.

### 3. Filtering Files with `find`

The `find` command supports multiple filters that can be combined to narrow down results.

| Option | Description |
|---|---|
| `-type f` | Matches regular files |
| `-user` | Filters by file owner |
| `-group` | Filters by file group |
| `-size` | Filters by file size |
| `-name` | Filters by filename |

For example, the following command searches for regular files owned by a particular user and group, with an exact size:

```bash
find / -type f -user alice -group developers -size 100c
```

The `c` suffix specifies that the size is measured in bytes.

### 4. Efficient Searching and Error Redirection

After completing the challenge, I learned that I could have searched more efficiently by combining all the required file properties into a single command.

```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```

**Command breakdown:**

- `find /` – Starts searching from the root directory.
- `-type f` – Searches only for regular files.
- `-user bandit7` – Matches files owned by the specified user.
- `-group bandit6` – Matches files assigned to the specified group.
- `-size 33c` – Matches files exactly 33 bytes in size.
- `2>/dev/null` – Discards error messages generated during the search.

**Understanding `2>/dev/null`**

Linux processes commonly use three standard data streams:

| Stream | Number | Purpose |
|---|---|---|
| stdin | 0 | Standard input |
| stdout | 1 | Standard output |
| stderr | 2 | Standard error output |

When searching the entire filesystem, some directories may be inaccessible due to insufficient permissions.

The `2>` operator redirects standard error output, while `/dev/null` is a special device that discards anything written to it.

Therefore:

```bash
2>/dev/null
```

Suppresses error messages while allowing normal search results to remain visible.

This does not bypass Linux permissions. It only prevents error messages from cluttering the terminal.

### 5. Absolute and Relative Paths

This challenge also improved my understanding of Linux paths.

- `/` – The filesystem root.
- `.` – The current directory.
- `..` – The parent directory.
- **Absolute path:** Specifies a location starting from `/`.
- **Relative path:** Specifies a location relative to the current working directory.

Understanding these concepts is essential when exploring unfamiliar Linux systems.

## Challenges Encountered

The main difficulty was determining where to search.

Initially, I assumed the target file might be located near my current directory. I manually navigated through directories and inspected their contents.

Although this approach was not efficient, it helped me better understand Linux directory structures.

After completing the challenge, I learned how to combine multiple `find` filters and suppress unnecessary error messages.

## Cybersecurity Relevance

- **File Enumeration:** Identifying files based on metadata and ownership.
- **Access Control:** Understanding Linux file permissions and ownership.
- **System Investigation:** Searching across complex directory structures.
- **Security Auditing:** Locating files associated with particular users or groups.
- **Automation:** Replacing repetitive manual searches with targeted commands.
- **Troubleshooting:** Understanding why searches may fail or encounter permission errors.

## Key Takeaways

1. Linux files have both a user owner and an associated group.
2. `find` can combine multiple conditions to locate specific files.
3. Search scope depends on the starting directory.
4. The `-size` option supports exact byte measurements using the `c` suffix.
5. Standard error output can be redirected using `2>`.
6. `/dev/null` discards unwanted output without changing access permissions.
7. Targeted searches are generally more efficient than manually inspecting large directory structures.

**Next Challenge:** OverTheWire – Bandit Level 7 to 8

*This documentation focuses on learned concepts and practical skills. No passwords are included.*
