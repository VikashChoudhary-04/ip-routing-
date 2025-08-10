# IP Routing in Cisco Packet Tracer – Step-by-Step Guide

## 📌 Overview

This repository provides a complete step-by-step guide to set up IP Routing in Cisco Packet Tracer using the following topology:

(1) 3 Routers

(2) 3 Switches

(3) 6 PCs

(4) IP Addressing Scheme with 255.224.0.0 subnet mask (as this is according to 10.0.0.0/11)


This guide is beginner-friendly and will walk you through device configuration, IP addressing, routing table setup, and PC connectivity testing.


---

## 🖥 Network Topology

### Connections:

Router0 G0/0 ↔ Router1 G0/0

Router0 G0/1 ↔ Switch0 Fa0/1

Router1 G0/1 ↔ Router2 G0/0

Router1 G0/2 ↔ Switch1 Fa0/1

Router2 G0/1 ↔ Switch2 Fa0/1

Switch2 Fa0/2 ↔ PC4 Fa0

Switch2 Fa0/3 ↔ PC5 Fa0

Switch1 Fa0/2 ↔ PC2 Fa0

Switch1 Fa0/3 ↔ PC3 Fa0

Switch0 Fa0/2 ↔ PC0 Fa0

Switch0 Fa0/3 ↔ PC1 Fa0



---

## 🌐 IP Addressing Table

Device & Interface |	IP Address |	Subnet Mask |
-------------------|-------------|--------------|
Router0 G0/0       | 10.0.0.1    | 255.224.0.0  |
Router1 G0/0       | 10.0.0.2    | 255.224.0.0  |
Router1 G0/1       | 20.0.0.5    | 255.224.0.0  |
Router2 G0/0       | 20.0.0.6    | 255.224.0.0  |
Router0 G0/1       | 10.32.0.2   | 255.224.0.0  |
PC0 Fa0	           | 10.32.0.3   | 255.224.0.0  |
PC1 Fa0	           | 10.32.0.4	 | 255.224.0.0  |
Router1 G0/2       | 10.64.0.3   | 255.224.0.0  |
PC2 Fa0            | 10.64.0.4   | 255.224.0.0  |
PC3 Fa0	           | 10.64.0.6	 | 255.224.0.0  |
Router2 G0/1       | 10.96.0.4   | 255.224.0.0  |
PC4 Fa0            | 10.96.0.5   | 255.224.0.0  |
PC5 Fa0	           | 10.96.0.6   | 255.224.0.0  |



---

## ⚙ Step-by-Step Configuration Guide

### 1️⃣ Open Cisco Packet Tracer

Launch Cisco Packet Tracer on your system.



---

### 2️⃣ Build the Topology

Drag and drop:

3 Routers

3 Switches

6 PCs


Connect them as per the Network Topology section above.



---

### 3️⃣ Configure Router Interfaces

Router0

```bash
enable
configure terminal
interface gig0/0
ip address 10.0.0.1 255.224.0.0
no shutdown
exit
interface gig0/1
ip address 10.32.0.2 255.224.0.0
no shutdown
exit
ip route 10.64.0.0 255.224.0.0 10.0.0.2
ip route 20.0.0.0 255.224.0.0 10.0.0.2
ip route 10.96.0.0 255.224.0.0 20.0.0.6
```

Router1

```bash
enable
configure terminal
interface gig0/0
ip address 10.0.0.2 255.224.0.0
no shutdown
exit
interface gig0/1
ip address 20.0.0.1 255.224.0.0
no shutdown
exit
interface gig0/2
ip address 10.64.0.3 255.224.0.0
no shutdown
exit
ip route 10.32.0.0 255.224.0.0 10.0.0.1
ip route 10.96.0.0 255.224.0.0 20.0.0.6
```
Router2

```bash
enable
configure terminal
interface gig0/0
ip address 20.0.0.2 255.224.0.0
no shutdown
exit
interface gig0/1
ip address 10.96.0.4 255.224.0.0
no shutdown
exit
ip route 10.64.0.0 255.224.0.0 20.0.0.5
ip route 10.0.0.0 255.224.0.0 20.0.0.5
ip route 10.32.0.0 255.224.0.0 10.0.0.1

```

---

### 4️⃣ Configure PCs

PC | IP Address | Subnet Mask | Default Gateway |
---|------------|-------------|-----------------|
PC0| 10.32.0.3	| 255.224.0.0	| 10.32.0.2       |
PC1| 10.32.0.4	| 255.224.0.0	| 10.32.0.2       |
PC2| 10.64.0.4	| 255.224.0.0	| 10.64.0.3       |
PC3| 10.64.0.6	| 255.224.0.0	| 10.64.0.3       |
PC4| 10.96.0.5	| 255.224.0.0	| 10.96.0.4       |
PC5| 10.96.0.6	| 255.224.0.0	| 10.96.0.4       |



---

### 5️⃣ Test Connectivity

Use the ping command from any PC to another PC in a different network.

Example:


ping 10.96.0.5 (from Router2)


---

## ✅ Result

If configured correctly:

All PCs should be able to communicate across different networks.

You have successfully implemented IP routing in Cisco Packet Tracer.



---

## 📂 Files in this Repository

IP_Routing.pkt → Cisco Packet Tracer project file

README.md → This step-by-step guide



---

## 📢 Author

Created by Vikash Choudhary – Networking Enthusiast & Learner.
