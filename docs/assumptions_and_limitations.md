# Assumptions and Limitations

This document outlines the assumptions made and limitations considered during the design and implementation of the TechNova Solutions enterprise network project.

---

## Assumptions

1. **Company Size and Users**
   - TechNova Solutions is a mid-sized company with approximately 150 users distributed across five departments (Administration, Development, HR, Sales & Marketing, and Guest users).
   
2. **Network Devices**
   - Routers and switches used in the simulation are representative of real enterprise-grade devices.  
   - All devices support VLANs, trunking, OSPF, ACLs, STP, and port security.

3. **Services**
   - Centralized DHCP, DNS, and NAT services are simulated within Packet Tracer.  
   - Internet access is simulated using NAT for testing purposes.

4. **Security**
   - All users comply with organizational security policies.  
   - Guest network users are isolated and only require internet access.  
   - Inter-department communication is restricted as per ACL rules.

5. **Topology**
   - The three-tier hierarchical model (Core, Distribution, Access) is sufficient to demonstrate scalability and high availability.  
   - Redundant links are assumed to prevent single points of failure.

6. **IP Addressing**
   - Private IP addressing is used for all internal networks.  
   - Static IPs are reserved for network infrastructure; DHCP is used for end devices.

7. **Simulation Environment**
   - All configurations are tested within Cisco Packet Tracer.  
   - All devices are assumed to be functional and properly powered on during testing.

---

## Limitations

1. **Simulation Constraints**
   - Packet Tracer does not fully emulate real-world device performance or traffic load.  
   - Advanced features such as QoS, VPNs, or real-time voice/video traffic are not simulated.

2. **Wireless Networks**
   - Wireless LANs, Wi-Fi access points, and mobile device connectivity are not included in this project.

3. **External Connectivity**
   - Internet access is simulated using NAT; no actual internet connectivity is established.

4. **High-Scale Performance**
   - The network is designed for mid-sized scale. High-scale enterprise optimizations are not covered.

5. **Physical Infrastructure**
   - Cabling, rack placement, and real-world physical constraints are not modeled.  

6. **Security Scope**
   - Firewall appliances, intrusion detection/prevention systems, and advanced endpoint security measures are out of scope.

7. **Management Tools**
   - Network management tools (SNMP, NetFlow, monitoring software) are not implemented.

---

**Note:** These assumptions and limitations help define the boundaries of the project and provide clarity for reviewers regarding the design decisions and scope.
