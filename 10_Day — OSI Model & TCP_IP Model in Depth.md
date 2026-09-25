# Day 10 — OSI Model & TCP/IP Model in Depth

**Course:** Cyber Security & Ethical Hacking Professional Program
**Module:** Networking Fundamentals
**Day:** 10
**Topic:** OSI Model & TCP/IP Model in Depth
**Level:** Beginner → Intermediate
**Recommended Duration:** 2.5–3 Hours

---

# 1. Learning Objectives

By the end of Day 10, students will understand:

* Why networking models are needed
* OSI model in detail
* TCP/IP model in detail
* Relationship between OSI and TCP/IP
* Data units at different layers
* Headers and trailers
* Encapsulation and decapsulation
* MAC address vs IP address vs port
* TCP and UDP positioning
* How a web request travels through a network
* How switches and routers process traffic
* Basic troubleshooting using the OSI model
* Why the OSI model is useful in cyber security

---

# 2. Revision — Day 09

Yesterday we learned:

```text
Network
LAN / WAN
Router
Switch
IP Address
MAC Address
Port
TCP
UDP
DNS
DHCP
ARP
OSI Model
TCP/IP Model
Packets
```

Today we will go much deeper into how these concepts work together.

---

# 3. Why Do We Need Networking Models?

Imagine trying to build a communication system where:

* One company designs cables
* Another designs IP
* Another designs applications
* Another designs encryption
* Another designs transport protocols

Without a common structure, interoperability would become difficult.

Networking models provide a common way to organize networking functions.

Think of:

```text
Application
     ↓
Transport
     ↓
Network
     ↓
Data Link
     ↓
Physical
```

Each layer has a specific responsibility.

---

# 4. Real-Life Analogy — Sending a Parcel

Suppose you want to send a package.

```text
You
 ↓
Write message
 ↓
Pack it
 ↓
Add address
 ↓
Choose delivery method
 ↓
Transport
 ↓
Road
 ↓
Destination
```

Networking works similarly.

```text
Application Data
      ↓
Transport
      ↓
IP
      ↓
Ethernet
      ↓
Physical Signals
```

The receiving system performs the reverse process.

---

# 5. OSI Model — Seven Layers

The OSI model has seven layers:

```text
7 → Application
6 → Presentation
5 → Session
4 → Transport
3 → Network
2 → Data Link
1 → Physical
```

Mnemonic:

> **All People Seem To Need Data Processing**

Another:

> **Please Do Not Throw Sausage Pizza Away**

Both are commonly used to remember the order.

---

# 6. OSI Layer 7 — Application

The Application layer provides network services to applications.

Examples:

```text
HTTP
HTTPS
DNS
SMTP
FTP
SSH
```

Important:

> The OSI Application layer is not simply "the application itself."

It represents network functionality available to applications.

---

# 7. Example — Browser

Suppose you open:

```text
https://example.com
```

Your browser needs network protocols.

Conceptually:

```text
Browser
   ↓
HTTPS
   ↓
Transport
   ↓
IP
   ↓
Ethernet/Wi-Fi
   ↓
Physical Network
```

---

# 8. OSI Layer 6 — Presentation

The Presentation layer is concerned conceptually with data representation.

Examples include:

* Encoding
* Data format
* Compression
* Encryption/decryption concepts

Example:

```text
Application Data
       ↓
Encoding / Encryption
       ↓
Network Transmission
```

In real TCP/IP implementations, these responsibilities are often handled by application protocols and libraries rather than a distinct layer.

---

# 9. OSI Layer 5 — Session

The Session layer deals conceptually with establishing, managing and terminating communication sessions.

Think:

```text
Session Start
     ↓
Communication
     ↓
Session Management
     ↓
Session End
```

Again, modern Internet protocols do not always map neatly to a single OSI layer.

---

# 10. OSI Layer 4 — Transport

The Transport layer provides end-to-end transport between applications.

Important protocols:

```text
TCP
UDP
```

It also uses **port numbers**.

Example:

```text
Computer
    │
    ├── Port 443 → HTTPS
    ├── Port 53  → DNS
    └── Port 22  → SSH
```

---

# 11. TCP — Transmission Control Protocol

TCP provides mechanisms for reliable, ordered communication.

Important concepts:

```text
Connection
Sequence Numbers
Acknowledgments
Retransmission
Flow Control
```

Simplified:

```text
Sender
  │
  │ Data
  ▼
Network
  │
  ▼
Receiver
  │
  │ ACK
  ▼
Sender
```

If data is lost, TCP can retransmit it.

---

# 12. TCP Three-Way Handshake

Before normal TCP data exchange, endpoints generally establish a connection using a handshake.

Simplified:

```text
Client                         Server

   SYN ───────────────────────►

       ◄──────────────── SYN-ACK

   ACK ───────────────────────►

          Connection Ready
```

### Step 1 — SYN

Client requests to establish a TCP connection.

### Step 2 — SYN-ACK

Server acknowledges and responds.

### Step 3 — ACK

Client acknowledges.

Then data transfer can begin.

---

# 13. Why the TCP Handshake Matters in Cyber Security

Security professionals may observe TCP connection behavior when investigating:

* Network problems
* Firewalls
* Scanning activity
* Suspicious connections
* Application behavior
* Network logs

Understanding normal TCP behavior helps identify abnormal patterns.

---

# 14. UDP

UDP is a connectionless transport protocol.

Simplified:

```text
Sender
  │
  │ UDP Datagram
  ▼
Network
  │
  ▼
Receiver
```

UDP does not provide TCP-style:

* Connection establishment
* Guaranteed delivery
* Ordered delivery
* Retransmission

This makes UDP useful for applications where low overhead or timing is important.

---

# 15. TCP vs UDP

| Feature         | TCP                 | UDP                      |
| --------------- | ------------------- | ------------------------ |
| Connection      | Connection-oriented | Connectionless           |
| Reliability     | Built-in mechanisms | No TCP-style reliability |
| Ordering        | Yes                 | Not guaranteed           |
| Retransmission  | Yes                 | No                       |
| Overhead        | Higher              | Lower                    |
| Common examples | HTTPS, SSH          | DNS, real-time traffic   |

Remember:

> "UDP is faster" is an oversimplification. Application performance depends on many factors.

---

# 16. Ports

Ports identify application/service endpoints at the transport layer.

Range:

```text
0 – 65535
```

Common examples:

|  Port | Common Protocol |
| ----: | --------------- |
| 20/21 | FTP             |
|    22 | SSH             |
|    23 | Telnet          |
|    25 | SMTP            |
|    53 | DNS             |
|    80 | HTTP            |
|   443 | HTTPS           |
|  3389 | RDP             |

These are **common associations**, not proof that a particular service is running on a port.

---

# 17. Source Port and Destination Port

Consider:

```text
192.168.1.10:51524
        ↓
93.184.216.34:443
```

Here:

```text
Source IP      = 192.168.1.10
Source Port    = 51524

Destination IP = 93.184.216.34
Destination Port = 443
```

Conceptually:

```text
WHO?
 ↓
IP Address

WHICH SERVICE?
 ↓
Port
```

---

# 18. OSI Layer 3 — Network

Layer 3 is associated with logical addressing and routing.

Important protocol:

```text
IP
```

Important device:

```text
Router
```

Example:

```text
Network A
   │
   ▼
Router
   │
   ▼
Network B
```

The router determines how packets should move between networks.

---

# 19. IP Packet

An IP packet contains an IP header and payload.

Simplified:

```text
┌─────────────────────────────┐
│       IP Header             │
├─────────────────────────────┤
│                             │
│        Payload              │
│                             │
└─────────────────────────────┘
```

The IP header can contain information such as:

* Source IP
* Destination IP
* TTL
* Protocol
* Other control information

---

# 20. Source and Destination IP

Example:

```text
Source IP
192.168.1.10

Destination IP
93.184.216.34
```

Conceptually:

```text
192.168.1.10
      │
      │ Packet
      ▼
93.184.216.34
```

Routers use destination IP information to help forward traffic.

---

# 21. TTL — Time To Live

IP packets contain a TTL field.

TTL helps prevent packets from circulating indefinitely due to routing problems.

Conceptually:

```text
Packet
TTL = 64

Router 1
TTL ↓

Router 2
TTL ↓

Router 3
TTL ↓
```

When TTL reaches zero, the packet is discarded.

TTL is also useful when understanding tools such as `tracert`.

---

# 22. OSI Layer 2 — Data Link

Layer 2 deals with local network delivery.

Important concepts:

```text
Ethernet
MAC Address
Frames
Switching
```

A switch commonly uses MAC addresses to make forwarding decisions in an Ethernet LAN.

---

# 23. Ethernet Frame

A simplified Ethernet frame:

```text
┌──────────────┬──────────────┬──────────────┐
│ Ethernet     │ IP Packet    │ FCS          │
│ Header       │              │              │
└──────────────┴──────────────┴──────────────┘
```

The Ethernet header can include:

```text
Source MAC
Destination MAC
```

The exact frame structure contains additional fields.

---

# 24. MAC Address

Example:

```text
00:1A:2B:3C:4D:5E
```

At the local network level:

```text
Source MAC
      ↓
Switch
      ↓
Destination MAC
```

A switch can use its MAC address table to determine where to forward Ethernet frames.

---

# 25. MAC Address Table

Imagine a switch learns:

```text
MAC Address          Port
────────────────────────────
AA:AA:AA:AA:AA:AA    Port 1
BB:BB:BB:BB:BB:BB    Port 2
CC:CC:CC:CC:CC:CC    Port 3
```

Then:

```text
Frame Destination
       ↓
MAC Table Lookup
       ↓
Correct Switch Port
```

This is the basic idea behind Layer 2 switching.

---

# 26. OSI Layer 1 — Physical

Layer 1 deals with transmission of raw bits.

Examples:

```text
Copper cable
Fiber optic
Radio waves
Connectors
Electrical signals
Optical signals
```

Conceptually:

```text
1010101010010101
       ↓
Physical Medium
       ↓
1010101010010101
```

---

# 27. Data Units at Different Layers

This is extremely important.

| Layer       | Common Data Unit               |
| ----------- | ------------------------------ |
| Application | Data                           |
| Transport   | Segment (TCP) / Datagram (UDP) |
| Network     | Packet                         |
| Data Link   | Frame                          |
| Physical    | Bits                           |

Visualize:

```text
DATA
  ↓
SEGMENT
  ↓
PACKET
  ↓
FRAME
  ↓
BITS
```

---

# 28. Encapsulation

When data travels from an application toward the network:

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

Each layer adds information needed for communication.

This is called:

> **Encapsulation**

---

# 29. Decapsulation

At the receiving system, the reverse process happens.

```text
Bits
 ↓
Frame
 ↓
Packet
 ↓
TCP Segment
 ↓
Application Data
```

This is called:

> **Decapsulation**

---

# 30. Complete Encapsulation Diagram

```text
                 SENDER
─────────────────────────────────────────

Application
    │
    ▼
┌──────────────────────┐
│ Application Data     │
└──────────────────────┘
    │
    ▼
┌──────────────────────┐
│ TCP │ Data           │
└──────────────────────┘
    │
    ▼
┌──────────────────────────────┐
│ IP │ TCP │ Data              │
└──────────────────────────────┘
    │
    ▼
┌──────────────────────────────────────┐
│ Ethernet │ IP │ TCP │ Data │ FCS    │
└──────────────────────────────────────┘
    │
    ▼
              BITS
```

---

# 31. Receiver Side

```text
                 RECEIVER
─────────────────────────────────────────

BITS
 ↓
Ethernet Frame
 ↓
IP Packet
 ↓
TCP Segment
 ↓
Application Data
 ↓
Application
```

The receiver removes/handles the headers appropriate to each layer.

---

# 32. OSI vs TCP/IP Model

### OSI

```text
7 Application
6 Presentation
5 Session
4 Transport
3 Network
2 Data Link
1 Physical
```

### TCP/IP

```text
Application
Transport
Internet
Network Access
```

Comparison:

```text
OSI                     TCP/IP
──────────────────────────────────
Application ┐
Presentation├───────── Application
Session     ┘

Transport   ────────── Transport

Network     ────────── Internet

Data Link   ┐
Physical    ┘───────── Network Access
```

---

# 33. Why Security Professionals Use the OSI Model

The OSI model helps classify problems.

Example:

### Problem 1

Cable disconnected.

Likely:

```text
Layer 1
```

### Problem 2

Switch cannot reach a device at Layer 2.

Potentially:

```text
Layer 2
```

### Problem 3

Incorrect IP configuration.

Likely:

```text
Layer 3
```

### Problem 4

TCP connection fails.

Potentially:

```text
Layer 4
```

### Problem 5

Web application returns an error.

Potentially:

```text
Layer 7
```

This is a troubleshooting framework, not a rigid rule.

---

# 34. Security Attacks by Layer — High-Level View

Cyber attacks can involve different layers.

| Layer       | Example Security Concern        |
| ----------- | ------------------------------- |
| Physical    | Unauthorized physical access    |
| Data Link   | ARP-related attacks             |
| Network     | IP/routing attacks              |
| Transport   | Port abuse / connection attacks |
| Application | Web application vulnerabilities |

We will study these topics later.

Today we are focusing on understanding the architecture, not performing attacks.

---

# 35. How a Website Request Works

Let's understand what happens when you visit:

```text
https://example.com
```

---

## Step 1 — Application

Your browser prepares an HTTPS request.

```text
Browser
  ↓
HTTPS
```

---

## Step 2 — DNS

The browser/system needs the IP address associated with the domain.

```text
example.com
     ↓
DNS
     ↓
IP Address
```

---

## Step 3 — Transport

The application communicates using a transport protocol such as TCP for traditional HTTPS over TCP.

```text
TCP
Destination Port: 443
```

Modern HTTPS can also use HTTP/3 over QUIC, which uses UDP. The exact transport depends on the protocol/version negotiated.

---

## Step 4 — Network

IP handles addressing.

```text
Source IP
    ↓
Destination IP
```

---

## Step 5 — Data Link

The local network uses technologies such as Ethernet or Wi-Fi.

```text
Source MAC
     ↓
Destination MAC
```

---

## Step 6 — Physical

Data becomes signals over:

* Cable
* Fiber
* Wi-Fi radio

---

# 36. Complete Web Request

```text
                     WEBSITE REQUEST

Browser
   │
   ▼
HTTPS / HTTP
   │
   ▼
TCP or QUIC
   │
   ▼
IP
   │
   ▼
Ethernet / Wi-Fi
   │
   ▼
Physical Network
   │
   ▼
Router
   │
   ▼
Internet
   │
   ▼
Web Server
```

The response travels back through the networking stack.

---

# 37. MAC vs IP vs Port

This is one of the most important concepts from today's lesson.

Think:

```text
MAC Address
     ↓
"Which device/interface on this local network?"

IP Address
     ↓
"Which host/network destination?"

Port
     ↓
"Which application/service endpoint?"
```

Example:

```text
MAC
00:11:22:33:44:55

IP
192.168.1.10

Port
443
```

Together they help describe where communication is happening at different layers.

---

# 38. Switch vs Router — Deeper Understanding

Suppose:

```text
PC1
IP: 192.168.1.10

PC2
IP: 192.168.1.20
```

They are on the same local network.

A switch can forward Ethernet frames based on MAC addresses.

Now:

```text
PC
192.168.1.10
      ↓
Router
      ↓
8.8.8.8
```

The destination is outside the local network.

The router performs Layer 3 forwarding based on IP routing information.

---

# 39. Default Gateway

A **default gateway** is typically the router/interface a host uses to reach destinations outside its local subnet.

Example:

```text
PC
192.168.1.10
       │
       │
Gateway
192.168.1.1
       │
       ▼
Internet
```

Without an appropriate route/default gateway, a device may be unable to reach external networks.

---

# 40. Practical Lab — OSI & TCP/IP

## Task 1 — Identify Your IP Information

Run:

```powershell
ipconfig /all
```

Record:

```text
IPv4:
Subnet Mask:
Default Gateway:
DNS:
MAC Address:
```

Do not share sensitive network information publicly.

---

# 41. Task 2 — Test Loopback

Run:

```powershell
ping 127.0.0.1
```

Answer:

1. Which device is being contacted?
2. Does the packet leave your computer?
3. Which networking concept does `127.0.0.1` represent?

Expected concept:

```text
Computer
   ↓
Loopback
   ↓
Same Computer
```

---

# 42. Task 3 — Test Your Gateway

Find the default gateway:

```powershell
ipconfig
```

Then, if it is a device on your own network:

```powershell
ping <gateway-ip>
```

Example:

```powershell
ping 192.168.1.1
```

Observe the result.

---

# 43. Task 4 — DNS Investigation

Run:

```powershell
nslookup example.com
```

Record:

```text
DNS Server:
Domain:
Returned IP:
```

Draw:

```text
Browser
   ↓
DNS Query
   ↓
DNS Server
   ↓
IP Address
```

---

# 44. Task 5 — View TCP Connections

Run:

```powershell
Get-NetTCPConnection
```

Identify several entries containing:

```text
LocalPort
RemotePort
State
```

Look for commonly used ports such as:

```text
443
80
53
```

Do not assume that every entry on a port represents the expected service.

---

# 45. Task 6 — Inspect a Process

Run:

```powershell
Get-Process
```

Select a process that you recognize.

Record:

```text
Process Name:
PID:
CPU:
Memory:
```

Then conceptually connect:

```text
Process
   ↓
Network Connection
   ↓
Local Port
   ↓
Remote IP
   ↓
Remote Port
```

This relationship becomes extremely useful in security investigations.

---

# 46. Task 7 — Trace a Route

Run:

```powershell
tracert example.com
```

Observe the hops.

Conceptually:

```text
Your Computer
      ↓
Gateway
      ↓
ISP
      ↓
Intermediate Routers
      ↓
Destination
```

Some hops may show timeouts or hidden addresses. This does not automatically mean the network is broken; routers may simply not respond to these diagnostic probes.

---

# 47. Task 8 — Build an OSI Mapping Table

Complete:

| Concept  | OSI Layer |
| -------- | --------: |
| Ethernet |           |
| IP       |           |
| TCP      |           |
| UDP      |           |
| MAC      |           |
| Router   |           |
| Switch   |           |
| Cable    |           |
| HTTP     |           |
| Port     |           |

### Suggested answers

```text
Ethernet → Layer 2
IP       → Layer 3
TCP      → Layer 4
UDP      → Layer 4
MAC      → Layer 2
Router   → Layer 3
Switch   → Layer 2
Cable    → Layer 1
HTTP     → Layer 7
Port     → Layer 4
```

Remember that modern devices can operate across multiple layers.

---

# 48. Mini Project

# Network Communication Analysis

Create a report titled:

> **How a Web Request Travels Through a Network**

Your report should contain:

### Section 1 — User Action

```text
User opens browser
       ↓
https://example.com
```

### Section 2 — DNS

Explain:

```text
Domain
 ↓
DNS
 ↓
IP
```

### Section 3 — Transport

Explain:

```text
TCP/QUIC
 ↓
Port 443
```

### Section 4 — Network

Explain:

```text
Source IP
 ↓
Routers
 ↓
Destination IP
```

### Section 5 — Data Link

Explain:

```text
MAC addresses
 ↓
Ethernet/Wi-Fi
```

### Section 6 — Physical

Explain:

```text
Electrical / optical / radio signals
```

### Section 7 — Encapsulation

Draw:

```text
Data
 ↓
Segment/Datagram
 ↓
Packet
 ↓
Frame
 ↓
Bits
```

### Section 8 — Decapsulation

Explain how the destination processes the received information.

---

# 49. Assignment

Answer the following:

1. Why do networking models exist?
2. Name all seven OSI layers.
3. Explain Layer 1.
4. Explain Layer 2.
5. Explain Layer 3.
6. Explain Layer 4.
7. Explain Layers 5–7.
8. What is encapsulation?
9. What is decapsulation?
10. What is a TCP segment?
11. What is an IP packet?
12. What is an Ethernet frame?
13. What are bits?
14. What is a TCP handshake?
15. What is a UDP datagram?
16. What is a port?
17. What is a source port?
18. What is a destination port?
19. What is the difference between IP and MAC addresses?
20. What is a default gateway?
21. What is TTL?
22. What is the purpose of a switch?
23. What is the purpose of a router?
24. What is the TCP/IP model?
25. Why is the OSI model useful to cyber security professionals?

---

# 50. Quick Quiz

### Q1. How many layers does the OSI model have?

A. 4
B. 5
C. 7
D. 8

**Answer: C**

---

### Q2. Which layer is associated with TCP?

A. Layer 1
B. Layer 2
C. Layer 3
D. Layer 4

**Answer: D**

---

### Q3. Which layer is associated with IP?

A. Layer 1
B. Layer 2
C. Layer 3
D. Layer 7

**Answer: C**

---

### Q4. Which layer is associated with Ethernet?

A. Layer 1/2 concepts
B. Layer 3
C. Layer 4
D. Layer 7

**Answer: A**

---

### Q5. What is the data unit commonly associated with TCP?

A. Frame
B. Segment
C. Bit
D. Packet

**Answer: B**

---

### Q6. What is the data unit commonly associated with IP?

A. Packet
B. Frame
C. Segment
D. Bit

**Answer: A**

---

### Q7. What is the data unit commonly associated with Ethernet?

A. Packet
B. Segment
C. Frame
D. Datagram

**Answer: C**

---

### Q8. Which protocol generally uses a three-way handshake?

A. UDP
B. TCP
C. ARP
D. DNS

**Answer: B**

---

### Q9. Which address operates primarily at the Data Link layer?

A. IP
B. MAC
C. Port
D. URL

**Answer: B**

---

### Q10. What does encapsulation mean?

A. Adding protocol information as data moves down the networking stack
B. Deleting all headers
C. Blocking network traffic
D. Assigning an IP address

**Answer: A**

---

# 51. Important Terminology

| Term          | Meaning                                                        |
| ------------- | -------------------------------------------------------------- |
| OSI           | Open Systems Interconnection reference model                   |
| TCP/IP        | Internet protocol architecture                                 |
| Encapsulation | Adding protocol information as data moves down layers          |
| Decapsulation | Processing/removing protocol information at the receiving side |
| Segment       | Common term for TCP transport data                             |
| Datagram      | Common term for UDP transport data                             |
| Packet        | Network-layer data unit                                        |
| Frame         | Data-link-layer data unit                                      |
| Bit           | Basic binary data unit                                         |
| Header        | Control information placed before payload                      |
| Payload       | Actual carried data                                            |
| MAC           | Link-layer interface address                                   |
| IP            | Network-layer logical address                                  |
| Port          | Transport-layer endpoint identifier                            |
| TTL           | IP packet lifetime/hop limit mechanism                         |
| Handshake     | Protocol exchange used to establish communication              |
| Gateway       | Path/device used to reach another network                      |

---

# 52. Day 10 Final Concept

You should now be able to visualize a network request like this:

```text
                         APPLICATION
                              │
                         HTTP / HTTPS
                              │
                              ▼
                         TRANSPORT
                         TCP / UDP
                              │
                         Source Port
                         Destination Port
                              │
                              ▼
                           NETWORK
                              │
                              IP
                              │
                     Source / Destination
                              │
                              ▼
                         DATA LINK
                              │
                         Ethernet/Wi-Fi
                              │
                         Source/Dest MAC
                              │
                              ▼
                          PHYSICAL
                              │
                    Electrical / Radio / Light
                              │
                              ▼
                           NETWORK
                              │
                              ▼
                         DESTINATION
```

And the encapsulation process:

```text
┌──────────────────────────────┐
│ Application Data             │
└──────────────────────────────┘
              ↓
┌──────────────────────────────┐
│ TCP/UDP │ Application Data   │
└──────────────────────────────┘
              ↓
┌────────────────────────────────────┐
│ IP │ TCP/UDP │ Application Data   │
└────────────────────────────────────┘
              ↓
┌─────────────────────────────────────────────┐
│ Ethernet │ IP │ TCP/UDP │ Application Data │
└─────────────────────────────────────────────┘
              ↓
                    BITS
```

---

# 53. Cyber Security Connection

This knowledge becomes the foundation for future topics:

```text
OSI / TCP-IP
      │
      ├── IP Addressing
      │
      ├── MAC Addressing
      │
      ├── Ports
      │
      ├── TCP/UDP
      │
      ├── Packets
      │
      ├── Routing
      │
      └── Protocols
             │
             ▼
       Network Security
             │
       ┌─────┼─────┐
       ▼     ▼     ▼
     Firewall SOC  Pentesting
       │     │     │
       └─────┼─────┘
             ▼
       Ethical Hacking
```

### Core Principle

> **A cyber security professional must be able to look at a communication and ask: Which application is communicating, which transport protocol is being used, which ports are involved, which IP addresses are involved, how is the traffic moving between networks, and what happens at the local link layer?**

That is the purpose of understanding the OSI and TCP/IP models.

---

## Course Progress

```text
Day 01 → Cyber Security Fundamentals
Day 02 → Cyber Security Domains & Career Paths
Day 03 → Computer & Operating System Fundamentals
Day 04 → Computer Hardware & System Architecture
Day 05 → Processes, Threads & Memory Management
Day 06 → Windows Operating System Fundamentals
Day 07 → Windows Users, Permissions & Services
Day 08 → Windows System Administration & Security Controls
Day 09 → Introduction to Computer Networking
Day 10 → OSI Model & TCP/IP Model in Depth
```

**Next: Day 11 — IPv4 Addressing & Subnetting Fundamentals**, covering **binary, IPv4 structure, network/host portions, subnet masks, CIDR notation, private/public IPs, network address, broadcast address, usable hosts, default gateway and practical subnetting exercises.**
