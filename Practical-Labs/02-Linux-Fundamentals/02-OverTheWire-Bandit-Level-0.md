# OverTheWire – Bandit Level 0

**Platform:** OverTheWire  
**Wargame:** Bandit  
**Difficulty:** Beginner  
**Status:** Completed  
**Topic:** Linux Fundamentals / SSH

## Overview

In this lab, I learned how to establish a secure connection to a remote Linux server using SSH (Secure Shell Protocol).

I practiced connecting to a remote system, working with the Linux terminal, and understanding SSH authentication.

## What I Learned

### SSH (Secure Shell Protocol)

- SSH is a cryptographic network protocol used for secure remote access to systems.
- It provides an encrypted connection between a client and a remote server.
- SSH is commonly used for remote administration and command-line access.
- The default SSH port is **22**, but servers can use different ports.

### SSH Connection Syntax

```bash
ssh -p <port> <username>@<hostname>
```

- `ssh` – Starts an SSH connection.
- `-p` – Specifies the port number.
- `<username>` – User account on the remote system.
- `<hostname>` – Hostname or IP address of the server.

### Linux Commands Practiced

| Command | Description |
|---|---|
| `ssh` | Establishes a secure remote connection |
| `ls` | Lists files and directories |
| `ls -a` | Displays files, including hidden files |
| `cat` | Displays the contents of a file |
| `man` | Opens a command's manual page |
| `exit` | Exits the current shell or SSH session |

## Challenges Encountered

I experienced SSH authentication issues while attempting to access the next level.

I investigated the problem by:
- Verifying the username, hostname, and port.
- Checking the SSH connection using verbose mode (`ssh -v`).
- Testing connections using both a hostname and an IP address.
- Reviewing password entry and authentication.

I eventually established a successful connection using Windows Command Prompt.

## Key Takeaways

- SSH is an essential tool for securely accessing remote Linux systems.
- Understanding usernames, hostnames, ports, and authentication is important when troubleshooting connections.
- Linux commands such as `ls`, `cat`, and `man` are useful for exploring unfamiliar environments.
- Troubleshooting connection problems is an important practical cybersecurity skill.

**Next Lab:** OverTheWire – Bandit Level 1

*No passwords or challenge solutions are included in this documentation.*
