# Networking Functions

Modern networks use many different technologies to improve performance, security, availability and reliability.

This lesson covered several important networking functions, including CDN, VPN, QoS, TTL and DNS caching.

---

## Content Delivery Network (CDN)

A **Content Delivery Network (CDN)** is a geographically distributed network of servers used to deliver content more efficiently to users.

Instead of every user downloading content from one central server, a CDN can provide cached content from a server located closer to the user.

Example:

```text
Origin Server
     |
     +-------------------+
     |                   |
CDN Europe           CDN USA
     |                   |
European Users       US Users
```

### Benefits of a CDN

- Reduced latency
- Faster content delivery
- Reduced load on the origin server
- Improved availability
- Better performance for users in different geographic locations

CDNs are commonly used for:

- Images
- Videos
- JavaScript and CSS files
- Software downloads
- Website content

---

## Virtual Private Network (VPN)

A **Virtual Private Network (VPN)** creates a secure connection across another network, such as the Internet.

VPNs are commonly used to allow users to securely connect to a remote private network.

Example:

```text
Remote User
     |
  Internet
     |
Encrypted VPN Tunnel
     |
Company Network
```

VPN traffic is typically protected using encryption so that sensitive information cannot easily be read while travelling across an untrusted network.

### VPN Concentrator

In larger environments, a **VPN concentrator** can manage many VPN connections at the same time.

It can perform tasks such as:

- Establishing VPN tunnels
- Authentication
- Encryption
- Decryption
- Managing multiple VPN users

---

## Quality of Service (QoS)

**Quality of Service (QoS)** is used to prioritize certain types of network traffic.

Not all applications have the same requirements.

For example:

- Voice calls require low latency
- Video streaming requires consistent bandwidth
- File downloads can usually tolerate delays

QoS allows administrators to give important traffic higher priority when network resources are limited.

### Example

```text
Voice traffic      → High priority
Video conference   → High priority
Web browsing       → Normal priority
Large file download → Lower priority
```

QoS policies may be configured on devices such as:

- Routers
- Switches
- Firewalls

---

## Time To Live (TTL)

TTL is used in different ways depending on the protocol.

### IP TTL

In an IP packet, **TTL does not represent actual time**.

Instead, it represents the maximum number of router hops a packet can make before being discarded.

Each router that forwards the packet decreases the TTL value by 1.

Example:

```text
Initial TTL = 64

Router 1 → TTL 63
Router 2 → TTL 62
Router 3 → TTL 61
```

If TTL reaches `0`, the router discards the packet.

This prevents packets from travelling around the network forever.

---

## Routing Loops

A **routing loop** occurs when routers continuously forward a packet between each other because of incorrect routing information.

Example:

```text
Router A → Router B
    ↑          |
    |          ↓
    +----------+
```

Without a limit, the packet could continue circulating indefinitely.

IP TTL prevents this by reducing the TTL value every time the packet passes through a router.

When TTL reaches zero, the packet is discarded.

---

## Default TTL Values

Operating systems often use different initial TTL values.

Common examples include:

- Linux / macOS → often `64`
- Windows → often `128`

These are common defaults, but they should not be treated as guaranteed values because they can be changed.

---

## DNS TTL

TTL is also used by **DNS**, but it has a different meaning than IP TTL.

In DNS, TTL specifies how long a DNS record may remain cached before it should be refreshed.

This value is normally measured in **seconds**.

Example:

```text
example.com → 192.0.2.10
TTL → 3600 seconds
```

This means the DNS information may be cached for one hour.

After the TTL expires, the DNS resolver may request the information again from the appropriate DNS server.

### Why DNS Caching Is Useful

- Reduces DNS traffic
- Speeds up name resolution
- Reduces load on DNS servers
- Improves user experience

---

# Key Takeaways

- **CDN** → distributes content using geographically distributed servers
- **VPN** → creates a secure connection across an untrusted network
- **VPN concentrator** → manages many VPN connections
- **QoS** → prioritizes important network traffic
- **IP TTL** → limits the number of router hops a packet can make
- **Routing loop** → packets repeatedly circulate between routers
- **DNS TTL** → determines how long a DNS record can remain cached
