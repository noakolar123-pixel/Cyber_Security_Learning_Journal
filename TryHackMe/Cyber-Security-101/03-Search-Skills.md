# TryHackMe - Search Skills

## Learning Path

Cyber Security 101

## Overview

This room introduced several websites, tools and documentation sources that can be used to research systems, files, vulnerabilities and technical problems.

An important cybersecurity skill is knowing **where and how to search for information**, rather than trying to memorize everything.

---

## Shodan

**Shodan** is a search engine for Internet-connected devices and services.

It continuously scans publicly accessible systems on the Internet and collects information about the services they expose.

Shodan can provide information such as:

- IP address
- Open ports
- Running services
- Software versions
- Organization
- Location
- Service banners

It can discover many types of Internet-connected systems, including:

- Web servers
- Network equipment
- Cameras
- Industrial systems
- IoT devices

### Practical Exercise

I searched Shodan for systems running the Apache web server and examined the information Shodan had collected about publicly accessible servers.

### Security Relevance

Shodan can be useful during authorized reconnaissance and vulnerability assessments because exposed service versions may help identify systems that require further investigation.

---

## VirusTotal

**VirusTotal** is an online service that analyzes files, URLs and domains using many different security engines and threat intelligence sources.

It can help determine whether something has previously been identified as suspicious or malicious.

### Practical Exercise

I searched for a file called:

```text
invoice_payment.exe
```

VirusTotal results indicated that the file had been detected as malicious by multiple security engines.

### Important Note

A VirusTotal detection does not automatically prove that a file is malicious.

Results should be investigated further because false positives are possible.

---

## CVE

**CVE (Common Vulnerabilities and Exposures)** is a standardized system for identifying publicly known cybersecurity vulnerabilities.

A CVE identifier usually follows this format:

```text
CVE-YEAR-NUMBER
```

Example:

```text
CVE-2024-12345
```

This gives security researchers, vendors and administrators a common identifier when discussing the same vulnerability.

### Vulnerability Severity

Vulnerabilities are often assigned a **CVSS (Common Vulnerability Scoring System)** score.

CVSS helps describe how serious a vulnerability may be by considering factors related to:

- Exploitability
- Attack complexity
- Required privileges
- User interaction
- Confidentiality impact
- Integrity impact
- Availability impact

### Practical Exercise

I searched for a known vulnerability and examined its severity score and related information.

---

## Product and Tool Documentation

Official documentation should often be one of the first places to look when:

- Learning a new tool
- Troubleshooting unexpected behavior
- Looking for command syntax
- Understanding configuration options

Documentation can often provide more reliable information than random forum posts or tutorials.

---

## Linux Man Pages

Linux provides built-in documentation called **manual pages**, or **man pages**.

They can be opened using:

```bash
man <command>
```

For example:

```bash
man nc
```

This displays documentation for the `nc` command.

---

## Netcat

`nc`, commonly called **Netcat**, is a networking utility that can work with TCP and UDP connections.

Depending on how it is used, Netcat can:

- Connect to TCP services
- Listen on TCP ports
- Send UDP packets
- Receive network data
- Test network connectivity

### Practical Exercise

I used:

```bash
man nc
```

to learn about Netcat directly from its Linux manual page.

---

## GitHub

GitHub can also be useful as a cybersecurity research resource.

It contains:

- Security tools
- Open-source projects
- Detection rules
- Scripts
- Research projects
- Proof-of-concept code related to some vulnerabilities

Any exploit or proof-of-concept code should only be tested in systems where permission has been granted, such as personal labs or authorized training platforms.

---

## Key Takeaways

- Knowing how to search for information is an important cybersecurity skill.
- Shodan can provide information about publicly exposed Internet services.
- VirusTotal can help investigate suspicious files, URLs and domains.
- CVE identifiers provide a standardized way to reference known vulnerabilities.
- CVSS scores help describe vulnerability severity.
- Official documentation should be checked when learning or troubleshooting tools.
- Linux man pages provide documentation directly from the terminal.
- GitHub can be a valuable source of cybersecurity tools and research.
