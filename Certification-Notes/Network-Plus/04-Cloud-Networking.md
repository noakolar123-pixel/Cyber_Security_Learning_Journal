# Cloud Networking

Cloud networking allows traditional networking concepts such as routing, switching, firewalls and private networks to be implemented virtually inside a cloud environment.

---

## Cloud Design Concepts

### On-Demand Computing

Cloud providers allow computing resources to be created when they are needed instead of requiring organizations to purchase and install physical hardware in advance.

---

### Elasticity

**Elasticity** means that cloud resources can scale up or down depending on demand.

For example:

- More servers can be added when traffic increases.
- Resources can be reduced when demand decreases.

This allows applications to dynamically adjust to changing workloads.

---

### Multitenancy

**Multitenancy** means that multiple customers can use the same underlying cloud infrastructure while remaining logically separated from each other.

Cloud providers use virtualization and isolation mechanisms to ensure that one customer cannot normally access another customer's resources.

---

# Network Function Virtualization (NFV)

**Network Function Virtualization (NFV)** replaces dedicated physical network appliances with software-based virtual versions.

Examples of network functions that can be virtualized include:

- Routers
- Firewalls
- Load balancers
- VPN gateways
- Intrusion detection and prevention systems

Instead of installing a new physical appliance, a virtual network function can often be deployed quickly through software.

### Benefits

- Faster deployment
- Easier scaling
- Reduced dependence on physical hardware
- Centralized management
- Greater flexibility

---

# Virtual Private Cloud (VPC)

A **Virtual Private Cloud (VPC)** is a private and logically isolated network inside a public cloud provider.

It behaves similarly to a traditional private network but exists virtually inside the cloud.

A VPC can contain:

- Subnets
- Virtual machines
- Servers
- Databases
- Routing tables
- Gateways
- Security rules

Example:

```text
VPC: 10.0.0.0/16

├── Public Subnet
│   └── Web Server
│
└── Private Subnet
    └── Database Server
```

Organizations can create multiple VPCs for different applications, departments or environments.

---

# Connecting VPCs

Different VPCs are often placed in different IP networks.

Sometimes these VPCs still need to communicate with each other.

A cloud networking service such as a **Transit Gateway** can provide centralized connectivity between multiple VPCs or networks.

Example:

```text
VPC A ──┐
        │
VPC B ──┼── Transit Gateway
        │
VPC C ──┘
```

This can simplify network design compared with creating many individual connections between VPCs.

---

# VPN and Cloud Networks

A **Virtual Private Network (VPN)** can securely connect:

- A user to a cloud network
- An office network to a cloud network
- Two remote networks

Example:

```text
Company Office
      |
 Encrypted VPN
      |
     VPC
```

VPNs allow private cloud resources to be accessed securely across an untrusted network such as the Internet.

---

# Internet Gateway

An **Internet Gateway** provides connectivity between a VPC and the public Internet.

It is commonly used when resources such as web servers need to be publicly reachable.

Example:

```text
Internet
   |
Internet Gateway
   |
Public Subnet
   |
Web Server
```

Routing and security rules must still allow the traffic.

---

# NAT Gateway

A **NAT Gateway** allows resources inside a private subnet to access the Internet without making those resources directly reachable from the Internet.

Example:

```text
Private Server
     |
NAT Gateway
     |
 Internet
```

This is useful when a private server needs to:

- Download updates
- Install software packages
- Access external APIs
- Download security patches

The connection is initiated from inside the private network.

---

# VPC Endpoint

A **VPC Endpoint** provides a private connection between resources inside a VPC and supported cloud services.

Traffic does not need to travel through the public Internet.

Example:

```text
Private Server
      |
 VPC Endpoint
      |
 Cloud Service
```

### Benefits

- Keeps traffic private
- Reduces Internet exposure
- Can improve security
- Can reduce the need for NAT for certain cloud services

---

# Security Rules

Cloud networks use virtual firewall rules to control communication.

Rules can often be defined using information such as:

- Source IP address
- Destination IP address
- TCP or UDP protocol
- Port number
- IPv4 or IPv6 address ranges

Two important types of rules are:

### Ingress

Controls traffic entering a resource or network.

### Egress

Controls traffic leaving a resource or network.

---

# Network Security List

A **Network Security List** contains firewall rules that control which traffic is allowed into and out of a subnet.

Example:

```text
Ingress:
Allow TCP 443 from Internet
Allow TCP 22 from administrator network

Egress:
Allow outbound HTTPS traffic
```

Security lists generally apply rules at the subnet level.

---

# Network Security Group

A **Network Security Group (NSG)** provides more granular security control.

Instead of applying the same rules to every resource inside a subnet, rules can be assigned to specific virtual network interfaces or resources.

Example:

```text
Same Subnet

Web Server
→ Allow ports 80 and 443

Database Server
→ Allow port 3306 only from Web Server
```

This means two resources can exist in the same subnet but have different security rules.

---

# Security List vs Security Group

```text
Security List
→ Usually applies rules to a subnet

Network Security Group
→ Applies rules to selected resources/interfaces
```

Exact terminology and implementation can differ between cloud providers.

---

# Key Takeaways

- **Elasticity** → automatically or dynamically scale resources based on demand
- **Multitenancy** → multiple customers share cloud infrastructure while remaining isolated
- **NFV** → replaces physical network appliances with virtual network functions
- **VPC** → private virtual network inside a public cloud
- **Transit Gateway** → connects multiple VPCs or networks
- **VPN** → provides secure remote connectivity
- **Internet Gateway** → provides Internet connectivity for appropriate VPC resources
- **NAT Gateway** → gives private resources outbound Internet access
- **VPC Endpoint** → provides private access to supported cloud services
- **Security List** → subnet-level firewall rules
- **Network Security Group** → more granular security rules for selected resources
