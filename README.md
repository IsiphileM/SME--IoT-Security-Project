# 🏢Project: SME IoT Secure Network Architecture (Cisco Packet Tracer)

### Project Specifications
* **Primary Function:** Enterprise Network Segmentation & Security Enforcement
* **Core Technologies:** VLANs | ACLs | Inter-VLAN Routing | Cisco ASA Firewall
* **Security Model:** Defense-in-Depth Architecture
* **Simulation Platform:** Cisco Packet Tracer
* **Operational Status:** ACTIVE / Security Validation Phase
* **Application Scope:** Enterprise Networking + CCNA Security Fundamentals

---

## Project Overview

This project simulates a **real-world SME enterprise network environment** with a strong emphasis on **IoT isolation, internal threat containment, and perimeter defense**.

The architecture was intentionally designed to reflect how modern organizations mitigate:
- Internal malicious users (insider threats)
- External attackers
- Vulnerable IoT device exposure
- Lateral movement across networks

In simple terms:  
> “Nobody talks to everyone. And IoT devices definitely don’t get opinions.”

---

## Network Architecture

### Core Infrastructure Components

* **Edge Router**
  - Acts as the WAN gateway
  - Handles external connectivity and routing decisions

* **Layer 2 Switch**
  - Provides VLAN-based segmentation at the access layer
  - Handles MAC address forwarding within VLANs

* **Multilayer Switch (Layer 3 Core)**
  - Performs inter-VLAN routing
  - Enforces ACL-based traffic control
  - Serves as internal traffic control hub

* **Cisco ASA Firewall**
  - Perimeter security enforcement
  - Filters inbound/outbound traffic
  - Blocks unauthorized access attempts and DoS traffic

---

## LAN Segmentation Design

| VLAN | Purpose | Security Classification |
|------|--------|------------------------|
| VLAN 10 | Trusted End Users (PCs) | High Trust |
| VLAN 20 | Internal Users / Staff | Medium Trust |
| VLAN 30 | Attacker Simulation Zone | Untrusted / Isolated |
| VLAN 40 | IoT Device Network | Restricted / Monitored |

### Design Principle
The network is segmented to enforce **strict trust boundaries**, ensuring:
- No flat network communication
- Controlled inter-VLAN access
- Isolation of high-risk IoT devices

---

## Security Implementation

### 1. Access Control Lists (ACLs)
ACLs were implemented on the multilayer switch and router to:

- Block unauthorized inter-VLAN communication
- Prevent attacker VLAN (VLAN 30) from accessing internal systems
- Allow only explicitly permitted traffic flows

Security Principle: *Implicit deny by default*

---

### 2. Inter-VLAN Routing Control
Routing between VLANs is centrally controlled via the multilayer switch, ensuring:
- Traffic inspection before forwarding
- Policy-based access enforcement
- Controlled segmentation enforcement

---

### 3. Cisco ASA Firewall Configuration
The firewall acts as the **first and last line of defense**:

- Filters external traffic before it enters internal network
- Blocks unauthorized inbound requests
- Prevents external reconnaissance attempts
- Mitigates DoS attack simulations

---

### 4. IoT Security Isolation
IoT devices (VLAN 40) are:
- Segmented from critical infrastructure
- Restricted from unrestricted communication
- Accessible only through controlled VLAN pathways

Because IoT devices should never be trusted. Ever.

---

## Security Testing & Validation

### Internal Threat Simulation (VLAN 30 - Attacker Zone)

| Test Case | Result |
|-----------|--------|
| Ping VLAN 10 (Trusted PCs) | ❌ Blocked |
| Ping VLAN 20 (Internal Users) | ❌ Blocked |
| Ping VLAN 40 (IoT Devices) | ❌ Blocked |
| Intra-VLAN Communication | ✅ Allowed |

**Conclusion:** Attacker containment successfully enforced. No lateral movement possible.

---

### Trusted Network Communication

| Test Case | Result |
|-----------|--------|
| VLAN 10 → VLAN 20 | ✅ Success |
| VLAN 10 → VLAN 40 | ✅ Success (Controlled) |
| VLAN 20 → VLAN 40 | ✅ Success (Policy-based) |

**Conclusion:** Controlled inter-VLAN routing functions as expected.

---

### External Attack Simulation

| Test Case | Result |
|-----------|--------|
| Ping Internal DHCP Server | ❌ Blocked |
| External Network Recon Attempts | ❌ Blocked |
| DoS Attack Simulation | ❌ Failed |

**Conclusion:** ASA firewall successfully prevents external intrusion attempts.

---

## Security Outcomes

This architecture successfully demonstrates:

- Network segmentation using VLANs
- Layered security enforcement (Switch + Router + Firewall)
- ACL-based traffic filtering
- IoT isolation strategy
- Internal attacker containment
- External perimeter defense

---

## 🎯 CCNA Exam Alignment

This project directly maps to key CCNA objectives:

### Network Fundamentals
- VLAN segmentation
- MAC vs IP forwarding behavior
- Switch vs router roles

### IP Connectivity
- Inter-VLAN routing (Layer 3 switching)
- Static routing concepts (edge router behavior)

### Security Fundamentals
- ACL configuration and filtering logic
- Firewall security policies (ASA basics)
- Network segmentation for threat mitigation

### Network Access
- VLAN trunking concepts
- Access vs trunk port behavior
- Device role separation

---

## Professional Relevance

This project simulates real enterprise environments where:
- IoT devices are treated as high-risk endpoints
- Internal users are segmented by trust level
- Traffic is governed by explicit security policies
- Firewalls enforce perimeter defense strategies

---

## Key Skills Demonstrated

- Enterprise network design (SME scale)
- Cisco Packet Tracer configuration
- VLAN & subnet segmentation strategy
- ACL policy design and implementation
- Firewall rule enforcement (ASA)
- Threat simulation & validation testing
- Defense-in-depth architecture design

---

## Future Improvements

- Implementation of IDS/IPS (Intrusion Detection/Prevention System)
- VPN remote access for secure offsite connectivity
- Network monitoring via SNMP/syslog integration
- Zero Trust architecture upgrade
- Dynamic routing protocols (OSPF/EIGRP integration)

---

## Final Note

This project was built to simulate how real-world enterprise networks enforce **security boundaries, not assumptions**.

Or in simpler terms:
> “If you’re not explicitly allowed in, you’re not getting in.”

---
