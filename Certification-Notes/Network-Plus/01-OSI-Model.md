# OSI Model

The **OSI (Open Systems Interconnection) model** is a conceptual model used to describe how data moves through a network.

It divides network communication into seven layers, with each layer having a different responsibility.

## OSI Layers

| Layer | Name | Main Purpose | Examples |
|---|---|---|---|
| 7 | Application | Network services used by applications | HTTP, DNS, FTP, SMTP, POP3 |
| 6 | Presentation | Data formatting, encoding, encryption and decryption | TLS/SSL, character encoding |
| 5 | Session | Establishes, manages and terminates communication sessions | Session management |
| 4 | Transport | End-to-end transport of data | TCP, UDP |
| 3 | Network | IP addressing and routing between networks | IP, routers, packets |
| 2 | Data Link | Local network communication using MAC addresses | Ethernet, switches, frames |
| 1 | Physical | Transmission of raw signals through physical media | Copper cables, fiber, radio |

---

## Layer 1 - Physical Layer

The Physical layer is responsible for transmitting raw bits across the physical network medium.

Examples include:

- Ethernet cables
- Fiber-optic cables
- Wireless radio signals
- Network adapters
- Connectors

If a problem occurs at Layer 1, troubleshooting may include:

- Checking or replacing cables
- Checking physical connections
- Testing network adapters
- Performing loopback tests
- Checking whether a device or interface is powered on

---

## Layer 2 - Data Link Layer

The Data Link layer provides communication between devices on the same local network.

It works with **frames** and hardware addresses such as **MAC addresses**.

Ethernet is one of the most common Layer 2 technologies.

### Important concepts

- MAC (Media Access Control) addresses
- Ethernet
- Frames
- Network Interface Cards (NICs)
- Switches

A network switch primarily operates at **Layer 2** and forwards Ethernet frames based on MAC addresses.

---

## Layer 3 - Network Layer

The Network layer is responsible for communication between different networks.

Its main responsibilities include:

- Logical addressing
- Routing
- Forwarding packets between networks

The most important protocol at this layer is **IP (Internet Protocol)**.

Routers primarily operate at Layer 3 and determine where packets should be forwarded.

### Important concepts

- IPv4
- IPv6
- IP addresses
- Routers
- Packets
- Routing

---

## Layer 4 - Transport Layer

The Transport layer provides end-to-end communication between devices.

The two main transport protocols are:

### TCP - Transmission Control Protocol

TCP provides reliable, connection-oriented communication.

It can provide:

- Error recovery
- Ordered delivery
- Retransmission of lost data
- Flow control

### UDP - User Datagram Protocol

UDP provides connectionless communication with less overhead.

It does not guarantee that packets will arrive or arrive in order.

Layer 4 also introduces the concept of **port numbers**, which allow a device to identify which application or service should receive the data.

---

## Layer 5 - Session Layer

The Session layer is responsible for managing communication sessions between applications.

Its responsibilities can include:

- Establishing a session
- Maintaining a session
- Terminating a session
- Restarting or recovering communication sessions

In modern networking, many Session layer functions are often handled by higher-level application protocols.

---

## Layer 6 - Presentation Layer

The Presentation layer is responsible for how data is represented.

Its functions can include:

- Character encoding
- Data formatting
- Encryption
- Decryption
- Compression

Encryption technologies such as TLS are commonly used as examples when explaining this layer.

---

## Layer 7 - Application Layer

The Application layer provides network services directly to applications.

Common Layer 7 protocols include:

- HTTP / HTTPS
- DNS
- FTP
- SMTP
- POP3
- IMAP

This is the layer closest to the software that the user interacts with.

---

# Key Takeaways

The OSI model is useful because it allows network problems to be divided into smaller layers.

For example:

- No physical connection → investigate Layer 1
- MAC or switching problem → investigate Layer 2
- IP addressing or routing problem → investigate Layer 3
- TCP/UDP or port problem → investigate Layer 4
- Application protocol problem → investigate Layer 7

Understanding the OSI model is especially useful in cybersecurity because network analysis, packet inspection, firewalls, scanning and troubleshooting all involve different layers of the network stack.
