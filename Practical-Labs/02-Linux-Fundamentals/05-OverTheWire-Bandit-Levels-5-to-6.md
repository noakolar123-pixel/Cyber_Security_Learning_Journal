# OverTheWire – Bandit Level 5 to 6

**Platform:** OverTheWire  
**Wargame:** Bandit  
**Difficulty:** Beginner  
**Status:** Completed  
**Category:** Linux Fundamentals  
**Topics:** File Enumeration, File Permissions, File Size, Directory Exploration

## Overview

In this challenge, I had to locate a specific file somewhere inside the `inhere` directory, which contained 19 subdirectories.

The target file had to satisfy three requirements:

- **Human-readable:** The file had to contain readable text.
- **Exactly 1033 bytes:** The file size had to match the specified requirement.
- **Non-executable:** The file had to have no execute permission bits set.

The main challenge was identifying the correct file among many files distributed across multiple subdirectories.

## What I Learned

### 1. Exploring Multiple Directories

I practiced navigating through multiple Linux directories and examining their contents.

I used the `ls` command with different options to inspect files and their properties.

### 2. Understanding `ls` Options

- `ls -l` – Displays detailed file information, including permissions, ownership and size.
- `ls -a` – Includes hidden files and directories.
- `ls -b` – Displays non-printable characters in filenames using escape sequences.
- `ls -lab` – Combines all three options.

### 3. Understanding File Permissions

The `ls -l` command displays permission information using characters such as:

`-rw-r--r--`

- The first character identifies the file type.
- The next three characters represent owner permissions.
- The following three represent group permissions.
- The final three represent permissions for others.

The `x` permission indicates whether execution is permitted for the corresponding category.

### 4. File Size and Readability

I learned how to examine file sizes in bytes using detailed directory listings.

I also learned that file size and readability are different characteristics. A file can have the correct size without containing human-readable information.

### 5. Inspecting Files

After identifying files with matching properties, I used `cat` to inspect readable content.

I also learned that `file` can help determine whether a file contains text or another data format.

## Challenges Encountered

The main difficulty was searching through 19 subdirectories and distinguishing files based on their metadata.

I initially inspected the directories manually, which helped me understand file permissions, sizes and directory structures.

This also demonstrated why automated file searches become useful when working with larger directory structures.

## Cybersecurity Relevance

- **File Enumeration:** Discovering files across directory structures.
- **Permission Analysis:** Understanding which files can be read, modified or executed.
- **Metadata Analysis:** Identifying files using properties such as size and permissions.
- **System Investigation:** Efficiently exploring unfamiliar Linux environments.

## Key Takeaways

- Linux files can be identified using multiple properties.
- File size, permissions and content readability are separate characteristics.
- `ls -l` provides useful metadata for examining files.
- Searching manually can become inefficient when many directories are involved.
- Commands such as `find` can automate searches using file attributes.

**Next Challenge:** OverTheWire – Bandit Level 6 to 7

*No passwords or challenge solutions are included in this documentation.*
