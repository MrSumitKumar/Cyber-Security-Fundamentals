# Day 05 — Processes, Threads & Memory Management

**Course:** Cyber Security & Ethical Hacking Professional Program
**Day:** 05
**Module:** Computer & Operating System Fundamentals
**Topic:** Processes, Threads & Memory Management
**Level:** Beginner

## Learning Objectives

By the end of Day 05, students should be able to:

* Understand what a process is.
* Understand the difference between a program, process, and thread.
* Understand how the operating system manages processes.
* Understand process states.
* Understand Process IDs.
* Understand parent and child processes.
* Understand basic memory management.
* Understand virtual memory.
* Understand stack and heap at a conceptual level.
* Understand why processes and memory are important in cyber security.

---

# 1. Why Processes Matter in Cyber Security

A computer can run many applications simultaneously:

```text
Chrome
VS Code
Python
Antivirus
File Explorer
System Services
```

But how does the operating system manage all of them?

The answer involves:

> **Processes, threads, scheduling, and memory management.**

Security professionals need to understand these concepts because suspicious activity often appears as:

* An unexpected process
* An unusual process hierarchy
* Excessive resource usage
* A suspicious child process
* An unexpected network connection
* Abnormal memory behavior

---

# 2. Program vs Process

A **program** is a set of instructions stored somewhere, usually on persistent storage.

A **process** is a running instance of that program.

Example:

```text
Program
Chrome.exe
     ↓
User launches it
     ↓
Process
Chrome running in memory
```

### Easy analogy

Think of:

**Program = Recipe**

**Process = Cooking the recipe**

The recipe can exist without cooking it.

---

# 3. What Happens When You Start a Program?

Suppose you open a calculator.

A simplified sequence is:

```text
Program stored on disk
        ↓
Operating System loads required code/data
        ↓
Memory is allocated
        ↓
Process is created
        ↓
CPU executes instructions
        ↓
Application runs
```

The OS handles many of these operations behind the scenes.

---

# 4. What is a Process?

A **process** is a running execution environment managed by the operating system.

A process generally has resources associated with it, such as:

* Memory
* CPU time
* Open files
* Network connections
* Security context
* Threads

Conceptually:

```text
Process
├── Process ID
├── Memory
├── Threads
├── Open Files
├── Network Connections
└── Security Context
```

---

# 5. Process ID — PID

Operating systems typically assign a unique identifier to each active process.

This is called a:

**PID — Process ID**

Example:

```text
PID     Process
1000    System
1250    Browser
2034    Python
2450    VS Code
```

The exact values change from system to system.

---

# 6. Why is PID Important?

Security analysts often use process IDs to investigate activity.

For example:

```text
Suspicious Process
       ↓
Find PID
       ↓
Check Parent Process
       ↓
Check Command Line
       ↓
Check User
       ↓
Check Network Connections
       ↓
Investigate
```

A PID is therefore an important identifier during system investigation.

---

# 7. Process States

A process can move through different states.

A simplified model:

```text
New
 ↓
Ready
 ↓
Running
 ↓
Waiting
 ↓
Ready
 ↓
Running
 ↓
Terminated
```

### New

The process is being created.

### Ready

The process is ready to run but waiting for CPU scheduling.

### Running

The CPU is executing its instructions.

### Waiting/Blocked

The process is waiting for something, such as:

* File I/O
* Network response
* User input
* Another resource

### Terminated

The process has finished or has been stopped.

---

# 8. Process Scheduling

A computer may have hundreds of processes but only a limited number of CPU cores.

So the operating system needs a **scheduler**.

The scheduler decides which runnable work gets CPU time.

Simplified:

```text
Process A ──┐
Process B ──┤
Process C ──┼──→ CPU Scheduler → CPU
Process D ──┤
Process E ──┘
```

Modern scheduling is much more sophisticated than this simplified diagram, but this gives the basic idea.

---

# 9. Multitasking

Modern operating systems allow multiple programs to appear to run simultaneously.

For example:

```text
Browser
Music
VS Code
Antivirus
Terminal
```

The operating system manages CPU time and other resources among them.

On multi-core systems, multiple threads can also execute concurrently on different cores.

---

# 10. Context Switching

When the CPU switches from one running task to another, the operating system needs to preserve enough execution state to resume the previous task later.

This is called a **context switch**.

Conceptually:

```text
Process A
   ↓
Save State
   ↓
Process B
   ↓
Save State
   ↓
Process A
   ↓
Resume
```

Context switching allows many tasks to share CPU resources.

---

# 11. What is a Thread?

A **thread** is an execution unit within a process.

A process can contain one or multiple threads.

Example:

```text
Process
│
├── Thread 1
├── Thread 2
├── Thread 3
└── Thread 4
```

Threads within the same process generally share the process's address space and resources, while each thread has its own execution state.

---

# 12. Process vs Thread

| Process                      | Thread                               |
| ---------------------------- | ------------------------------------ |
| Running program environment  | Execution unit within a process      |
| Has its own address space    | Usually shares process address space |
| More isolated                | Less isolated from sibling threads   |
| More resource overhead       | Generally lighter weight             |
| Can contain multiple threads | Belongs to a process                 |

### Easy analogy

Think of a company:

```text
Company = Process

Employees = Threads
```

The employees work within the same organization but perform different tasks.

---

# 13. Why Threads Matter in Security

Threads are relevant to:

* Malware analysis
* Application security
* Performance analysis
* Incident response
* Debugging
* Exploit research
* Digital forensics

A suspicious process may have unusual threads or thread behavior.

Security analysts may investigate these characteristics.

---

# 14. Parent and Child Processes

Processes can create other processes.

This creates a process hierarchy.

Example:

```text
Parent Process
      │
      ├── Child Process A
      │
      ├── Child Process B
      │
      └── Child Process C
```

The exact process relationship mechanisms differ across operating systems.

---

# 15. Why Process Trees Matter

Imagine an ordinary application unexpectedly launches a command interpreter.

A security analyst may investigate:

```text
Office Application
       ↓
Command Interpreter
       ↓
Unknown Program
```

The process tree provides context.

Instead of looking only at the suspicious process, analysts ask:

> **Who started it?**

and:

> **What did it start afterward?**

This is an important defensive investigation technique.

---

# 16. Process Tree

A process tree visually represents parent-child relationships.

Example:

```text
System
 ├── Service Manager
 │      ├── Web Service
 │      └── Database Service
 │
 └── User Session
        ├── Browser
        ├── Terminal
        └── Editor
```

Security analysts can use process trees to identify unusual execution chains.

---

# 17. What is Memory?

Memory is the working area used by running programs.

A simplified system:

```text
Storage
   ↓
Program/Data
   ↓
RAM
   ↓
CPU
```

When a program runs, it needs memory for:

* Code
* Data
* Variables
* Execution state
* Runtime information

---

# 18. Process Memory

Each process normally operates within its own virtual address space.

Conceptually:

```text
Process A
┌─────────────────┐
│ Virtual Memory  │
└─────────────────┘

Process B
┌─────────────────┐
│ Virtual Memory  │
└─────────────────┘
```

This separation helps prevent ordinary applications from directly accessing arbitrary memory belonging to other processes.

Operating systems enforce these boundaries using hardware and software mechanisms.

---

# 19. Virtual Address Space

Modern operating systems generally give processes a **virtual address space**.

The application sees virtual addresses rather than simply working directly with physical RAM addresses.

Simplified:

```text
Application
     ↓
Virtual Address
     ↓
Memory Management
     ↓
Physical Memory
```

This abstraction provides:

* Isolation
* Flexibility
* Memory management
* Protection

---

# 20. Virtual Memory

Virtual memory is a memory-management technique that allows the OS to provide processes with virtual memory spaces and manage physical memory resources.

Some inactive memory pages may be moved between RAM and storage depending on the operating system and workload.

Simplified:

```text
Application Memory
       ↓
Virtual Memory
       ↓
┌───────────────┐
│      RAM      │
└───────────────┘
       ↕
┌───────────────┐
│    Storage    │
└───────────────┘
```

This is more complex than simply "using storage as RAM," but that is a useful beginner-level intuition.

---

# 21. Pages

Virtual memory is commonly divided into fixed-size units called **pages**.

Physical memory is divided into corresponding units called **frames**.

Conceptually:

```text
Virtual Memory
├── Page 1
├── Page 2
├── Page 3
└── Page 4

Physical Memory
├── Frame 1
├── Frame 2
├── Frame 3
└── Frame 4
```

The OS maintains mappings between virtual pages and physical frames.

---

# 22. Page Table

A **page table** helps the system map virtual addresses to physical memory.

Simplified:

```text
Virtual Page
     ↓
Page Table
     ↓
Physical Frame
```

Example concept:

```text
Virtual Page 5 → Physical Frame 12
Virtual Page 6 → Physical Frame 3
```

This mapping is a fundamental part of virtual memory.

---

# 23. Why Memory Isolation Matters

Imagine:

```text
Browser Process
       ↓
Memory
```

and:

```text
Banking Application
       ↓
Memory
```

If every application could freely read or modify every other application's memory, security would be extremely difficult.

Memory protection helps provide isolation.

This is one reason operating system security is so important.

---

# 24. Stack Memory

The **stack** is commonly used for temporary execution-related data.

It may contain things such as:

* Function call information
* Local variables
* Return addresses
* Execution state

Simplified:

```text
Stack
┌──────────────┐
│ Function C   │
├──────────────┤
│ Function B   │
├──────────────┤
│ Function A   │
└──────────────┘
```

The exact layout depends on architecture, compiler, operating system, and program.

---

# 25. Heap Memory

The **heap** is commonly used for dynamically allocated memory.

For example, a program may request memory while it is running.

Conceptually:

```text
Program
   ↓
Request Memory
   ↓
Heap
   ↓
Memory Allocated
```

Languages such as C and C++ give programmers more direct control over dynamic memory than languages with automatic memory management.

---

# 26. Stack vs Heap

| Stack                                                 | Heap                                         |
| ----------------------------------------------------- | -------------------------------------------- |
| Commonly used for function execution data             | Commonly used for dynamic allocation         |
| Managed automatically by execution/runtime mechanisms | Allocation depends on program/runtime        |
| Typically structured around call frames               | More flexible                                |
| Often relatively fast                                 | Can have more allocation-management overhead |

For now, understand the concepts rather than memorizing implementation details.

---

# 27. Memory Management

The operating system manages memory so multiple processes can coexist.

It needs to handle:

* Memory allocation
* Memory protection
* Virtual memory
* Address translation
* Process isolation
* Sharing where appropriate
* Reclaiming memory

Simplified:

```text
Applications
     ↓
Process Memory Requests
     ↓
Operating System
     ↓
Memory Management
     ↓
Physical RAM
```

---

# 28. Memory Allocation

When a program needs memory, it requests memory from the operating system or from a runtime/allocator.

For example:

```text
Program
   ↓
"Need memory"
   ↓
Allocator / OS
   ↓
Memory region
   ↓
Program uses it
```

When memory is no longer needed, it can be released or reclaimed.

---

# 29. Memory Leak

A **memory leak** occurs when a program continues to hold memory that it no longer needs, preventing that memory from being efficiently reused.

Example:

```text
Start Program
     ↓
Allocate Memory
     ↓
Use Memory
     ↓
Forget to Release
     ↓
Allocate More
     ↓
Memory Usage Increases
```

Potential result:

```text
High Memory Usage
       ↓
Performance Problems
       ↓
Application/System Instability
```

---

# 30. Memory Corruption

**Memory corruption** occurs when a program incorrectly reads, writes, or manages memory.

Examples include:

* Out-of-bounds access
* Use-after-free
* Invalid memory access

Memory corruption can create serious security vulnerabilities.

This is one reason secure programming is important.

---

# 31. Buffer Overflow — Basic Concept

A **buffer** is a region of memory used to hold data.

Suppose a buffer can store 10 bytes:

```text
Buffer Capacity = 10 bytes
```

If a program incorrectly writes more data than the buffer can safely hold:

```text
Input
 ↓
Too Much Data
 ↓
Buffer
 ↓
Memory Corruption
```

This is called a **buffer overflow**.

Buffer overflow vulnerabilities have historically been an important class of security issue.

For now, students only need to understand the concept.

We will study secure memory handling later.

---

# 32. Use-After-Free — Basic Concept

A **use-after-free** issue can occur when a program continues using memory after that memory has already been released.

Simplified:

```text
Allocate Memory
      ↓
Use Memory
      ↓
Free Memory
      ↓
Incorrectly Use Same Memory
      ↓
Potential Security Issue
```

This is an advanced topic that will be covered later.

---

# 33. Why Memory Matters in Malware Analysis

Malware may execute in memory and create processes or threads.

During an investigation, analysts may examine:

* Running processes
* Process memory
* Loaded modules
* Threads
* Network connections
* Process relationships

This can help identify suspicious behavior.

---

# 34. Memory Forensics

**Memory forensics** is the analysis of volatile memory to investigate activity on a system.

A memory image may contain information about:

* Running processes
* Network connections
* Loaded modules
* Command activity
* In-memory artifacts

A simplified investigation:

```text
System Incident
      ↓
Memory Acquisition
      ↓
Memory Image
      ↓
Analysis
      ↓
Suspicious Activity
      ↓
Investigation Report
```

This will be covered in greater depth later in the course.

---

# 35. Processes and Security Monitoring

Security monitoring can examine process-related information.

For example:

```text
Process Name
PID
Parent Process
User
Command Line
CPU Usage
Memory Usage
Network Activity
```

Analysts can combine these signals to identify suspicious behavior.

---

# 36. Example Investigation

Imagine a user's computer has an unknown process.

The analyst sees:

```text
Process:
unknown.exe

PID:
2450

Parent:
unexpected_application.exe

User:
Student

Network:
Unknown outbound connection
```

The analyst should not immediately assume it is malware.

Instead:

```text
Observe
 ↓
Collect Evidence
 ↓
Identify Process
 ↓
Check Parent
 ↓
Check File Location
 ↓
Check Signature/Hash
 ↓
Check Network Activity
 ↓
Investigate
```

### Important principle

> **A suspicious indicator is a reason to investigate, not automatic proof of compromise.**

---

# 37. Windows Process Management

Windows provides several ways to inspect processes.

For beginner observation, students can use:

* Task Manager
* PowerShell
* Command Prompt

Task Manager can display information such as:

* Process name
* CPU
* Memory
* Disk
* Network
* Users

---

# 38. Linux Process Management

Linux provides command-line tools for process inspection.

Common commands include:

```bash
ps
top
htop
pgrep
```

These commands can help display running processes.

### Example

```bash
ps
```

Students should use these commands only to **observe their own system** during this course.

---

# 39. Safe Process Investigation Lab

Today's practical work should be performed only on your own computer or an authorized lab.

## Windows

Open Task Manager.

Observe:

* Process name
* PID
* CPU
* Memory
* User

Select a familiar process and note its information.

Do not terminate system processes merely for experimentation.

---

## Linux

Run:

```bash
ps aux
```

Observe:

* User
* PID
* CPU
* Memory
* Command

You can also try:

```bash
top
```

Press `q` to exit `top`.

---

# 40. Day 05 Practical Activity

## Activity 1 — Process Observation

Select five normal processes on your own system.

Create:

| Process   | PID | User | CPU | Memory |
| --------- | --: | ---- | --: | -----: |
| Process 1 |     |      |     |        |
| Process 2 |     |      |     |        |
| Process 3 |     |      |     |        |
| Process 4 |     |      |     |        |
| Process 5 |     |      |     |        |

---

## Activity 2 — Process Tree

Choose one familiar application.

Determine:

```text
Application
   ↓
Parent Process
   ↓
Application Process
   ↓
Child Processes
```

Document what you observe.

---

# 41. Activity 3 — Memory Observation

Open:

* Browser
* VS Code
* A document
* Terminal

Observe memory usage.

Then close some applications.

Compare:

```text
Before
 ↓
Memory Usage

After Closing Apps
 ↓
Memory Usage
```

Write your observations.

---

# 42. Activity 4 — Process Investigation

Choose a **known, legitimate process** from your own system.

Find:

* Process name
* PID
* Parent process, if available
* Executable path
* User
* CPU usage
* Memory usage

Then answer:

> What is this process used for?

---

# 43. Day 05 Mini Project

## "Basic Process & Memory Analysis Report"

Create a report containing:

### Section 1 — System Information

```text
Operating System:
CPU:
RAM:
```

### Section 2 — Process Analysis

Document five processes.

### Section 3 — Process Tree

Show one parent-child process relationship.

### Section 4 — Memory

Explain:

* RAM
* Virtual memory
* Stack
* Heap

### Section 5 — Security

Identify three things that a SOC analyst might investigate about a suspicious process.

---

# 44. Day 05 Assignment

### Q1.

What is a process?

### Q2.

What is a PID?

### Q3.

Explain the difference between a program and a process.

### Q4.

Explain the difference between a process and a thread.

### Q5.

What is a process tree?

### Q6.

What is virtual memory?

### Q7.

What is a page?

### Q8.

What is the difference between stack and heap?

### Q9.

What is a memory leak?

### Q10.

What is memory corruption?

### Q11.

What is a buffer overflow at a high level?

### Q12.

Why is process analysis useful in cyber security?

---

# 45. Day 05 Quick Quiz

### Q1. What identifies a running process?

A. PID
B. MAC
C. URL
D. DNS

**Answer: A**

---

### Q2. A process is:

A. A running instance of a program
B. A physical CPU
C. A storage device
D. A network cable

**Answer: A**

---

### Q3. A thread is:

A. A physical memory chip
B. An execution unit within a process
C. A network protocol
D. A file system

**Answer: B**

---

### Q4. What does a process tree show?

A. CPU temperature
B. Parent-child process relationships
C. Storage capacity
D. Network speed

**Answer: B**

---

### Q5. Which memory concept provides virtual address spaces?

A. Virtual memory
B. BIOS
C. DNS
D. Ethernet

**Answer: A**

---

### Q6. Which is commonly associated with function call information?

A. Stack
B. SSD
C. GPU
D. NIC

**Answer: A**

---

### Q7. Which is commonly used for dynamic memory allocation?

A. Heap
B. BIOS
C. CPU cache only
D. Bootloader

**Answer: A**

---

### Q8. What can a memory leak cause?

A. Increasing memory consumption
B. Faster internet
C. More storage capacity
D. Automatic encryption

**Answer: A**

---

### Q9. What is a buffer overflow?

A. Writing beyond the intended bounds of a buffer
B. Increasing RAM capacity
C. Installing an operating system
D. Starting a network service

**Answer: A**

---

### Q10. Why can process trees help security analysts?

A. They show monitor resolution
B. They provide execution context and parent-child relationships
C. They increase CPU speed
D. They encrypt files

**Answer: B**

---

# 46. Important Terminology

| Term              | Meaning                                                 |
| ----------------- | ------------------------------------------------------- |
| Program           | Set of instructions                                     |
| Process           | Running instance of a program                           |
| PID               | Process identifier                                      |
| Thread            | Execution unit within a process                         |
| Process Tree      | Parent-child process relationships                      |
| Scheduler         | OS component that manages CPU scheduling                |
| Context Switch    | Switching CPU execution between tasks                   |
| RAM               | Physical working memory                                 |
| Virtual Memory    | OS-managed virtual memory abstraction                   |
| Page              | Fixed-size unit of virtual memory                       |
| Page Table        | Maps virtual pages to physical frames                   |
| Stack             | Memory area commonly associated with function execution |
| Heap              | Memory area commonly used for dynamic allocation        |
| Memory Leak       | Memory remains allocated when no longer needed          |
| Memory Corruption | Incorrect memory access or management                   |
| Buffer Overflow   | Writing beyond intended buffer boundaries               |
| Memory Forensics  | Analysis of volatile memory                             |

---

# 47. Day 05 Key Takeaways

Students should remember:

1. A **program** is not the same as a **process**.
2. A process is a running execution environment.
3. Every process normally has an identifier called a **PID**.
4. Processes can create other processes.
5. Parent-child relationships form process trees.
6. Threads are execution units within processes.
7. The operating system schedules processes and threads.
8. Memory management allows multiple processes to operate safely.
9. Virtual memory provides processes with managed virtual address spaces.
10. Pages and page tables are fundamental to virtual memory.
11. Stack and heap are important memory concepts.
12. Memory leaks can cause excessive memory consumption.
13. Memory corruption can create serious security vulnerabilities.
14. Buffer overflows are an important historical and ongoing vulnerability class.
15. Process and memory analysis are important skills for SOC analysts, incident responders, malware analysts, and security researchers.
16. **Security analysts investigate process behavior in context rather than judging a process solely by its name.**

---

# 48. Day 05 Final Concept

The complete relationship is:

```text
                 USER
                   ↓
              APPLICATION
                   ↓
                PROGRAM
                   ↓
                PROCESS
             ┌─────┼─────┐
             ↓     ↓     ↓
          Thread Thread Thread
             │     │     │
             └─────┼─────┘
                   ↓
             VIRTUAL MEMORY
                   ↓
          ┌────────┼────────┐
          ↓        ↓        ↓
       Stack      Heap    Other Regions
          │        │        │
          └────────┼────────┘
                   ↓
              MEMORY MANAGER
                   ↓
                  RAM
```

### Cyber Security Mindset

When a security analyst sees a process, they should think:

```text
What is it?
     ↓
Who started it?
     ↓
Which user is running it?
     ↓
What is its parent process?
     ↓
What does it access?
     ↓
What network connections does it make?
     ↓
What files/modules does it use?
     ↓
Is the behavior expected?
     ↓
If not → Investigate
```

**Next: Day 06 — Windows Operating System Fundamentals**, where students will learn the Windows architecture, user accounts, NTFS, permissions, registry, services, processes, Event Viewer, PowerShell basics, and the Windows security model.
