
# Certified in Cybersecurity – Domain 4: Network Security (ADHD-Friendly Guide)

## How to use this guide

This guide covers all the material from Domain 4 of the ISC² **Certified in Cybersecurity** (CC) course.  It is designed with an ADHD-friendly structure based on evidence-backed learning strategies.  You’ll find concise micro-lessons, analogies, quick quizzes, and plenty of pauses for rest.  The information comes from the official Domain 4 text along with research-based teaching strategies for students with ADHD.

## Overview of Domain 4

Domain 4 of the CC course introduces **computer networking** and the basics of securing networks.  It starts with networking concepts and devices, moves on to common network threats and attacks, and finishes with network security infrastructure.  By the end you will know the terminology of network security, understand how data moves through networks, recognise common threats, and be familiar with data-centre and cloud terminology.

---

## Module 1 – Networking Fundamentals

### 1.1 What is a network?

A **network** is simply two or more computers linked together to share data, information or resources.  Common types include:

| Network type | Example |
|---|---|
| **LAN** – Local Area Network | Your home Wi-Fi or office network
| **WAN** – Wide Area Network | The Internet, or a network connecting multiple offices:content
| **WLAN** – Wireless LAN | Wi-Fi network based on radio transmissions
| **VPN** – Virtual Private Network | Secure tunnel over a public network
| **PAN**/ **EPN**/ **CAN** | Personal (Bluetooth), enterprise, or campus networks

**Analogy:** Think of a network as a **road system**.  LANs are neighbourhood streets; WANs are interstate highways; WLANs are like air routes; and a VPN is an encrypted tunnel protecting your travel.

**Quick quiz:**
1. Which network type connects devices within a small area like a house?
2. How does a VPN differ from a regular connection?

<details><summary>Answer key</summary>
1. LAN / WLAN  
2. A VPN creates a secure, encrypted tunnel over public networks.
</details>

### 1.2 Network devices and their roles

Networks use hardware devices to move and control traffic.  Each plays a distinct role:

* **Hub** – A simple “megaphone” that repeats incoming data to all ports.  It operates at the Physical layer.
* **Switch** – A smart “mail sorter” that sends frames to the correct device based on MAC addresses.
* **Router** – A “GPS dispatcher” that routes packets between networks using IP addresses; this connects LANs and WANs.
* **Firewall** – A “checkpoint booth” that inspects traffic and blocks or allows it based on rules; part of defense in depth.
* **Access Point** – A wireless “off-ramp” connecting devices to a wired network.
* **Repeaters, bridges and gateways** – These extend networks (repeaters), connect network segments (bridges) or translate between protocols (gateways).
* **Endpoints** – Desktops, laptops, tablets, phones or any end-user device.

**Mnemonic:** “**Hub hears all, switch selects, router routes, firewall filters.**”

**Quick quiz:**
1. Which device reads MAC addresses to forward traffic efficiently?
2. Which device connects different IP subnets and chooses the best path?

<details><summary>Answer key</summary>
1. Switch  
2. Router
</details>

### 1.3 Packets, ports and protocols

When data traverses a network, it is packaged into **packets** at Layer 3 of the OSI model.  Each packet carries source and destination IP addresses and a **payload** containing the actual data.

* **Port numbers** are logical connection points that identify specific services.  Ports below 1024 are well-known (e.g., 80 for HTTP, 443 for HTTPS).
* **Protocols** are sets of rules for communication.  For example, HTTP transfers web pages, SMTP sends email, and DNS resolves domain names.

**Analogy:** A packet is like a **postal envelope**: the addresses tell the network where to deliver it; the port is like an apartment number directing it to the right service; and the protocol defines the format of the letter.

**Quick quiz:**
1. What information does a network packet contain?
2. Give two examples of common port numbers and their associated protocols.

<details><summary>Answer key</summary>
1. Source and destination IP addresses plus payload.  
2. 80 – HTTP; 443 – HTTPS.
</details>

### 1.4 The OSI and TCP/IP models

Networks follow layered models to standardise communication.  The **OSI model** has seven layers; from bottom to top they are **Physical, Data-Link, Network, Transport, Session, Presentation, and Application**.  The **TCP/IP model** consolidates these into four layers – **Link, Internet, Transport, and Application**.

**Mnemonic:** *Please Do Not Throw Sausage Pizza Away* – the first letters of the OSI layers (Physical, Data-Link, Network, Transport, Session, Presentation, Application).

**Analogy:** Imagine sending a parcel through a multi-storey mailroom.  At each floor (layer), a clerk adds or strips packaging (headers and footers), ensuring that the parcel gets to the right address and is delivered intact.

**Quick quiz:**
1. Which OSI layer deals with IP routing?
2. How many layers does the TCP/IP model have?

<details><summary>Answer key</summary>
1. Network layer.  
2. Four layers.
</details>

### 1.5 IPv4 versus IPv6

IPv4 is the widely used addressing system, but it has only about four billion unique addresses.  **IPv6** introduces a much larger address field, improved security and better quality of service:contentReference[oaicite:34]{index=34}.  As more devices come online (IoT), IPv6 will gradually replace IPv4.

**Quick quiz:**
1. Name one benefit of IPv6 over IPv4.

<details><summary>Answer key</summary>
1. Larger address space / improved security / improved quality of service.
</details>

---

## Module 2 – Network Threats and Attacks

### 2.1 Common attack categories

**Disruption attacks** aim to overwhelm or destabilise systems.  Examples include:

* **Denial-of-Service (DoS)/Distributed DoS** – Flooding a target with traffic to exhaust resources.
* **Fragment and oversized packet attacks** – Sending traffic fragmented or larger than expected so that systems cannot reassemble it.
* **Privilege escalation / insider threats** – Gaining higher privileges or abusing insider access.

**Deception attacks** focus on tricking systems or users:

* **Spoofing** – Faking the sending address to gain illegal entry.
* **Man-in-the-Middle (on-path)** – Intercepting and possibly altering traffic between two parties.
* **Phishing / social engineering** – Fraudulent messages to obtain credentials.

**Malware and code injection** attacks deliver malicious software or code:

* **Virus** – Malicious code that attaches itself to files or programs and replicates when executed.
* **Worm** – Self-replicating malware that spreads across networks without user interaction.
* **Trojan** – Malicious software disguised as legitimate software.
* **Rootkit, spyware/adware** – Hides presence or spies on user activity.
* **Code/SQL injection and XSS** – Inserting malicious code into applications or websites.

**Quick quiz:**
1. How does a worm differ from a virus?
2. What is the goal of a man-in-the-middle attack?

<details><summary>Answer key</summary>
1. A worm spreads without user intervention, whereas a virus needs an executable host.  
2. To intercept and potentially alter data between two parties.
</details>

### 2.2 Ports and secure alternatives

Many attacks exploit insecure protocols.  Knowing the default and secure ports helps you choose safer options.  The table below lists some examples (memorise three at a time):

| Service | Insecure port/protocol | Secure alternative |
|---|---|---|
| **FTP** | 21 – File Transfer Protocol | 22 – SFTP / SSH |
| **Telnet** | 23 – Telnet | 22 – SSH |
| **SMTP** | 25 – SMTP | 587 – SMTP with TLS |
| **Time sync** | 37 – Time Protocol | 123 – NTP |
| **DNS** | 53 – DNS | 853 – DNS over TLS (DoT) |
| **HTTP** | 80 – HTTP | 443 – HTTPS |
| **IMAP** | 143 – IMAP | 993 – IMAP over SSL/TLS |
| **SMB** | 445 – SMB | 2049 – NFS (alternative secure file service) |
| **LDAP** | 389 – LDAP | 636 – LDAPS |

**Quick quiz:**
1. Which port is used for secure web traffic?
2. What secure protocol replaces FTP?

<details><summary>Answer key</summary>
1. Port 443 – HTTPS.  
2. SFTP (SSH File Transfer Protocol) on port 22.
</details>

### 2.3 Threat identification and prevention

To detect and mitigate attacks, organisations use a combination of monitoring and defensive tools:

* **IDS (Intrusion Detection System)** – Monitors network or host activity to identify malicious behaviour.  A **NIDS** watches network traffic; a **HIDS** monitors activity on a single host.
* **SIEM (Security Information and Event Management)** – Centralises and correlates logs and alerts for analysis.
* **IPS/NIPS/HIPS (Intrusion Prevention System)** – Similar to IDS but actively blocks suspicious traffic.
* **Antivirus and malware scanners** – Detect and remove malicious software.
* **Firewalls** – Enforce rules to allow or deny traffic based on ports, protocols or content.

**Analogy:** Think of IDS as a **security camera** that alerts you to suspicious activity, and IPS as a **security guard** who can intervene.

**Quick quiz:**
1. What is the difference between IDS and IPS?
2. Why is SIEM useful in threat detection?

<details><summary>Answer key</summary>
1. IDS monitors and alerts; IPS actively blocks malicious traffic.  
2. SIEM aggregates logs and alerts from multiple systems, enabling correlation and rapid response.
</details>

---

## Module 3 – Network Security Infrastructure

### 3.1 Data centre requirements

On-premises data centres must ensure physical and operational resilience.  Key requirements include **power**, **HVAC** (heating, ventilation and air conditioning), **fire suppression**, **redundancy**, and formal agreements (MOU/MOA).

* **Power and redundancy** – Dual power supplies and backup generators keep servers running during outages.
* **HVAC** – Cooling systems maintain safe temperatures.
* **Fire suppression** – Systems such as inert gas or sprinkler systems protect equipment from fires.
* **Redundancy** – Duplicate critical components (servers, power, network links) improve uptime.
* **MOU/MOA (Memorandum of Understanding/Agreement)** – Defines responsibilities when sharing data centre facilities or services.

**Analogy:** A data centre is like a **hospital** for computers – it needs electricity (life support), climate control, fire alarms and clear agreements between staff.

**Quick quiz:**
1. Why is redundancy important in a data centre?
2. What does HVAC stand for?

<details><summary>Answer key</summary>
1. It ensures that if one component fails, others maintain service.  
2. Heating, ventilation and air conditioning.
</details>

### 3.2 Cloud service and deployment models

Cloud computing offers on-demand access to configurable resources.  There are three main service models:

* **SaaS (Software as a Service)** – The cloud provider hosts applications; the customer uses them via a web browser.  The consumer does not manage the underlying infrastructure.
* **PaaS (Platform as a Service)** – The provider delivers a development platform and runtime; customers build and deploy their own applications.
* **IaaS (Infrastructure as a Service)** – The provider supplies virtualised computing resources; customers control operating systems and applications.

Deployment models describe who owns and uses the cloud:

* **Public cloud** – Services are available to the general public; infrastructure is managed by the provider.
* **Private cloud** – Hosted within an organisation’s firewall; provides greater control over data and compliance.
* **Community cloud** – Shared among organisations with common concerns (e.g., healthcare providers).
* **Hybrid cloud** – Combines private and public resources to balance control and scalability.

**Quick quiz:**
1. Which service model lets you use applications without managing servers?
2. What is the main difference between public and private clouds?

<details><summary>Answer key</summary>
1. SaaS.  
2. Public clouds are shared and operated by a provider; private clouds are dedicated to one organisation and managed internally.
</details>

### 3.3 Network design principles

Secure networks are built with layered defences and logical separation:

* **Network segmentation / microsegmentation** – Divides networks into smaller zones to limit the blast radius of an incident.  A DMZ (demilitarised zone) is a segment exposed to the Internet but isolated from the internal network.
* **VLAN (Virtual Local Area Network)** – Creates logical groupings of devices regardless of physical location.
* **VPN (Virtual Private Network)** – Provides secure, encrypted communication over untrusted networks.
* **Defense in depth** – Deploys multiple overlapping controls (firewalls, IDS/IPS, antivirus) to mitigate failures in any single layer.
* **Zero trust** – Assumes no part of the network is trusted; security is enforced at every level and microsegmentation is applied.
* **Network Access Control (NAC)** – Ensures only authorised devices can connect to the network, often by evaluating device health and credentials.

**Quick quiz:**
1. What is the purpose of a DMZ?
2. How does zero trust differ from traditional perimeter security?

<details><summary>Answer key</summary>
1. To host public-facing services (e.g., web servers) while isolating them from the internal network.  
2. Zero trust removes the assumption of a trusted internal network and enforces authentication and authorization everywhere.
</details>

---

## Study tips and next steps

1. **Active recall and spaced repetition:** After completing each micro-lesson, close the guide and try to recall the key points.  Repeat the quiz questions after 24 hours, 48 hours and one week to strengthen memory.
2. **Pomodoro technique:** Study in 25-minute blocks with 5-minute breaks.  During breaks, stretch or squeeze a stress ball to release restlessness.
3. **Use incentives:** Reward yourself with a treat or enjoyable activity after finishing a module.  Positive reinforcements should be frequent and meaningful.
4. **Alternate topics:** Mix practice quizzes or hands-on labs between reading sessions to maintain engagement.
5. **Leverage technology:** Flashcard apps, network simulators and typing your own summaries can make study more interactive.
6. **Visual aids and mind maps:** Draw the OSI layers as floors of a building or map how devices connect.  Listing lesson activities at the start and summarising key points at the end helps maintain focus.
7. **Monitor and adjust:** If a strategy stops working, tweak it.  Interventions often lose effectiveness over time.
