# TryHackMe - Offensive Security Intro

## Learning Path

Cyber Security 101

## Overview

In this lab, I was introduced to the basic idea of offensive security.

The objective was to interact with a simulated banking website and discover functionality that was not directly visible from the main page.

---

## What I Learned

### Web Directory Enumeration

Websites can contain pages and directories that are not linked from the visible user interface.

An attacker or penetration tester can attempt to discover these hidden locations using **directory enumeration**.

For this lab, I used the `dirb` tool.

Example:

```bash
dirb http://target
```

`dirb` sends requests for many common directory and file names and reports which locations exist on the web server.

---

## Practical Exercise

The lab provided a simulated banking website.

I first explored the visible website and then used directory enumeration to search for hidden pages.

After discovering additional functionality, I was able to access a page that was not linked from the main website and interact with the simulated banking application.

---

## Tool Used

### DIRB

DIRB is a web content scanner used to discover hidden directories and files on a web server.

Example usage:

```bash
dirb http://target
```

This can be useful during the **reconnaissance and enumeration** phase of a penetration test.

---

## Key Takeaways

- Not every page on a website needs to be visible through links.
- Hidden directories can sometimes expose sensitive functionality.
- Directory enumeration is an important part of web reconnaissance.
- Tools such as DIRB can automate the discovery of hidden web content.
- Finding an endpoint is only the beginning — it is important to understand what functionality the endpoint exposes.

---
