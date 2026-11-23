# OverTheWire – Bandit Level 8 to 9

**Platform:** OverTheWire  
**Wargame:** Bandit  
**Difficulty:** Beginner  
**Status:** Completed  
**Category:** Linux Fundamentals  
**Topics:** Text Processing, Sorting, Duplicate Detection, Pipes

---

## Overview

In this challenge, I practiced processing text files using Linux command-line tools.

The objective was to identify the only line in `data.txt` that appeared exactly once, while all other lines were repeated.

This exercise helped me understand how to combine multiple commands to efficiently process and filter text data.

## What I Learned

### 1. Sorting Text with `sort`

The `sort` command reads lines from a file and arranges them in a specified order.

By default, it performs a lexicographical sort based on the current locale.

Example:

```bash
sort example.txt
```

Sorting is particularly useful when working with large datasets, analyzing logs, or preparing data for further processing.

### 2. Finding Duplicate Lines with `uniq`

The `uniq` command processes adjacent lines and identifies or filters repeated content.

An important limitation is that **`uniq` only detects consecutive duplicate lines**.

If two identical lines are separated by other lines, `uniq` will not treat them as adjacent duplicates.

This is why `uniq` is frequently combined with `sort`.

### 3. Understanding the `-u` Option

The `-u` option tells `uniq` to output only lines that occur once within each consecutive group.

Example:

```bash
uniq -u example.txt
```

When the input has already been sorted, this can be used to identify lines that appear exactly once in the entire file.

Other useful `uniq` options include:

| Option | Description |
|---|---|
| `-u` | Displays lines that occur only once in a consecutive group |
| `-d` | Displays one copy of each repeated consecutive group |
| `-c` | Displays the number of occurrences in each consecutive group |
| `-i` | Ignores case differences when comparing lines |

### 4. Combining Commands with Pipes (`|`)

The pipe operator connects the standard output of one command to the standard input of another.

For example:

```bash
sort example.txt | uniq -c
```

This command sorts the file and displays each distinct line with its occurrence count.

**How the pipeline works:**

1. `sort` reads and sorts the input.
2. The pipe (`|`) transfers the sorted lines to `uniq`.
3. `uniq -c` groups consecutive identical lines and counts their occurrences.

Pipes allow commands to work together without manually creating intermediate files.

### 5. Why Sorting Matters

Consider the following example:

```text
apple
banana
apple
orange
banana
```

Running `uniq` directly on this input will not remove the repeated values because they are not adjacent.

After sorting:

```text
apple
apple
banana
banana
orange
```

The repeated lines are grouped together.

This allows `uniq` to correctly identify duplicates and unique values.

## Cybersecurity Relevance

Text-processing tools are widely used in system administration and cybersecurity.

- **Log Analysis:** Grouping repeated log entries to identify recurring events.
- **Security Monitoring:** Counting repeated events or indicators.
- **Data Filtering:** Removing duplicate information from investigation results.
- **Incident Response:** Organizing large volumes of text data.
- **Automation:** Combining commands to create efficient processing pipelines.

## Challenges Encountered

The main challenge was understanding why `uniq` alone was not sufficient to find lines that appeared only once throughout a file.

I learned that identical lines must first be grouped together, which can be achieved using `sort`.

Combining commands provided a much more efficient way to analyze the file than manually searching through its contents.

## Key Takeaways

1. `sort` arranges text lines into a specified order.
2. `uniq` compares adjacent lines rather than searching the entire file for duplicates.
3. The `-u` option displays lines that occur only once within consecutive groups.
4. Sorting input before using `uniq` makes it possible to identify globally unique lines.
5. Pipes allow multiple Linux commands to work together efficiently.
6. Text processing is an essential skill for log analysis and cybersecurity investigations.

**Next Challenge:** OverTheWire – Bandit Level 9 to 10

*This documentation focuses on learned concepts and does not include passwords or full challenge solutions.*
