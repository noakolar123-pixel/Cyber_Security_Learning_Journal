# Networking Devices

Network devices perform different roles when forwarding, filtering, protecting and managing network traffic.

Understanding what each device does and where it operates in the OSI model is important for both networking and cybersecurity.

---

## Router

A **router** connects different IP networks and forwards packets between them.

Routers primarily operate at **OSI Layer 3 - Network Layer**.

### Main functions

- Forward packets between different networks
- Connect LANs to WANs
- Make routing decisions based on IP addresses
- Maintain routing tables
- Connect networks that may use different physical media

For example, a router may connect:

```text
Local Network (LAN)
        |
      Router
        |
Internet / WAN
```

Routers are commonly used to connect a private local network to the Internet.

---

## Switch

A **switch** connects devices inside a local network.

Traditional switches primarily operate at **OSI Layer 2 - Data Link Layer**.

They forward Ethernet frames using **MAC addresses**.

### Main functions

- Connect devices within a LAN
- Learn MAC addresses
- Forward Ethernet frames
- Separate traffic between switch ports

Many switches perform much of their packet/frame processing using specialized hardware such as **ASICs (Application-Specific Integrated Circuits)**.

### Power over Ethernet (PoE)

Some switches support **PoE - Power over Ethernet**.

PoE allows both electrical power and network data to travel through the same Ethernet cable.

This is commonly used for devices such as:

- Wireless access points
- IP cameras
- VoIP phones

### Layer 3 Switch

Some switches also include routing functionality.

These are commonly called **Layer 3 switches**.

---

## Firewall

A **firewall** controls traffic between networks according to security rules.

A traditional firewall may filter traffic based on information such as:

- Source IP address
- Destination IP address
- TCP or UDP port
- Protocol
- Connection state

Example:

```text
Internal Network
      |
   Firewall
      |
   Internet
```

Firewalls are often positioned between trusted and untrusted networks.

### Next-Generation Firewall (NGFW)

A **Next-Generation Firewall** provides additional capabilities beyond traditional packet filtering.

NGFWs may be able to:

- Identify applications
- Inspect traffic more deeply
- Apply application-based security policies
- Integrate intrusion prevention functionality
- Inspect encrypted traffic when configured appropriately

Some firewall devices can also provide additional services such as:

- NAT
- VPN connectivity

However, NAT is not required for a device to function as a firewall.

---

## IDS and IPS

### IDS - Intrusion Detection System

An **IDS** monitors traffic and attempts to identify suspicious or malicious activity.

If an attack is detected, the IDS can generate:

- Alerts
- Alarms
- Log entries

An IDS normally focuses on **detection** rather than directly stopping traffic.

### IPS - Intrusion Prevention System

An **IPS** can detect malicious activity and can also take action to prevent it.

An IPS is commonly deployed inline so that it can block malicious traffic before it reaches the target.

### Detection vs Prevention

```text
IDS → Detect and alert

IPS → Detect and potentially block
```

These systems may attempt to detect attacks such as:

- Exploitation attempts
- Buffer overflows
- Web attacks
- Malicious network traffic
- Known attack signatures

---

## Load Balancer

A **load balancer** distributes incoming traffic across multiple servers.

Instead of every user connecting directly to one server:

```text
             Internet
                |
          Load Balancer
          /    |    \
         /     |     \
     Server A Server B Server C
```

This helps improve:

- Availability
- Scalability
- Performance
- Fault tolerance

### Health Checks

Load balancers can monitor backend servers.

If one server fails, the load balancer can stop sending traffic to it and continue using the remaining healthy servers.

### Layer 4 and Layer 7 Load Balancing

Load balancers can operate at different layers.

**Layer 4 load balancing** may make decisions using:

- IP addresses
- TCP ports
- UDP ports

**Layer 7 load balancing** can make decisions based on application information such as HTTP requests.

### TLS Offloading

A load balancer can sometimes perform **TLS termination/offloading**.

This means the load balancer handles encryption and decryption instead of requiring every backend server to perform that work.

---

## Proxy Server

A **proxy server** acts as an intermediary between a client and another service.

Instead of the client communicating directly with an Internet server:

```text
Client
   |
Proxy Server
   |
Internet
```

The client sends its request to the proxy.

The proxy then performs the request on behalf of the client and returns the result.

### Uses of a Proxy

A proxy can be useful for:

- Access control
- URL filtering
- Content filtering
- Malware scanning
- Logging
- Caching

A proxy placed between internal users and the Internet is commonly called a **forward proxy**.

---

## NAS vs SAN

Centralized storage can be provided across a network using technologies such as NAS and SAN.

### NAS - Network Attached Storage

A **NAS** provides **file-level storage** over a network.

Users and systems access files and folders through network file protocols.

Common protocols include:

- SMB
- NFS

From the client's perspective, the NAS behaves similarly to shared network storage.

### SAN - Storage Area Network

A **SAN** provides **block-level storage**.

Instead of presenting individual shared files, the storage is presented to a system as blocks that can behave similarly to a locally attached disk.

SAN technologies are commonly used in:

- Data centers
- Virtualization environments
- Large enterprise storage systems

Common technologies include:

- Fibre Channel
- iSCSI

### Main Difference

```text
NAS → File-level storage

SAN → Block-level storage
```

Both can require significant network bandwidth depending on workload.

---

## Wireless Access Point (AP)

A **Wireless Access Point** allows wireless devices to connect to a wired network.

Example:

```text
Phone / Laptop
      )))
       AP
       |
   Ethernet
       |
     Switch
```

The access point bridges wireless communication with the wired Ethernet network.

An AP primarily performs Layer 2 functions.

---

## Wireless LAN Controller (WLC)

A **Wireless LAN Controller** provides centralized management for multiple wireless access points.

Instead of configuring every AP individually, administrators can manage many access points from a central system.

### Common functions

- Centralized AP configuration
- Deploying new access points
- Security policy management
- Performance monitoring
- Wireless network management
- Applying configuration changes across multiple APs

This is particularly useful in environments with many wireless access points.

---

# Key Takeaways

- **Router** → connects different IP networks and operates primarily at Layer 3
- **Switch** → connects devices inside a LAN and normally operates at Layer 2
- **Layer 3 switch** → combines switching and routing capabilities
- **Firewall** → controls network traffic according to security rules
- **IDS** → detects suspicious activity and generates alerts
- **IPS** → detects and can actively block malicious traffic
- **Load balancer** → distributes traffic across multiple servers
- **Proxy** → acts as an intermediary between clients and other services
- **NAS** → provides file-level network storage
- **SAN** → provides block-level storage
- **Access Point** → connects wireless clients to a wired network
- **Wireless LAN Controller** → centrally manages multiple access points
