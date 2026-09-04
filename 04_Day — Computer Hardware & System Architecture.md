# Day 04 — Computer Hardware & System Architecture

**Course:** Cyber Security & Ethical Hacking Professional Program
**Day:** 04
**Module:** Cyber Security Fundamentals
**Topic:** Computer Hardware & System Architecture
**Level:** Beginner

## Learning Objectives

By the end of Day 04, students should be able to:

* Understand the basic architecture of a computer.
* Understand how CPU, RAM, storage, and motherboard work together.
* Understand 32-bit vs 64-bit architecture.
* Understand BIOS/UEFI and the boot process.
* Understand firmware and device drivers.
* Understand buses and system communication.
* Understand why hardware knowledge matters in cyber security.
* Identify basic hardware-related security risks.

---

# 1. What is System Architecture?

**Computer system architecture** describes how the major components of a computer are organized and how they communicate with each other.

A simplified architecture looks like this:

```text
                COMPUTER SYSTEM
                      │
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
       CPU           RAM         STORAGE
        │             │             │
        └─────────────┼─────────────┘
                      ↓
                 MOTHERBOARD
                      │
        ┌─────────────┼─────────────┐
        ↓             ↓             ↓
      GPU           Network       I/O Devices
                    Adapter
```

The operating system sits above this hardware and manages its resources.

---

# 2. Basic Computer Architecture

A computer can be understood as several layers:

```text
User
  ↓
Applications
  ↓
Operating System
  ↓
Firmware
  ↓
Hardware
```

Each layer has a different responsibility.

### Example

When you open a browser:

```text
You click Chrome
      ↓
Operating System
      ↓
Creates/uses processes
      ↓
CPU executes instructions
      ↓
RAM stores active data
      ↓
Network adapter communicates
      ↓
Internet
```

This interaction happens extremely quickly.

---

# 3. CPU — Central Processing Unit

The **CPU** is the main processor responsible for executing instructions.

A simplified CPU contains:

```text
CPU
├── Control Unit
├── Arithmetic Logic Unit
├── Registers
└── Cache
```

Let's understand these concepts.

---

# 4. Control Unit

The **Control Unit** coordinates the execution of instructions.

It helps control:

* Instruction fetching
* Instruction decoding
* Instruction execution
* Data movement

Simplified:

```text
Instruction
    ↓
Fetch
    ↓
Decode
    ↓
Execute
```

This is part of the basic instruction cycle.

---

# 5. Arithmetic Logic Unit — ALU

The **Arithmetic Logic Unit**, or **ALU**, performs many arithmetic and logical operations.

Examples:

```text
10 + 20
50 - 15
AND
OR
NOT
Comparison
```

The ALU is therefore an important part of instruction execution.

---

# 6. CPU Registers

Registers are very small and extremely fast storage locations inside the CPU.

They hold information needed during instruction execution.

For example, registers may hold:

* Data
* Addresses
* Instruction-related information
* Intermediate results

Registers are much smaller than RAM.

---

# 7. CPU Cache

CPU cache is high-speed memory located close to or within the processor.

Common cache levels include:

```text
L1
L2
L3
```

Generally:

```text
CPU Registers
      ↓
L1 Cache
      ↓
L2 Cache
      ↓
L3 Cache
      ↓
RAM
      ↓
Storage
```

As you move down this hierarchy, capacity generally increases while access becomes relatively slower.

---

# 8. CPU Clock Speed

CPU performance is sometimes described using clock frequency such as:

```text
3.5 GHz
4.0 GHz
```

A higher clock frequency can contribute to performance, but **clock speed alone does not determine overall CPU performance**.

Other factors include:

* CPU architecture
* Number of cores
* Cache
* Instruction set
* Workload
* Memory performance

---

# 9. CPU Cores and Threads

A CPU may contain multiple processing cores.

Example:

```text
CPU
├── Core 1
├── Core 2
├── Core 3
└── Core 4
```

Some processors also support technologies that allow a core to expose multiple logical processors to the operating system.

The OS can then schedule work across available logical processors.

---

# 10. RAM Architecture

RAM is where active programs and data are held while they are being used.

Example:

```text
Storage
   ↓
Operating System
   ↓
RAM
   ↓
CPU
```

When you start an application, relevant code and data are loaded into memory so the CPU can work with them.

---

# 11. Memory Address

Computer memory is organized using addresses.

Think of memory like a large collection of numbered locations:

```text
Address       Data
1000          A
1001          B
1002          C
1003          D
```

The operating system and applications use memory addresses to work with data.

Students will later encounter memory concepts in:

* Operating system security
* Digital forensics
* Malware analysis
* Secure programming

---

# 12. Virtual Memory

Operating systems can use a combination of RAM and storage to provide **virtual memory**.

A simplified idea:

```text
Physical RAM
     +
Storage
     ↓
Virtual Memory System
```

Virtual memory allows the OS to provide each process with a managed memory environment.

This is one reason applications don't normally directly access arbitrary memory belonging to other processes.

---

# 13. Storage Architecture

Storage devices are used for persistent data.

Two common types are:

### HDD

Uses magnetic disks and mechanical components.

### SSD

Uses flash memory and has no spinning disk.

Simplified:

```text
SSD/HDD
   ↓
File System
   ↓
Files & Directories
```

---

# 14. HDD vs SSD

| HDD                       | SSD                         |
| ------------------------- | --------------------------- |
| Mechanical                | Solid-state                 |
| Uses spinning disks       | Uses flash memory           |
| Generally slower          | Generally faster            |
| Mechanical parts          | No spinning mechanical disk |
| Usually lower cost per GB | Usually higher cost per GB  |

From a security perspective, both can contain sensitive information.

---

# 15. Motherboard

The motherboard connects major components.

It provides communication pathways between:

* CPU
* RAM
* Storage
* GPU
* Network interfaces
* USB devices
* Other peripherals

Simplified:

```text
             CPU
              │
              ↓
        MOTHERBOARD
       /      │      \
      ↓       ↓       ↓
    RAM    Storage    GPU
              │
              ↓
        Network / I/O
```

---

# 16. System Bus

A **bus** is a communication pathway used to transfer information between components.

Conceptually, buses may carry:

* Data
* Addresses
* Control signals

Modern systems use multiple interconnect technologies rather than one simple shared bus, but the basic idea remains:

> **Components need communication pathways to exchange information.**

---

# 17. GPU

The **Graphics Processing Unit**, or GPU, is specialized for graphics and highly parallel computation.

It is commonly used for:

* Graphics rendering
* Video processing
* Machine learning
* Scientific computing

From a cyber security perspective, GPUs can also be relevant to topics such as:

* Password security research
* Cryptographic computation
* Malware research
* Security performance testing

Any security testing involving password recovery should only be performed on systems and data you are authorized to test.

---

# 18. Network Interface Card

A **Network Interface Controller/Card**, commonly called a NIC, allows a system to communicate over a network.

It may support:

* Ethernet
* Wi-Fi

The operating system interacts with the network interface through drivers.

Simplified:

```text
Application
     ↓
Operating System
     ↓
Network Stack
     ↓
Network Driver
     ↓
NIC
     ↓
Network
```

This architecture becomes very important when we start networking.

---

# 19. Device Drivers

A **device driver** is software that enables the operating system to communicate with hardware.

Example:

```text
Operating System
       ↓
Wi-Fi Driver
       ↓
Wi-Fi Adapter
```

Without an appropriate driver, the OS may not be able to properly use the device.

Drivers are security-sensitive because they operate close to the operating system and hardware.

---

# 20. Firmware

**Firmware** is software stored on hardware that provides low-level control or initialization.

Examples include firmware associated with:

* Motherboards
* Network devices
* Storage devices
* Embedded devices

Firmware operates at a lower level than normal applications.

---

# 21. BIOS and UEFI

When a computer starts, firmware helps initialize hardware and begin the boot process.

Older systems commonly use **BIOS**.

Modern systems commonly use **UEFI**.

A simplified boot sequence:

```text
Power On
   ↓
Firmware
   ↓
Hardware Initialization
   ↓
Boot Manager
   ↓
Operating System Loader
   ↓
Operating System
   ↓
Login
```

---

# 22. What Happens When You Turn On a Computer?

Let's break it down.

### Step 1 — Power On

The system receives power.

### Step 2 — Firmware Starts

BIOS/UEFI firmware begins execution.

### Step 3 — Hardware Initialization

The system initializes essential hardware.

### Step 4 — Boot Device Selection

Firmware identifies a device from which the system can boot.

### Step 5 — Bootloader

The bootloader starts loading the operating system.

### Step 6 — Kernel Loads

The OS kernel is loaded into memory.

### Step 7 — System Initialization

Services and system components start.

### Step 8 — Login

The user receives the operating system login interface.

Complete flow:

```text
Power
 ↓
BIOS / UEFI
 ↓
Hardware Initialization
 ↓
Boot Manager
 ↓
Bootloader
 ↓
OS Kernel
 ↓
System Services
 ↓
Login
```

---

# 23. Why is the Boot Process Important in Cyber Security?

The boot process is security-sensitive.

If an attacker can manipulate low-level startup components, they may potentially interfere with system integrity.

Modern computers therefore use security technologies such as:

* Secure Boot
* Trusted Platform Module
* Firmware protections
* Measured boot mechanisms

These help establish trust during startup.

---

# 24. Secure Boot

**Secure Boot** is a security mechanism supported by many modern UEFI systems.

Its purpose is to help ensure that trusted software is used during the early boot process.

Simplified:

```text
UEFI
 ↓
Verify Boot Component
 ↓
Trusted?
 ├── YES → Continue
 └── NO  → Block / Warn
```

The exact implementation and policy depend on the system.

---

# 25. TPM — Trusted Platform Module

A **TPM** is a security component designed to provide hardware-assisted security functions.

It can support capabilities related to:

* Cryptographic keys
* Device identity
* Secure boot measurements
* Platform integrity

TPM technology is important in modern endpoint security.

---

# 26. Hardware Security Risks

Hardware can also have security risks.

Examples include:

### Unauthorized Physical Access

Someone physically accesses a computer.

### Malicious USB Devices

An unknown USB device could introduce security risks.

### Firmware Vulnerabilities

Vulnerabilities in firmware can potentially affect systems at a low level.

### Hardware Theft

A stolen laptop can expose sensitive information if it is not properly protected.

### Evil Maid-Type Physical Attacks

An attacker with physical access may attempt to tamper with boot-related components.

The exact attack depends heavily on the hardware and security configuration.

---

# 27. Full Disk Encryption

If a laptop is stolen, protecting data stored on the drive becomes extremely important.

**Full Disk Encryption (FDE)** encrypts stored data so that unauthorized parties cannot simply read the disk contents.

Conceptually:

```text
Without Encryption:

Disk → Readable Data


With Encryption:

Disk → Encrypted Data
          ↓
   Correct Key / Authentication
          ↓
      Readable Data
```

Examples of technologies include BitLocker and FileVault.

---

# 28. Physical Security is Cyber Security

A common beginner mistake is thinking:

> "Cyber security only means software."

This is incorrect.

Consider:

```text
Physical Access
      ↓
Computer
      ↓
Storage
      ↓
Sensitive Data
```

If an attacker obtains physical access to an inadequately protected device, many software security controls may be affected.

Therefore:

> **Physical security and cyber security are closely connected.**

---

# 29. Hardware Security Layers

A secure computer can have multiple layers:

```text
Physical Security
       ↓
Firmware Security
       ↓
Boot Security
       ↓
Operating System Security
       ↓
Application Security
       ↓
Data Security
```

This is an example of **defense in depth**.

---

# 30. 32-bit vs 64-bit

You may see systems described as:

```text
32-bit
64-bit
```

These terms generally refer to aspects of the processor architecture and the size of certain data/address operations.

Modern desktop and server operating systems are predominantly 64-bit.

### Why does this matter?

Architecture affects:

* Memory addressing
* Application compatibility
* OS compatibility
* Security features
* Performance characteristics

---

# 31. Endianness — Basic Introduction

Computer systems represent multi-byte values in memory.

Two common byte-order concepts are:

* Big-endian
* Little-endian

For example, consider a multi-byte value:

```text
0x12345678
```

The order in which bytes are stored can differ depending on architecture and context.

You do not need to memorize this deeply today.

Just remember:

> **Byte order matters when analyzing low-level data.**

It will become more relevant in advanced topics.

---

# 32. Virtualization

**Virtualization** allows a physical computer to run one or more virtual machines.

Example:

```text
Physical Computer
       ↓
Hypervisor
   ┌───┴────┐
   ↓        ↓
VM 1      VM 2
Linux    Windows
```

This is extremely useful for cyber security training.

---

# 33. Why Cyber Security Labs Use Virtual Machines

A security student can create an isolated environment such as:

```text
Host Computer
      ↓
Virtualization
      ↓
┌──────────────┐
│ Security Lab │
│              │
│ Linux VM     │
│ Windows VM   │
│ Practice VM  │
└──────────────┘
```

This allows students to practice safely on systems they control.

### Important

Security testing should be performed only on:

* Your own systems
* Authorized training labs
* Explicitly authorized environments

---

# 34. Hypervisor

A **hypervisor** manages virtual machines.

Two broad categories are:

### Type 1

Runs directly on hardware.

```text
Hardware
   ↓
Hypervisor
   ↓
Virtual Machines
```

### Type 2

Runs on top of an operating system.

```text
Hardware
   ↓
Host Operating System
   ↓
Hypervisor
   ↓
Virtual Machines
```

Examples of virtualization software will be explored later in the course.

---

# 35. Snapshot

A virtual machine snapshot captures the state of a VM at a particular point.

For example:

```text
Clean Lab
   ↓
Snapshot
   ↓
Security Practice
   ↓
Something Goes Wrong
   ↓
Restore Snapshot
```

Snapshots are extremely useful for learning environments.

However, they should not be considered a replacement for proper backups.

---

# 36. Why System Architecture Matters to Ethical Hackers

Ethical hackers need to understand what exists underneath applications.

For example:

```text
Web Application
      ↓
Web Server
      ↓
Operating System
      ↓
Kernel
      ↓
CPU / RAM / Storage
```

A vulnerability may exist at different layers.

Understanding the underlying architecture helps security professionals:

* Interpret findings
* Understand system behavior
* Assess impact
* Communicate with administrators
* Recommend appropriate mitigations

---

# 37. Day 04 Practical Lab

Today's lab should focus on **observation**, not attacking anything.

## Task 1 — Identify System Architecture

On your computer, record:

```text
Operating System:
Architecture:
CPU:
Number of Cores:
RAM:
Storage Type:
Network Adapter:
```

---

## Task 2 — Check CPU Information

Find:

* CPU model
* Number of cores
* Logical processors
* Approximate clock speed

Record the information.

---

## Task 3 — Check RAM

Record:

```text
Total RAM:
Currently Used:
Available:
```

Observe how memory usage changes when you open and close applications.

---

## Task 4 — Check Storage

Identify:

* Number of drives
* Drive type, if available
* Total capacity
* Available space
* File system

Do not delete or modify anything.

---

# 38. Task 5 — Observe the Boot Process

Restart your own computer and observe the startup process.

Look for:

```text
Power On
 ↓
Manufacturer Logo
 ↓
Boot Process
 ↓
Operating System
 ↓
Login
```

Do not change firmware settings unless you know what you are doing.

---

# 39. Task 6 — Explore Virtualization

If your computer supports virtualization, research:

* What is a virtual machine?
* What is a hypervisor?
* What is a VM snapshot?
* Why are VMs useful for security labs?

Do not install anything yet unless instructed by your instructor.

---

# 40. Day 04 Mini Project

## "My Computer Architecture Report"

Create a one-page report containing:

### Section 1 — Hardware

```text
CPU:
RAM:
Storage:
GPU:
Network Adapter:
```

### Section 2 — Software

```text
Operating System:
OS Architecture:
File System:
```

### Section 3 — Boot

Explain:

```text
Power On
→ Firmware
→ Bootloader
→ Kernel
→ Operating System
```

### Section 4 — Security

Write **five security recommendations** for your computer.

Example:

1. Enable automatic security updates.
2. Use strong authentication.
3. Enable disk encryption where appropriate.
4. Avoid unknown USB devices.
5. Keep security software and drivers updated.

---

# 41. Day 04 Assignment

### Q1.

What is computer system architecture?

### Q2.

Explain the difference between:

**CPU vs RAM vs Storage**

### Q3.

What is the purpose of BIOS/UEFI?

### Q4.

Explain the basic boot process.

### Q5.

What is firmware?

### Q6.

What is a device driver?

### Q7.

What is Secure Boot?

### Q8.

What is TPM?

### Q9.

What is virtualization?

### Q10.

Why are virtual machines useful for cyber security training?

---

# 42. Day 04 Quick Quiz

### Q1. Which component executes instructions?

A. CPU
B. SSD
C. Monitor
D. Keyboard

**Answer: A**

---

### Q2. Which component provides temporary working memory?

A. HDD
B. RAM
C. GPU
D. BIOS

**Answer: B**

---

### Q3. What normally starts before the operating system during boot?

A. Browser
B. Firmware
C. Word processor
D. Database

**Answer: B**

---

### Q4. What does UEFI relate to?

A. Boot firmware
B. Web browser
C. Database
D. Programming language

**Answer: A**

---

### Q5. What does a device driver do?

A. Connects software with hardware
B. Encrypts every file
C. Replaces the CPU
D. Deletes malware automatically

**Answer: A**

---

### Q6. What is Secure Boot designed to help protect?

A. Early boot integrity
B. Monitor brightness
C. Keyboard layout
D. Internet speed

**Answer: A**

---

### Q7. What is a hypervisor used for?

A. Managing virtual machines
B. Editing images
C. Writing emails
D. Formatting documents

**Answer: A**

---

### Q8. Which is persistent storage?

A. CPU register
B. RAM
C. SSD
D. CPU cache

**Answer: C**

---

# 43. Day 04 Important Terminology

| Term            | Meaning                                           |
| --------------- | ------------------------------------------------- |
| CPU             | Processor that executes instructions              |
| Core            | Processing unit within a CPU                      |
| Register        | Very small, fast CPU storage                      |
| Cache           | High-speed memory close to/within CPU             |
| RAM             | Temporary working memory                          |
| SSD             | Solid-state persistent storage                    |
| HDD             | Magnetic persistent storage                       |
| Motherboard     | Main board connecting system components           |
| Firmware        | Low-level software stored on hardware             |
| BIOS            | Traditional system firmware interface             |
| UEFI            | Modern firmware environment                       |
| Bootloader      | Software that helps load the OS                   |
| Kernel          | Core privileged component of an OS                |
| Driver          | Software enabling OS-hardware communication       |
| Secure Boot     | Mechanism helping establish trusted boot software |
| TPM             | Hardware-assisted security component              |
| Hypervisor      | Software/firmware managing virtual machines       |
| Virtual Machine | Software-based computer environment               |
| Snapshot        | Saved VM state                                    |
| FDE             | Full Disk Encryption                              |

---

# 44. Day 04 Key Takeaways

Students should remember:

1. Computer architecture describes how system components work together.
2. The CPU executes instructions.
3. RAM stores active working data.
4. SSDs and HDDs provide persistent storage.
5. The motherboard connects major components.
6. Drivers allow the OS to communicate with hardware.
7. Firmware operates at a low level and helps initialize hardware.
8. BIOS/UEFI participates in the boot process.
9. Secure Boot helps protect the integrity of the early boot chain.
10. TPM provides hardware-assisted security capabilities.
11. Physical security is an important part of cyber security.
12. Disk encryption helps protect data if a device is lost or stolen.
13. Virtualization is extremely useful for creating controlled cyber security labs.
14. Security professionals need to understand systems from hardware through applications.
15. **Strong cyber security starts with understanding the technology being protected.**

---

# Day 04 Final Concept

The complete architecture can be visualized as:

```text
                    USER
                      ↓
                APPLICATIONS
                      ↓
                  PROCESSES
                      ↓
              OPERATING SYSTEM
                      ↓
                   KERNEL
                      ↓
                 DEVICE DRIVERS
                      ↓
               FIRMWARE / UEFI
                      ↓
              ┌───────┼────────┐
              ↓       ↓        ↓
             CPU     RAM     STORAGE
              │       │        │
              └───────┼────────┘
                      ↓
              MOTHERBOARD / I/O
                      ↓
             NETWORK / PERIPHERALS
```

### Cyber Security Perspective

At every layer, ask:

> **What is running?**
> **Who has access?**
> **What privileges exist?**
> **What data is stored?**
> **What is exposed?**
> **What can be monitored?**
> **What happens if this component is compromised?**

That mindset prepares students for **Day 05: Processes, Threads & Memory Management**, where we move from hardware architecture into how the operating system actually manages running programs and memory.
