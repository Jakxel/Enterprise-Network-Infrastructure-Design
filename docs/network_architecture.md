# Network Architecture Design

This document describes the network architecture selected for the TechNova Solutions enterprise network project. It explains the architectural model, routing strategy, inter-VLAN routing method, and the roles of each network layer.

---

## Architectural Overview

The TechNova Solutions network is designed using a **three-tier hierarchical architecture**, consisting of the **Core**, **Distribution**, and **Access** layers. This model is widely adopted in enterprise networks due to its scalability, modularity, performance, and ease of management.

The architecture supports departmental segmentation through VLANs, centralized services, secure traffic control, and high availability through redundancy and Spanning Tree Protocol (STP).

---

## Three-Tier Hierarchical Architecture

### 1. Core Layer

**Role:**
- Acts as the high-speed backbone of the network.
- Provides fast and reliable data forwarding between distribution layer devices.
- Ensures minimal latency and high availability.

**Responsibilities:**
- High-speed routing between major network segments.
- Interconnection to external networks (simulated internet).
- Redundant paths to prevent single points of failure.

**Design Characteristics:**
- No policy enforcement to avoid performance bottlenecks.
- Optimized for speed and reliability.

---

### 2. Distribution Layer

**Role:**
- Serves as the control and policy enforcement point between the core and access layers.
- Aggregates access layer traffic and applies routing and security policies.

**Responsibilities:**
- Inter-VLAN routing.
- Implementation of ACLs for traffic control.
- Participation in dynamic routing (OSPF).
- Acting as the default gateway for VLANs.

**Inter-VLAN Routing Method:**
- **Layer 3 Switching using Switch Virtual Interfaces (SVIs)** is selected.
- This method provides better performance and scalability compared to router-on-a-stick.
- Enables routing directly on the distribution switches without relying on external routers.

---

### 3. Access Layer

**Role:**
- Provides direct network connectivity to end devices.

**Responsibilities:**
- VLAN assignment for end devices.
- Port security enforcement.
- Disabling unused ports.
- Forwarding traffic to the distribution layer.

**Design Characteristics:**
- Access ports configured per department VLAN.
- Trunk links uplinked to distribution switches.
- Security controls applied closest to users.

---

## Architecture Justification

The three-tier hierarchical architecture was selected because it:

- **Improves scalability** by allowing easy expansion of users and departments.
- **Enhances fault isolation**, ensuring failures at the access layer do not impact the core.
- **Simplifies troubleshooting** through clear separation of roles.
- **Aligns with enterprise best practices** used in real-world corporate environments.
- **Supports redundancy and high availability** through multiple paths and STP.

This architecture is well-suited for a mid-sized organization such as TechNova Solutions and allows future growth without major redesign.

---

## Routing Design

### Routing Protocol Selection: OSPF

**Open Shortest Path First (OSPF)** is used as the dynamic routing protocol for this network.

**Justification:**
- Open standard and widely supported.
- Fast convergence compared to distance-vector protocols.
- Scales well for enterprise environments.
- Supports hierarchical design using areas.

**Design Approach:**
- Single OSPF Area (Area 0) for simplicity.
- All routed interfaces participate in OSPF.
- Router IDs are manually defined for consistency.

---

## Inter-VLAN Routing Strategy

**Chosen Method:** Layer 3 Switching (SVIs)

**Reasons for Selection:**
- Higher throughput than router-on-a-stick.
- Reduces dependency on a single routing device.
- Better suited for enterprise distribution layers.
- Simplifies VLAN gateway configuration.

Each VLAN has a corresponding SVI configured on the distribution switches, serving as the default gateway for that VLAN.

---

## Layer Responsibilities Summary

| Layer          | Primary Function                          |
|---------------|--------------------------------------------|
| Core          | High-speed routing and backbone connectivity |
| Distribution | Inter-VLAN routing, ACLs, OSPF, policy enforcement |
| Access        | End-device connectivity, VLAN assignment, port security |

---

## Conclusion

The selected network architecture provides a structured, scalable, and secure foundation for the TechNova Solutions enterprise network. By leveraging a three-tier hierarchical model, dynamic routing with OSPF, and Layer 3 switching for inter-VLAN routing, the design aligns with real-world enterprise networking standards and best practices.


