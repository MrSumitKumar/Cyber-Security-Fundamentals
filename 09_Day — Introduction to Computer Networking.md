# Day 09 — Introduction to Computer Networking

**Course:** Cyber Security & Ethical Hacking Professional Program
**Module:** Networking Fundamentals
**Day:** 09
**Topic:** Introduction to Computer Networking
**Level:** Beginner → Intermediate
**Recommended Duration:** 2–3 Hours

---

# 1. Learning Objectives

By the end of Day 09, students will understand:

* What a computer network is
* Why networking is important in cyber security
* LAN, WAN, MAN and PAN
* Network devices
* Client-server and peer-to-peer models
* Network topology
* OSI model
* TCP/IP model
* IP addresses
* IPv4 basics
* MAC addresses
* Ports
* Protocols
* Packets
* Basic network communication
* Basic Windows networking commands
* The relationship between networking and ethical hacking

> **Security Rule:** All practical activities must be performed on your own computer, your own network, or an explicitly authorized lab.

---

# 2. Why Networking Is Important in Cyber Security

Almost every modern cyber attack involves a network at some stage.

Consider a simple scenario:

```text
User
 ↓
Computer
 ↓
Local Network
 ↓
Router
 ↓
Internet
 ↓
Web Server
```

If you want to understand:

* Network attacks
* Firewalls
* Port scanning
* Network monitoring
* Web security
* Remote access
* SOC operations
* Packet analysis
* Intrusion detection
* Penetration testing

you need a strong networking foundation.

Therefore:

> **Networking is one of the most important foundations of cyber security.**

---

# 3. What Is a Computer Network?

A **computer network** is a collection of devices that communicate with each other using defined communication protocols.

Example:

```text
        Network
           │
    ┌──────┼──────┐
    ▼      ▼      ▼
   PC     Laptop  Phone
    │       │      │
    └───────┼──────┘
            ▼
          Router
            │
         Internet
```

Devices can communicate to:

* Exchange data
* Access applications
* Share resources
* Access the internet
* Communicate with servers

---

# 4. Network Components

A basic network may contain:

| Component           | Purpose                             |
| ------------------- | ----------------------------------- |
| Computer            | End device                          |
| Laptop              | End device                          |
| Smartphone          | End device                          |
| Server              | Provides services                   |
| Switch              | Connects devices in a LAN           |
| Router              | Connects networks                   |
| Access Point        | Provides wireless connectivity      |
| Firewall            | Controls network traffic            |
| Network Interface   | Allows device to connect to network |
| Transmission Medium | Carries data                        |

---

# 5. End Devices

Devices that originate or receive network communication are called **end devices**.

Examples:

```text
Computer
Laptop
Mobile
Printer
Server
IP Camera
IoT Device
```

Example:

```text
Laptop
   │
   │ request
   ▼
Web Server
   │
   │ response
   ▼
Laptop
```

---

# 6. Network Types

Networks can be classified based on size and purpose.

Important types:

```text
PAN
LAN
MAN
WAN
```

---

# 7. PAN — Personal Area Network

**PAN = Personal Area Network**

A PAN is a small network around an individual.

Example:

```text
        Smartphone
          /     \
         /       \
   Smartwatch   Earbuds
```

Technologies may include:

* Bluetooth
* USB
* Personal hotspot

---

# 8. LAN — Local Area Network

**LAN = Local Area Network**

A LAN covers a relatively limited area.

Examples:

* Home network
* School lab
* Office
* Computer institute

Example:

```text
             Switch
          /    |    \
         /     |     \
       PC1    PC2    PC3
```

MSK Institute's computer lab can be an example of a LAN.

---

# 9. MAN — Metropolitan Area Network

**MAN = Metropolitan Area Network**

A MAN generally covers a larger geographic area than a LAN, often across parts of a city or metropolitan region.

Conceptually:

```text
Building A ─── Building B
      \          /
       \        /
        Building C
```

The exact boundaries of a MAN can vary depending on the network design.

---

# 10. WAN — Wide Area Network

**WAN = Wide Area Network**

A WAN connects networks across large geographic distances.

Example:

```text
Delhi Network
      │
      │
Internet / WAN
      │
      │
Mumbai Network
      │
      │
Bangalore Network
```

The **Internet** is the world's largest interconnected network.

---

# 11. LAN vs WAN

| Feature   | LAN                                      | WAN                            |
| --------- | ---------------------------------------- | ------------------------------ |
| Coverage  | Small area                               | Large area                     |
| Example   | Office                                   | Multiple cities                |
| Speed     | Usually high within local infrastructure | Varies                         |
| Ownership | Often organization/private               | May involve multiple providers |
| Example   | School lab                               | Internet                       |

---

# 12. Client-Server Model

In the client-server model:

```text
Client
   │
   │ Request
   ▼
Server
   │
   │ Response
   ▼
Client
```

### Client

Requests a service.

### Server

Provides a service.

Example:

When you open a website:

```text
Browser
   ↓
Web Request
   ↓
Web Server
   ↓
Web Response
   ↓
Browser
```

---

# 13. Examples of Servers

Common server types include:

* Web server
* DNS server
* File server
* Database server
* Mail server
* Authentication server
* Application server

Later in the course, you will study these services from a security perspective.

---

# 14. Peer-to-Peer Network

In a peer-to-peer model, devices can communicate directly without requiring a dedicated central server for every service.

Example:

```text
PC A ───── PC B
 │           │
 └─────┬─────┘
       │
      PC C
```

Each device can potentially act as both a client and provider of resources.

---

# 15. Client-Server vs Peer-to-Peer

| Feature        | Client-Server                         | Peer-to-Peer                  |
| -------------- | ------------------------------------- | ----------------------------- |
| Central server | Usually yes                           | Not necessarily               |
| Management     | Centralized                           | More distributed              |
| Scalability    | Generally better for managed services | Can become difficult at scale |
| Example        | Website                               | Small file-sharing network    |

---

# 16. Network Topology

**Topology** describes how devices are arranged or connected.

Common topologies:

* Bus
* Star
* Ring
* Mesh
* Tree

---

# 17. Star Topology

A very common modern LAN design is a star-like topology.

```text
             PC1
              │
              │
PC2 ─────── Switch ─────── PC3
              │
              │
             PC4
```

The switch acts as a central connection point.

Advantages:

* Easy to manage
* Easy to add devices
* Failure of one cable usually affects only one device

Potential disadvantage:

* Failure of the central switch can affect connected devices.

---

# 18. Mesh Topology

In a mesh topology, devices can have multiple connections.

Simplified:

```text
A ───── B
│ \     │
│  \    │
│   \   │
C ───── D
```

Mesh designs can provide redundancy but may require more infrastructure.

---

# 19. Network Devices

Let's understand the major devices.

### NIC

**NIC = Network Interface Card/Controller**

Allows a computer to connect to a network.

```text
Computer
   ↓
NIC
   ↓
Network
```

---

# 20. Switch

A **switch** connects devices within a network.

Example:

```text
PC1 ─┐
PC2 ─┼── Switch
PC3 ─┤
PC4 ─┘
```

A switch primarily operates at the **Data Link Layer** in the traditional OSI model, although modern switches can provide functions across multiple layers.

---

# 21. Router

A router connects different networks.

Example:

```text
LAN
 │
 ▼
Router
 │
 ▼
Internet
```

A router decides where network packets should be forwarded based on routing information.

---

# 22. Switch vs Router

| Switch                                                              | Router                            |
| ------------------------------------------------------------------- | --------------------------------- |
| Connects devices within a network                                   | Connects different networks       |
| Primarily associated with Layer 2                                   | Primarily associated with Layer 3 |
| Uses MAC addresses for forwarding in traditional Ethernet switching | Uses IP addressing/routing        |
| Common inside LANs                                                  | Connects LANs/WANs                |

Modern networking equipment can combine multiple functions, so these are conceptual distinctions.

---

# 23. Wireless Access Point

An **Access Point (AP)** provides wireless connectivity to a network.

Example:

```text
Laptop ))))
         \
Phone )))) → Access Point → Network
         /
Tablet ))))
```

A home Wi-Fi router often combines:

* Router
* Switch
* Wireless access point
* Firewall
* DHCP server

in one device.

---

# 24. Firewall

A firewall controls network traffic according to security rules.

Example:

```text
Internet
   │
   ▼
Firewall
   │
   ▼
Internal Network
```

A firewall may inspect traffic based on factors such as:

* Source
* Destination
* Protocol
* Port
* Connection state
* Application, depending on firewall capabilities

---

# 25. What Is an IP Address?

An **IP address** identifies a network interface/address within an IP network.

IPv4 example:

```text
192.168.1.10
```

Another example:

```text
10.0.0.25
```

An IP address allows network devices to identify the logical destination of IP traffic.

---

# 26. IPv4 Structure

IPv4 uses **32 bits**.

Example:

```text
192.168.1.10
```

It contains four octets:

```text
192    168    1    10
 │       │    │     │
8 bits  8 bits 8 bits 8 bits
```

Therefore:

```text
8 + 8 + 8 + 8 = 32 bits
```

---

# 27. Binary Representation

An IPv4 address is ultimately represented in binary.

Example:

```text
192
```

is:

```text
11000000
```

And:

```text
168
```

is:

```text
10101000
```

So:

```text
192.168.1.10
```

can be represented as:

```text
11000000.10101000.00000001.00001010
```

You will study subnetting and binary calculations in detail later.

---

# 28. Private IPv4 Addresses

Common private IPv4 ranges include:

```text
10.0.0.0/8

172.16.0.0/12

192.168.0.0/16
```

Examples:

```text
10.0.0.5
172.16.10.20
192.168.1.10
```

These are commonly used inside private networks.

---

# 29. Public IP Address

A public IP address is generally used for communication across the public Internet.

Conceptually:

```text
Your Computer
     ↓
Private IP
     ↓
Router/NAT
     ↓
Public IP
     ↓
Internet
```

Your local computer may have a private address while your router uses a public address toward the Internet.

---

# 30. Loopback Address

A loopback address refers to the local computer itself.

For IPv4:

```text
127.0.0.1
```

The hostname commonly associated with it is:

```text
localhost
```

Example:

```text
Browser
   ↓
127.0.0.1
   ↓
Same Computer
```

This is extremely useful for local development and security labs.

---

# 31. MAC Address

A **MAC address** is a link-layer hardware/network interface identifier used in Ethernet and other LAN technologies.

Example format:

```text
00-1A-2B-3C-4D-5E
```

or:

```text
00:1A:2B:3C:4D:5E
```

It is commonly 48 bits for Ethernet interfaces.

---

# 32. IP Address vs MAC Address

| IP Address                          | MAC Address                          |
| ----------------------------------- | ------------------------------------ |
| Network-layer addressing            | Link-layer addressing                |
| Used for routing across IP networks | Used for local network communication |
| IPv4 = 32 bits                      | Ethernet MAC commonly = 48 bits      |
| Can change depending on network     | Associated with network interface    |
| Example: `192.168.1.10`             | Example: `00:1A:2B:3C:4D:5E`         |

---

# 33. Simple Network Communication

Suppose:

```text
PC A
IP: 192.168.1.10
```

wants to communicate with:

```text
PC B
IP: 192.168.1.20
```

Conceptually:

```text
PC A
 │
 │ Data
 ▼
Network
 │
 ▼
PC B
```

The actual communication involves multiple protocols and addressing mechanisms.

---

# 34. What Is a Packet?

Network data is broken into smaller units for transmission.

At the IP layer, these are called **packets**.

Simplified:

```text
Large Data
    ↓
┌────┬────┬────┬────┐
│ P1 │ P2 │ P3 │ P4 │
└────┴────┴────┴────┘
    ↓
Network
    ↓
Destination
    ↓
Reassembled / processed
```

The exact terminology varies by protocol layer; for example, Ethernet uses frames while TCP uses segments.

---

# 35. What Is a Protocol?

A **protocol** is a defined set of rules for communication.

Examples:

| Protocol | Purpose                              |
| -------- | ------------------------------------ |
| HTTP     | Web communication                    |
| HTTPS    | Secure web communication             |
| DNS      | Name resolution                      |
| DHCP     | Automatic IP configuration           |
| TCP      | Reliable transport                   |
| UDP      | Connectionless transport             |
| ICMP     | Network control/diagnostic messaging |
| SSH      | Secure remote administration         |
| SMTP     | Email transfer                       |

---

# 36. TCP

**TCP = Transmission Control Protocol**

TCP provides reliable, ordered delivery of data between endpoints.

Conceptually:

```text
Application
    ↓
TCP
    ↓
IP
    ↓
Network
```

TCP uses mechanisms such as:

* Connection establishment
* Sequencing
* Acknowledgments
* Retransmission
* Flow control

---

# 37. UDP

**UDP = User Datagram Protocol**

UDP provides a simpler connectionless transport mechanism.

It generally has lower protocol overhead than TCP but does not provide TCP's built-in reliable, ordered delivery.

Common applications can include:

* DNS
* Streaming-related traffic
* Real-time communication
* Online gaming

The suitability depends on the specific application.

---

# 38. TCP vs UDP

| TCP                                | UDP                                       |
| ---------------------------------- | ----------------------------------------- |
| Connection-oriented                | Connectionless                            |
| Reliable delivery mechanisms       | No built-in TCP-style reliability         |
| Ordered delivery                   | No guarantee of ordering                  |
| More overhead                      | Lower overhead                            |
| Common for web/application traffic | Common for DNS and real-time applications |

---

# 39. What Is a Port?

A **port number** helps identify a particular service or application endpoint on a host.

TCP and UDP ports range from:

```text
0 – 65535
```

Examples:

| Port | Common Service |
| ---: | -------------- |
|   22 | SSH            |
|   53 | DNS            |
|   80 | HTTP           |
|  443 | HTTPS          |
| 3389 | RDP            |

These are common associations, not guarantees. A service can be configured to use a different port.

---

# 40. IP Address + Port

Think of:

```text
IP address = Which computer/network interface?
Port = Which service/application endpoint?
```

Example:

```text
192.168.1.10:443
```

Conceptually:

```text
192.168.1.10
      │
      └── 443
          │
          ▼
       HTTPS service
```

This concept will become extremely important during ethical hacking and network security.

---

# 41. OSI Model

The **OSI model** provides a conceptual framework for understanding network communication.

It has seven layers:

```text
7. Application
6. Presentation
5. Session
4. Transport
3. Network
2. Data Link
1. Physical
```

Mnemonic:

> **All People Seem To Need Data Processing**

---

# 42. OSI Layer 1 — Physical

Deals with physical transmission.

Examples:

* Cables
* Electrical signals
* Fiber
* Radio signals
* Connectors

```text
Bits
 ↓
Physical medium
```

---

# 43. OSI Layer 2 — Data Link

Responsible for local network communication.

Concepts include:

* Ethernet
* MAC addresses
* Frames
* Switching

Typical device:

```text
Switch
```

---

# 44. OSI Layer 3 — Network

Responsible for logical addressing and routing.

Important concept:

```text
IP
```

Typical device:

```text
Router
```

---

# 45. OSI Layer 4 — Transport

Provides end-to-end transport mechanisms.

Important protocols:

```text
TCP
UDP
```

Ports are associated with transport-layer communication.

---

# 46. OSI Layers 5–7

### Layer 5 — Session

Manages communication sessions conceptually.

### Layer 6 — Presentation

Deals conceptually with:

* Data representation
* Encoding
* Encryption
* Compression

### Layer 7 — Application

Provides network services used by applications.

Examples:

```text
HTTP
DNS
SMTP
SSH
```

---

# 47. OSI Model Summary

| Layer | Name         | Examples/Concepts             |
| ----: | ------------ | ----------------------------- |
|     7 | Application  | HTTP, DNS, SMTP               |
|     6 | Presentation | Encoding, encryption concepts |
|     5 | Session      | Sessions                      |
|     4 | Transport    | TCP, UDP, ports               |
|     3 | Network      | IP, routing                   |
|     2 | Data Link    | Ethernet, MAC, switching      |
|     1 | Physical     | Cable, radio, signals         |

---

# 48. TCP/IP Model

The practical Internet architecture is often represented using the TCP/IP model.

A common four-layer representation is:

```text
Application
Transport
Internet
Network Access
```

Comparison:

```text
OSI                 TCP/IP
────────────────────────────
Application ┐
Presentation├──→ Application
Session     ┘

Transport   ───→ Transport

Network     ───→ Internet

Data Link   ┐
Physical    ┘──→ Network Access
```

---

# 49. OSI vs TCP/IP

The OSI model is primarily a conceptual/reference model.

TCP/IP represents the protocol architecture used by the Internet and many modern networks.

Don't think:

> "The Internet literally has seven physical layers."

Instead, use the models to understand how networking functions are organized.

---

# 50. Encapsulation

When an application sends data, information is added as it moves through networking layers.

Conceptually:

```text
Application Data
      ↓
TCP Header + Data
      ↓
IP Header + TCP Segment
      ↓
Ethernet Header + IP Packet
      ↓
Bits
```

At the receiving side:

```text
Bits
 ↓
Frame
 ↓
IP Packet
 ↓
TCP Segment
 ↓
Application Data
```

This process is called **encapsulation/decapsulation**.

---

# 51. Basic Network Commands — Windows

## Check IP Configuration

```powershell
ipconfig
```

More detailed:

```powershell
ipconfig /all
```

---

# 52. Ping

`ping` can be used to test IP connectivity using ICMP Echo messages where permitted.

Example:

```powershell
ping 127.0.0.1
```

This tests the local TCP/IP stack.

You can also test your gateway if you know its address:

```powershell
ping 192.168.1.1
```

Use only addresses belonging to your own network or systems you are authorized to test.

---

# 53. Tracert

Windows provides:

```powershell
tracert
```

Example:

```powershell
tracert example.com
```

It can help show the path toward a destination.

Network paths can change dynamically, and some routers may not respond to traceroute probes.

---

# 54. NSLookup

DNS converts names into IP addresses.

You can inspect DNS resolution using:

```powershell
nslookup example.com
```

Conceptually:

```text
example.com
     ↓
DNS
     ↓
IP address
```

---

# 55. ARP

ARP is used in IPv4 local networks to map IP addresses to link-layer addresses such as MAC addresses.

Windows command:

```powershell
arp -a
```

This can display your local ARP cache.

Conceptually:

```text
IP Address
    ↓
ARP
    ↓
MAC Address
```

---

# 56. Network Connections

PowerShell can show TCP connections:

```powershell
Get-NetTCPConnection
```

You can inspect:

```text
Local Address
Local Port
Remote Address
Remote Port
State
```

Example concept:

```text
192.168.1.10:51524
        ↓
93.184.216.34:443
```

This means a local endpoint is communicating with a remote endpoint over TCP port 443.

---

# 57. Practical Lab — Network Discovery on Your Own System

## Task 1 — Identify Your Network Configuration

Run:

```powershell
ipconfig /all
```

Record:

```text
IPv4 Address:
Subnet Mask:
Default Gateway:
DNS Servers:
MAC Address:
```

**Do not share this information publicly.**

---

# 58. Task 2 — Test Local TCP/IP

Run:

```powershell
ping 127.0.0.1
```

Expected concept:

```text
Your Computer
     ↓
Loopback
     ↓
Your Computer
```

Question:

> Why does this test not require another computer?

---

# 59. Task 3 — Identify Your Gateway

Run:

```powershell
ipconfig
```

Find:

```text
Default Gateway
```

If it is your own network/router, you may test it:

```powershell
ping <your-gateway>
```

Example:

```powershell
ping 192.168.1.1
```

---

# 60. Task 4 — DNS Resolution

Run:

```powershell
nslookup example.com
```

Record:

```text
DNS Server:
Resolved Address:
```

Then explain:

> Why does DNS matter when accessing websites?

---

# 61. Task 5 — View ARP Cache

Run:

```powershell
arp -a
```

Observe:

```text
Internet Address
Physical Address
Type
```

Answer:

> What relationship between IP addresses and MAC addresses can you observe?

---

# 62. Task 6 — View Network Connections

Run:

```powershell
Get-NetTCPConnection
```

Look at:

```text
LocalAddress
LocalPort
RemoteAddress
RemotePort
State
```

Do **not** attempt to connect to or investigate systems you do not own.

The purpose is to understand how your own computer communicates.

---

# 63. Task 7 — Identify Common Ports

Create this table:

| Port | Protocol | Common Association |
| ---: | -------- | ------------------ |
|   22 | TCP      | SSH                |
|   53 | TCP/UDP  | DNS                |
|   80 | TCP      | HTTP               |
|  443 | TCP      | HTTPS              |
| 3389 | TCP      | RDP                |

Important:

> A port number alone does not prove which application is actually running there.

---

# 64. Task 8 — Draw Your Network

Create a diagram of your own network.

Example:

```text
                 INTERNET
                    │
                    │
              ISP / Modem
                    │
                    ▼
                 Router
               /   |   \
              /    |    \
             PC   Phone  Laptop
```

Label:

* IP addresses where appropriate
* Device types
* Router
* Wireless connection
* Internet connection

Do not include passwords.

---

# 65. Mini Project

# Personal Network Security Map

Create a document containing:

### 1. Network Type

```text
Home / Lab / Office
LAN / WAN
Wired / Wireless
```

### 2. Devices

List:

```text
Router
Laptop
Desktop
Phone
Printer
Other authorized devices
```

### 3. Addressing

Document:

```text
Private IPv4
Gateway
DNS
Subnet
```

Do not publish sensitive network details.

### 4. Network Diagram

```text
Internet
   ↓
Router
   ↓
Switch / Wi-Fi
   ├── PC
   ├── Laptop
   ├── Phone
   └── Printer
```

### 5. Security Controls

Identify:

```text
Firewall
Wi-Fi encryption
Router password
Device passwords
Updates
Antivirus
Guest network
```

### 6. Recommendations

Write five improvements based on your observations.

---

# 66. Assignment

Answer:

1. What is a computer network?
2. What is a LAN?
3. What is a WAN?
4. What is a PAN?
5. What is a router?
6. What is a switch?
7. What is an access point?
8. What is an IP address?
9. What is a MAC address?
10. What is a port?
11. What is a protocol?
12. What is a packet?
13. What is TCP?
14. What is UDP?
15. What is the difference between TCP and UDP?
16. What is the OSI model?
17. Name all seven OSI layers.
18. What is the TCP/IP model?
19. What is encapsulation?
20. What is DNS?
21. What is DHCP?
22. What is ARP?
23. What is `127.0.0.1`?
24. What does `ping` do?
25. What does `tracert` do?
26. What does `nslookup` do?
27. What does `ipconfig` do?
28. What does `arp -a` show?
29. Why is networking knowledge important for cyber security?
30. Why should network testing be performed only on authorized systems?

---

# 67. Quick Quiz

### Q1. What device normally connects different networks?

A. Switch
B. Router
C. Keyboard
D. Monitor

**Answer: B**

---

### Q2. Which address is an IPv4 loopback address?

A. `192.168.1.1`
B. `8.8.8.8`
C. `127.0.0.1`
D. `255.255.255.255`

**Answer: C**

---

### Q3. Which protocol translates domain names into IP addresses?

A. DNS
B. HTTP
C. FTP
D. ARP

**Answer: A**

---

### Q4. Which layer is associated with IP routing in the OSI model?

A. Physical
B. Data Link
C. Network
D. Presentation

**Answer: C**

---

### Q5. Which protocols operate at the transport layer?

A. TCP and UDP
B. HTTP and DNS
C. Ethernet and ARP
D. IP and ICMP

**Answer: A**

---

### Q6. What does a MAC address primarily identify?

A. A website
B. A network interface at the link layer
C. A TCP port
D. A DNS server

**Answer: B**

---

### Q7. Which command displays Windows IP configuration?

A. `ipconfig`
B. `whoami`
C. `tasklist`
D. `hostnamectl`

**Answer: A**

---

### Q8. Which command can perform DNS queries?

A. `arp`
B. `nslookup`
C. `tracert`
D. `whoami`

**Answer: B**

---

### Q9. Which protocol is generally connection-oriented?

A. UDP
B. TCP
C. ARP
D. ICMP

**Answer: B**

---

### Q10. What does a port help identify?

A. A physical cable
B. An application/service endpoint on a host
C. A monitor
D. A keyboard

**Answer: B**

---

# 68. Important Terminology

| Term         | Meaning                                          |
| ------------ | ------------------------------------------------ |
| Network      | Connected devices communicating using protocols  |
| LAN          | Local Area Network                               |
| WAN          | Wide Area Network                                |
| PAN          | Personal Area Network                            |
| Router       | Connects/routs between networks                  |
| Switch       | Connects devices in a LAN                        |
| Access Point | Provides wireless network connectivity           |
| IP           | Internet Protocol                                |
| IPv4         | 32-bit IP addressing system                      |
| MAC          | Link-layer interface address                     |
| Port         | Transport-layer service/application endpoint     |
| Protocol     | Rules for communication                          |
| Packet       | Data unit at the IP/network layer                |
| Frame        | Data-link layer data unit                        |
| TCP          | Reliable, connection-oriented transport protocol |
| UDP          | Connectionless transport protocol                |
| DNS          | Domain Name System                               |
| DHCP         | Dynamic Host Configuration Protocol              |
| ARP          | IPv4 address-to-link-layer address resolution    |
| OSI          | Seven-layer networking reference model           |
| TCP/IP       | Internet protocol architecture                   |
| Gateway      | Device/network path used to reach other networks |
| Loopback     | Local host communication mechanism               |

---

# 69. Day 09 — Final Concept

The complete networking picture can be visualized as:

```text
                    INTERNET
                       │
                       ▼
                    ROUTER
                       │
                ┌──────┴──────┐
                ▼             ▼
             SWITCH        Wi-Fi AP
                │             │
          ┌─────┼─────┐    ┌──┴──┐
          ▼     ▼     ▼    ▼     ▼
         PC1   PC2   PC3 Phone Laptop
          │
          ▼
        NIC
          │
          ▼
       MAC Address
          │
          ▼
       IP Address
          │
          ▼
      TCP / UDP
          │
          ▼
         Port
          │
          ▼
       Application
```

And conceptually, network communication passes through layers:

```text
Application
     ↓
Transport
     ↓
Internet / Network
     ↓
Data Link
     ↓
Physical
```

---

# 70. Cyber Security Connection

Today you learned the foundation required for many future topics:

```text
Networking
    │
    ├── IP Addresses
    │
    ├── MAC Addresses
    │
    ├── Ports
    │
    ├── Protocols
    │
    ├── Packets
    │
    ├── Routers
    │
    └── Firewalls
             │
             ▼
       Cyber Security
             │
      ┌──────┼──────┐
      ▼      ▼      ▼
    SOC    Pentest  Network
                    Security
```

### Core Principle

> **Before learning how to secure or test a network, you must first understand how normal network communication works.**

---
