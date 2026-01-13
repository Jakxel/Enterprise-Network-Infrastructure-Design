# Enterprise Network Infrastructure Design  
**Case Study: TechNova Solutions**

## Overview
This project presents the design and implementation of a **simulated enterprise network infrastructure** for a mid-sized technology company called **TechNova Solutions**. The objective is to demonstrate practical skills in **network planning, routing, switching, security, and documentation** using industry best practices.

The network is designed and implemented using **Cisco Packet Tracer**, following a **hierarchical architecture** to ensure scalability, security, and reliability.

---

## Objectives
- Design a scalable and secure enterprise network
- Apply VLAN segmentation and inter-VLAN routing
- Implement dynamic routing and centralized network services
- Enforce security policies using ACLs and port security
- Simulate redundancy and fault tolerance
- Document technical decisions and configurations clearly

---

## Network Architecture
The network follows a **three-layer hierarchical model**:

- **Core Layer** – High-speed routing and backbone connectivity  
- **Distribution Layer** – Inter-VLAN routing and policy enforcement  
- **Access Layer** – End-device connectivity and VLAN assignment  

The infrastructure is segmented into multiple **VLANs** to isolate departments and control traffic flow. Centralized services such as **DHCP, DNS, and NAT** are implemented to simplify management.

---

## VLAN and IP Addressing Plan

| VLAN | Department                 | Subnet            |
|-----:|----------------------------|-------------------|
| 10   | Administration             | 192.168.10.0/24  |
| 20   | Development / Engineering  | 192.168.20.0/24  |
| 30   | Human Resources            | 192.168.30.0/24  |
| 40   | Sales & Marketing          | 192.168.40.0/24  |
| 50   | Guest Network              | 192.168.50.0/24  |
| 99   | Network Management         | 192.168.99.0/24  |

---

## Technologies and Tools
- **Cisco Packet Tracer**
- Cisco Routers and Switches
- VLANs & Trunking (802.1Q)
- Inter-VLAN Routing
- **OSPF** (Dynamic Routing)
- **DHCP & DNS** (Simulated)
- **NAT / PAT**
- **ACLs (Standard & Extended)**
- **Port Security**
- **Spanning Tree Protocol (STP)**

---

## Security Implementation
- VLAN-based network segmentation
- Extended ACLs to control inter-department communication
- Strict isolation of the **Guest Network**
- Port Security on access switches
- Management VLAN for administrative access

---

## High Availability & Best Practices
- Redundant links between network devices
- STP enabled to prevent switching loops
- Consistent naming conventions for devices and interfaces
- Clear labeling and structured configuration

---

## Testing and Validation
The following tests were performed to validate the network:

- Connectivity testing between authorized VLANs
- Verification of ACL restrictions
- DHCP address assignment per VLAN
- Internet access via NAT
- Simulated link failures and recovery testing

---

## Project Structure
```text
/diagrams
  - network_diagram.png
/configs
  - router_configs.txt
  - switch_configs.txt
/docs
  - ip_addressing_plan.md
  - vlan_table.md
README.md
