# OverTheWire – Bandit Levels 1–2

**Platform:** OverTheWire  
**Wargame:** Bandit  
**Difficulty:** Beginner  
**Status:** Completed  
**Topic:** Linux File Handling

## Overview

In these labs, I practiced working with Linux files that have unusual names, including filenames beginning with a hyphen (`-`) and filenames containing spaces.

The exercises helped me understand how Linux commands interpret filenames and command-line arguments.

## What I Learned

### Level 1 → Level 2: Filenames Beginning with a Hyphen

- Learned that a filename beginning with `-` can be interpreted as a command-line option.
- Explored how commands distinguish filenames from arguments.
- Learned about the `--` separator, which marks the end of command options.
- Practiced using explicit paths when working with special filenames.

### Level 2 → Level 3: Filenames Containing Spaces

- Learned that the shell normally uses spaces to separate command arguments.
- Understood why filenames containing spaces need special handling.
- Practiced using quotation marks to treat a filename containing spaces as a single argument.
- Learned that backslash escaping can also prevent spaces from being interpreted as argument separators.

## Key Concepts

| Concept | Description |
|---|---|
| Command-line arguments | Values passed to a command |
| Options | Arguments that modify command behavior |
| `--` | Marks the end of options for commands that support it |
| Quotation marks | Preserve spaces within a single argument |
| Backslash (`\`) | Escapes the special meaning of the following character |
| Relative paths | Specify file locations relative to the current directory |

## Key Takeaways

- Linux commands may interpret filenames differently depending on their characters.
- Understanding how the shell processes arguments helps prevent command errors.
- Using explicit paths and proper quoting makes working with unusual filenames easier.
- Troubleshooting unexpected command behavior requires understanding how commands interpret their input.

**Next Lab:** OverTheWire – Bandit Level 3 → Level 4

*No passwords or challenge solutions are included in this documentation.*
