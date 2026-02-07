# VLAN and IP Addressing Design

This document defines the VLAN segmentation and IP addressing scheme for the TechNova Solutions enterprise network. The design ensures logical separation of departments, efficient IP address utilization, simplified network management, and enhanced security.

---

## VLAN Design Overview

Virtual Local Area Networks (VLANs) are implemented to logically segment the network by department. This segmentation reduces broadcast domains, improves security, and allows for controlled inter-department communication through routing and access control policies.

---

## VLAN Identification and Department Assignment

The following VLANs are defined for the TechNova Solutions network:

| VLAN ID | VLAN Name        | Department               |
|-------:|------------------|--------------------------|
| 10     | ADMIN            | Administration           |
| 20     | DEV              | Development / Engineering|
| 30     | HR               | Human Resources          |
| 40     | SALES            | Sales & Marketing        |
| 50     | GUEST            | Guest Network            |
| 99     | MGMT             | Network Management       |

Each department is assigned a dedicated VLAN to ensure traffic isolation and enforce security policies.

---

## IP Addressing Strategy

### IP Addressing Model
- Private IPv4 addressing is used throughout the internal network.
- Each VLAN is assigned a unique `/24` subnet to simplify management and allow future growth.
- Subnetting provides logical separation and predictable addressing.

---

## VLAN Subnet Allocation

| VLAN ID | Department        | Subnet              | Default Gateway      |
|-------:|-------------------|---------------------|----------------------|
| 10     | Administration   | 192.168.10.0/24     | 192.168.10.1         |
| 20     | Development      | 192.168.20.0/24     | 192.168.20.1         |
| 30     | Human Resources  | 192.168.30.0/24     | 192.168.30.1         |
| 40     | Sales & Marketing| 192.168.40.0/24     | 192.168.40.1         |
| 50     | Guest Network    | 192.168.50.0/24     | 192.168.50.1         |
| 99     | Management       | 192.168.99.0/24     | 192.168.99.1         |

The default gateway for each VLAN is configured on the distribution layer switches using Switch Virtual Interfaces (SVIs).

---

## Default Gateway Design

- Each VLAN has a corresponding SVI acting as its default gateway.
- Default gateways are standardized using the `.1` address in each subnet.
- This approach improves consistency, troubleshooting, and documentation clarity.

---

## IP Address Allocation Policy

### Dynamic IP Allocation (DHCP)
DHCP is used for end-user devices in the following VLANs:
- Administration (VLAN 10)
- Development (VLAN 20)
- Human Resources (VLAN 30)
- Sales & Marketing (VLAN 40)
- Guest Network (VLAN 50)

**Benefits:**
- Simplifies IP address management
- Reduces configuration errors
- Supports user mobility

---

### Static IP Allocation

Static IP addresses are reserved for:
- Routers and Layer 3 switches
- Switch management interfaces
- Servers and network services (DHCP, DNS)
- Network infrastructure devices

---

## Reserved IP Address Ranges

The following address ranges are reserved in each subnet for infrastructure devices:

| VLAN ID | Reserved Range            | Purpose                     |
|-------:|---------------------------|-----------------------------|
| All    | x.x.x.1 – x.x.x.20        | Gateways & Infrastructure   |
| All    | x.x.x.21 – x.x.x.200      | DHCP Address Pool           |
| All    | x.x.x.201 – x.x.x.254     | Future Expansion / Servers  |

This reservation strategy prevents IP conflicts and allows structured growth.

---

## Design Justification

- VLAN segmentation enhances security and traffic management.
- /24 subnets provide ample addressing capacity for departmental growth.
- Standardized gateway addressing simplifies operations.
- DHCP reduces administrative overhead.
- Static addressing ensures stability for critical infrastructure.

---

## Conclusion

The VLAN and IP addressing design for TechNova Solutions provides a scalable, secure, and manageable foundation for the enterprise network. This structured approach supports departmental isolation, centralized services, and aligns with industry best practices for enterprise network design.
