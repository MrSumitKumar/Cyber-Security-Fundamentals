# Day 01 — Introduction to Cyber Security

**Course:** Cyber Security & Ethical Hacking Professional Program
**Day:** 01
**Module:** Cyber Security Fundamentals
**Topic:** Introduction to Cyber Security
**Learning Objective:** Understand what cyber security is, why it matters, what security professionals protect, and how ethical hacking fits into the larger security ecosystem.

---

## 1. What is Cyber Security?

**Cyber Security** is the practice of protecting:

* Computers
* Servers
* Networks
* Applications
* Websites
* Cloud infrastructure
* Mobile devices
* Databases
* Digital identities
* Data

from unauthorized access, misuse, disruption, modification, destruction, or theft.

### Simple Definition

> **Cyber Security = Protecting digital systems and information from cyber threats.**

For example, when a company protects its customer database from unauthorized access, that is cyber security.

---

## 2. Why Do We Need Cyber Security?

Almost every modern organization depends on technology.

Consider a bank:

```text
Customer
   ↓
Mobile Banking App
   ↓
Internet
   ↓
Web/API Servers
   ↓
Database
   ↓
Banking Infrastructure
```

If attackers compromise any important component, they may cause:

* Financial loss
* Data theft
* Service disruption
* Privacy violations
* Reputation damage
* Legal consequences

Therefore, security must be considered throughout the entire technology environment.

---

# 3. What Does Cyber Security Protect?

Cyber security generally protects three major things:

### 1. Data

Examples:

* Customer information
* Passwords
* Financial records
* Source code
* Business documents
* Medical records
* Intellectual property

### 2. Systems

Examples:

* Computers
* Servers
* Routers
* Firewalls
* Applications
* Cloud services
* Databases

### 3. People and Identities

Examples:

* User accounts
* Administrator accounts
* Employee identities
* API credentials
* Access permissions

---

# 4. The CIA Triad

One of the most important concepts in cyber security is the **CIA Triad**.

CIA stands for:

```text
C → Confidentiality
I → Integrity
A → Availability
```

These three principles form the foundation of information security.

---

## 4.1 Confidentiality

**Confidentiality** means information should only be accessible to authorized people or systems.

### Example

Suppose a company has an employee salary database.

Only authorized HR employees should be able to access it.

If an unauthorized person obtains the database, confidentiality has been compromised.

### Security mechanisms

Examples include:

* Passwords
* Encryption
* Access control
* Multi-factor authentication
* Permissions

---

## 4.2 Integrity

**Integrity** means information should remain accurate, complete, and trustworthy.

### Example

Suppose a bank account contains:

```text
Balance = ₹50,000
```

If an unauthorized person changes it to:

```text
Balance = ₹5,00,000
```

the integrity of the data has been compromised.

### Security mechanisms

Examples:

* Hashing
* Digital signatures
* Access controls
* File integrity monitoring
* Database controls

---

## 4.3 Availability

**Availability** means authorized users should be able to access systems and information when required.

### Example

Imagine an online banking website becomes unavailable for several hours.

Even if the data remains confidential and unchanged, customers cannot use the service.

Therefore, availability has been affected.

### Security mechanisms

Examples:

* Backups
* Redundant servers
* Load balancing
* Disaster recovery
* DDoS protection
* Monitoring

---

# 5. CIA Triad Example

Imagine an online shopping website.

| Principle       | Example                                                 |
| --------------- | ------------------------------------------------------- |
| Confidentiality | Customer data is accessible only to authorized users    |
| Integrity       | Product prices cannot be modified by unauthorized users |
| Availability    | Website remains accessible to customers                 |

A good security system attempts to maintain all three.

---

# 6. What is a Cyber Threat?

A **cyber threat** is a potential event, action, or actor that could negatively affect a digital system or organization.

Examples include:

* Malware
* Phishing
* Password attacks
* Data theft
* Ransomware
* Insider threats
* Denial-of-service attacks
* Vulnerability exploitation

### Simple example

A phishing email attempts to trick an employee into providing their password.

The phishing attempt is a **threat**.

---

# 7. What is a Vulnerability?

A **vulnerability** is a weakness in a system that could potentially be exploited.

Examples:

```text
Weak Password
     ↓
Security Weakness
     ↓
Potential Account Compromise
```

Other examples:

* Outdated software
* Misconfigured server
* Weak authentication
* Excessive permissions
* Unpatched vulnerability
* Insecure application code

### Important distinction

**Threat ≠ Vulnerability**

A vulnerability is a **weakness**.

A threat is something that could **take advantage of that weakness**.

---

# 8. What is Risk?

**Risk** is the possibility of negative impact resulting from a threat exploiting a vulnerability.

A simplified model is:

```text
Threat + Vulnerability
        ↓
       Risk
        ↓
Potential Impact
```

For example:

```text
Threat:
Attacker

Vulnerability:
Weak administrator password

Risk:
Unauthorized access to server

Impact:
Data theft / service disruption
```

---

# 9. Threat vs Vulnerability vs Risk

| Term          | Meaning                    | Example            |
| ------------- | -------------------------- | ------------------ |
| Threat        | Potential source of harm   | Attacker           |
| Vulnerability | Weakness                   | Weak password      |
| Risk          | Potential negative outcome | Account compromise |
| Impact        | Damage caused              | Data theft         |

This distinction is extremely important for security professionals.

---

# 10. What is an Attack?

A **cyber attack** is an intentional attempt to compromise, disrupt, manipulate, or gain unauthorized access to a digital system.

Examples:

* Phishing attack
* Malware attack
* Password attack
* Web application attack
* Denial-of-service attack
* Social engineering attack

Not every security event is necessarily an attack.

For example, a server crashing because of a hardware failure is not necessarily a cyber attack.

---

# 11. What is an Attacker?

An attacker is an individual or group attempting to compromise a system.

Common categories include:

### Script Kiddies

People who use existing tools or scripts without necessarily understanding how they work.

### Cybercriminals

Attackers motivated primarily by financial gain or other criminal objectives.

### Insider Threats

People who already have legitimate access to an organization and misuse that access.

### Nation-State Actors

Highly resourced groups associated with governments or state interests.

### Hacktivists

Attackers motivated by political or social causes.

---

# 12. What is Hacking?

**Hacking** is the process of finding ways to interact with, modify, or gain access to systems beyond their intended or normal use.

However, the word **hacker** does not automatically mean criminal.

Hackers can have different intentions.

---

# 13. Types of Hackers

### White Hat Hacker

A security professional who performs authorized security testing.

Also commonly called:

**Ethical Hacker**

Example:

A company hires a penetration tester to identify vulnerabilities in its website.

---

### Black Hat Hacker

Someone who performs unauthorized malicious activities.

Examples:

* Stealing data
* Breaking into accounts
* Deploying malware
* Extorting organizations

---

### Gray Hat Hacker

A person whose activities may fall between traditional white-hat and black-hat classifications, often involving access or testing without clear authorization.

The key lesson:

> **Authorization matters.**

---

# 14. What is Ethical Hacking?

**Ethical hacking** is authorized security testing performed to identify and help remediate vulnerabilities.

The ethical hacker works within an agreed scope.

Typical process:

```text
Authorization
      ↓
Scope Definition
      ↓
Reconnaissance
      ↓
Security Testing
      ↓
Validation
      ↓
Documentation
      ↓
Remediation
      ↓
Retesting
```

Ethical hacking is therefore not simply "breaking into computers."

It is a structured security assessment process.

---

# 15. Ethical Hacking vs Illegal Hacking

| Ethical Hacking                     | Illegal Hacking                 |
| ----------------------------------- | ------------------------------- |
| Authorized                          | Unauthorized                    |
| Defined scope                       | No approved scope               |
| Goal is security improvement        | Often malicious or unauthorized |
| Findings are reported               | Findings may be exploited       |
| Evidence is documented responsibly  | Data may be stolen/damaged      |
| Conducted under rules of engagement | Conducted without permission    |

### Golden Rule

> **Never test a system unless you have explicit authorization.**

This rule should remain with you throughout the entire course.

---

# 16. What is Penetration Testing?

**Penetration testing**, commonly called **pentesting**, is an authorized security assessment in which security professionals evaluate systems for exploitable weaknesses.

A penetration test may assess:

* Websites
* APIs
* Networks
* Servers
* Cloud environments
* Applications
* Internal infrastructure

The objective is to identify security weaknesses so they can be fixed before malicious attackers exploit them.

---

# 17. Cyber Security vs Ethical Hacking

These terms are related but not identical.

### Cyber Security

A broad field covering:

* Prevention
* Detection
* Response
* Recovery
* Security architecture
* Risk management
* Governance
* Monitoring
* Incident response
* Security testing

### Ethical Hacking

A specialized area focused heavily on:

* Finding vulnerabilities
* Security testing
* Attack simulation
* Validation
* Penetration testing

Think of it as:

```text
                 CYBER SECURITY
                       │
       ┌───────────────┼───────────────┐
       ↓               ↓               ↓
    Defense         Detection       Testing
       │               │               │
     SOC/Blue        SIEM/SOC      Ethical Hacking
       Team                          Pentesting
```

---

# 18. Major Cyber Security Domains

During this 18-month program, students will encounter several areas.

### Network Security

Protecting network infrastructure and communications.

### Application Security

Protecting software applications from vulnerabilities.

### Web Security

Protecting websites and web applications.

### Cloud Security

Protecting cloud infrastructure, applications, identities, and data.

### Endpoint Security

Protecting laptops, desktops, servers, and other endpoints.

### Identity & Access Management

Managing who can access what.

### SOC

Security Operations Center responsible for monitoring and responding to security events.

### Digital Forensics

Investigating digital evidence after security incidents.

### Incident Response

Responding to and containing security incidents.

### Penetration Testing

Authorized security testing to identify vulnerabilities.

### Malware Analysis

Analyzing malicious software to understand its behavior and indicators.

---

# 19. Security is a Continuous Process

Cyber security is not something you do once.

A typical security lifecycle looks like:

```text
Identify
   ↓
Protect
   ↓
Detect
   ↓
Respond
   ↓
Recover
   ↓
Improve
   ↺
```

Organizations must continuously improve their security because technology, vulnerabilities, and threats constantly change.

---

# 20. Real-World Example

Imagine a company has an online employee portal.

The portal has:

```text
Login Page
     ↓
Web Application
     ↓
API
     ↓
Database
```

A security team may ask:

### Confidentiality

Can unauthorized users access employee information?

### Integrity

Can unauthorized users modify employee information?

### Availability

Can attackers prevent employees from accessing the portal?

### Vulnerability

Does the application contain a security weakness?

### Risk

What could happen if that weakness were exploited?

### Ethical Hacker

Can the security team safely validate the weakness within the authorized scope?

### SOC

Can the security monitoring team detect suspicious activity?

This demonstrates how different areas of cyber security work together.

---

# 21. Important Security Terms

Students should remember these terms from Day 01:

| Term           | Meaning                                                                                       |
| -------------- | --------------------------------------------------------------------------------------------- |
| Cyber Security | Protection of digital systems and information                                                 |
| Threat         | Potential source of harm                                                                      |
| Vulnerability  | Security weakness                                                                             |
| Risk           | Potential negative outcome                                                                    |
| Attack         | Intentional attempt to compromise a system                                                    |
| Hacker         | Person who uses technical skills to interact with systems in unconventional ways              |
| Ethical Hacker | Authorized security tester                                                                    |
| Pentest        | Authorized security assessment                                                                |
| Malware        | Malicious software                                                                            |
| Authentication | Verifying who a user is                                                                       |
| Authorization  | Determining what an authenticated user can access                                             |
| Encryption     | Protecting information by transforming it into an unreadable form without the appropriate key |

---

# 22. Authentication vs Authorization

These two concepts are often confused.

### Authentication

**Who are you?**

Example:

```text
Username + Password
        ↓
Identity Verification
        ↓
Authenticated
```

### Authorization

**What are you allowed to access?**

Example:

```text
Authenticated User
        ↓
Check Permissions
        ↓
Admin Dashboard? YES/NO
```

Remember:

> **Authentication = Who are you?**
> **Authorization = What can you access?**

---

# 23. Professional Ethics

As a cyber security student, technical knowledge must be combined with professional ethics.

You should:

* Obtain permission before testing.
* Stay within the approved scope.
* Avoid unnecessary damage.
* Protect discovered information.
* Document findings accurately.
* Report vulnerabilities responsibly.
* Never misuse credentials or sensitive information.
* Never access systems simply because you discovered they are vulnerable.

### Core principle

> **Just because you can access something does not mean you are authorized to access it.**

---

# 24. Day 01 Practical Activity

### Activity: Identify Security Risks

Choose a fictional organization:

**MSK Institute**

Imagine it has:

```text
Website
Student Portal
Admin Panel
Database
Wi-Fi Network
Student Computers
Cloud Storage
Email System
```

Students should identify:

### Step 1 — Assets

List at least 10 assets.

Example:

```text
1. Website
2. Student database
3. Admin account
4. Student accounts
5. Wi-Fi network
...
```

### Step 2 — Threats

Identify potential threats.

Example:

```text
Phishing
Malware
Unauthorized access
Data theft
Account compromise
```

### Step 3 — Vulnerabilities

Identify possible weaknesses.

Example:

```text
Weak passwords
Outdated software
Excessive permissions
Poor security configuration
```

### Step 4 — Risks

Connect the threat and vulnerability.

Example:

```text
Threat:
Attacker

Vulnerability:
Weak administrator password

Risk:
Unauthorized administrative access
```

---

# 25. Day 01 Assignment

### Assignment 1

Explain the following in your own words:

1. Cyber Security
2. Threat
3. Vulnerability
4. Risk
5. Attack
6. Ethical Hacker
7. Penetration Testing

### Assignment 2

Explain the CIA Triad with **one real-world example for each principle**.

### Assignment 3

Create a table containing:

```text
5 Assets
5 Threats
5 Vulnerabilities
5 Possible Risks
```

### Assignment 4

Answer:

> Why is authorization important in ethical hacking?

Write your answer in approximately **150–200 words**.

---

# 26. Day 01 Quick Quiz

**Q1. What does CIA stand for?**

A. Computer Internet Architecture
B. Confidentiality, Integrity, Availability
C. Cyber Intelligence Analysis
D. Confidential Internet Access

**Answer:** B

---

**Q2. Which of the following is a vulnerability?**

A. Attacker
B. Weak password
C. Data theft
D. Security incident

**Answer:** B

---

**Q3. What does authentication determine?**

A. What you can access
B. Who you are
C. How much data you have
D. Which server is online

**Answer:** B

---

**Q4. Who performs authorized security testing?**

A. Ethical hacker
B. Black hat hacker
C. Cybercriminal
D. Attacker

**Answer:** A

---

**Q5. What does authorization determine?**

A. Who you are
B. What you are allowed to access
C. Your IP address
D. Your password

**Answer:** B

---

# 27. Day 01 Key Takeaways

By the end of Day 01, students should understand:

* What cyber security means.
* Why digital security is important.
* The CIA Triad.
* Difference between threats and vulnerabilities.
* What risk means.
* What a cyber attack is.
* Different types of hackers.
* What ethical hacking means.
* What penetration testing means.
* Difference between cyber security and ethical hacking.
* Authentication vs authorization.
* Why authorization is mandatory for security testing.
* Major cyber security career domains.

### The most important concept of Day 01

```text
Cyber Security
      ↓
Protect Digital Assets
      ↓
Against Threats
      ↓
By Managing Vulnerabilities & Risks
      ↓
While Maintaining
Confidentiality + Integrity + Availability
```

**Day 01 practical mindset:**

> **A professional ethical hacker does not simply learn how to attack. They learn how systems work, how weaknesses arise, how those weaknesses can be validated safely, and how organizations can fix them.**
