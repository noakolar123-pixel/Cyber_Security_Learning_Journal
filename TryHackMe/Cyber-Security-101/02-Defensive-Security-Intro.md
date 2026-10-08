# TryHackMe - Defensive Security Intro

## Learning Path

Cyber Security 101

## Overview

In this lab, I was introduced to the basic idea of **defensive security**.

While the previous lab focused on finding weaknesses from an attacker's perspective, this exercise showed the same type of activity from the defender's perspective.

---

## What I Learned

### Defensive Security

Defensive security focuses on detecting, investigating and responding to suspicious or malicious activity.

Instead of looking for vulnerabilities to exploit, a defender monitors systems and tries to identify attackers before they can cause damage.

---

## Practical Exercise

In the simulated Security Hub, I received an alert about suspicious activity targeting the FakeBank website.

The attacker was attempting to discover hidden web pages, similar to the directory enumeration performed in the previous offensive security lab.

The Security Hub provided information such as:

- The attacker's IP address
- The suspicious activity that had been detected
- A web endpoint that the attacker had discovered

One of the discovered endpoints was:

```text
https://fakebank.thm/admin
```

After investigating the alert, I used the simulated defensive tools to block the attacker's access.

---

## Connection to the Previous Lab

In the previous **Offensive Security Intro** lab, I used directory enumeration to discover hidden web content.

In this lab, I saw how that same activity could appear from the defender's perspective.

### Offensive perspective

```text
Attacker → scans website → discovers hidden endpoint
```

### Defensive perspective

```text
Detection → investigation → identify attacker → block access
```

This helped me understand that offensive and defensive cybersecurity are closely connected.

---

## Key Takeaways

- Defensive security focuses on detecting and responding to threats.
- Suspicious web enumeration can be detected by defenders.
- IP addresses and activity logs can help investigate an attack.
- After identifying malicious activity, defenders can take action to block or limit the attacker.
- Understanding offensive techniques can help defenders recognize attacks more effectively.

---
