# TechNova Enterprise Network Project Checklist

This checklist outlines all phases and tasks for designing, configuring, and documenting the TechNova Solutions enterprise network. Check off tasks as they are completed to track progress.

---

## Phase 1 – Planning & Requirements

- [ ] Define company profile  
- [ ] Identify departments and user counts  
- [ ] Define security requirements
- [ ] Define internet and internal access needs  
- [ ] Define scalability and growth assumptions  
- [ ] Document scope (in-scope / out-of-scope)

**Deliverables**
- [ ] `docs/project_overview.md`  
- [ ] `docs/assumptions_and_limitations.md`

---

## Phase 2 – High-Level Design

- [ ] Select three-tier hierarchical architecture (Core, Distribution, Access)  
- [ ] Justify architecture choice in documentation  
- [ ] Select routing protocol (OSPF)  
- [ ] Decide inter-VLAN routing method (L3 switch or router-on-a-stick)  
- [ ] Identify core, distribution, and access layer roles

**Deliverables**
- [ ] `docs/network_architecture.md`

---

## Phase 3 – VLAN & IP Addressing

- [ ] Define VLAN IDs and names  
- [ ] Assign departments to VLANs  
- [ ] Design IP subnets per VLAN  
- [ ] Define default gateways  
- [ ] Decide DHCP vs static IP allocation  
- [ ] Reserve addresses for infrastructure devices

**Deliverables**
- [ ] `docs/vlan_and_ip_addressing.md`

---

## Phase 4 – Diagrams & Topology

- [ ] Create logical network diagram  
- [ ] Create physical topology diagram  
- [ ] Show VLAN segmentation and trunk links  
- [ ] Indicate routing points  
- [ ] Indicate redundant links

**Deliverables**
- [ ] `diagrams/logical_network_diagram.png`  
- [ ] `diagrams/physical_topology_diagram.png`

---

## Phase 5 – Device Selection & Base Setup

- [ ] Select router model(s)  
- [ ] Select access and distribution switch models  
- [ ] Place devices in Packet Tracer  
- [ ] Connect devices using correct cables  
- [ ] Label devices and interfaces  
- [ ] Set hostnames on all devices

**Deliverables**
- [ ] Base Packet Tracer topology

---

## Phase 6 – Switching Configuration

- [ ] Create all VLANs on switches  
- [ ] Assign access ports to correct VLANs  
- [ ] Configure trunk ports (802.1Q)  
- [ ] Set native VLAN  
- [ ] Verify VLAN configuration (`show vlan brief`)  
- [ ] Verify trunk status (`show interfaces trunk`)

**Deliverables**
- [ ] `configs/access/*.txt`

---

## Phase 7 – Inter-VLAN Routing

- [ ] Configure SVIs or router sub-interfaces  
- [ ] Assign IP addresses to gateways  
- [ ] Enable routing (if using Layer 3 switch)  
- [ ] Verify inter-VLAN connectivity (ping between VLANs)

**Deliverables**
- [ ] `configs/distribution/*.txt`

---

## Phase 8 – Dynamic Routing (OSPF)

- [ ] Configure router IDs  
- [ ] Configure OSPF area(s)  
- [ ] Advertise VLAN and WAN networks  
- [ ] Verify OSPF neighbor relationships (`show ip ospf neighbor`)  
- [ ] Verify routing table (`show ip route`)

**Deliverables**
- [ ] `docs/routing_and_switching.md`

---

## Phase 9 – Network Services

- [ ] Configure DHCP pools per VLAN  
- [ ] Exclude gateway and infrastructure IPs  
- [ ] Verify DHCP assignment  
- [ ] Configure DNS (simulated)  
- [ ] Configure NAT/PAT for internet access  
- [ ] Verify external connectivity

**Deliverables**
- [ ] `services/dhcp_configuration.md`  
- [ ] `services/dns_configuration.md`  
- [ ] `services/nat_configuration.md`

---

## Phase 10 – Security Implementation

- [ ] Design ACL policy for inter-VLAN restrictions  
- [ ] Configure extended ACLs  
- [ ] Restrict Guest VLAN to internet only  
- [ ] Protect HR and Management VLANs  
- [ ] Apply ACLs to correct interfaces  
- [ ] Verify allowed and denied traffic

**Deliverables**
- [ ] `docs/security_design.md`

---

## Phase 11 – Access Layer Security

- [ ] Enable port security  
- [ ] Limit MAC addresses per port  
- [ ] Configure violation mode (shutdown/restrict)  
- [ ] Disable unused switch ports  
- [ ] Enable BPDU Guard (if available)

**Deliverables**
- [ ] Updated access switch configurations

---

## Phase 12 – High Availability & Redundancy

- [ ] Enable STP (PVST+ recommended)  
- [ ] Set root bridge priority  
- [ ] Implement redundant links  
- [ ] Simulate link failure  
- [ ] Verify network recovery

**Verification**
- [ ] `show spanning-tree`

**Deliverables**
- [ ] `docs/high_availability.md`

---

## Phase 13 – Testing & Validation

- [ ] Test inter-VLAN communication  
- [ ] Test ACL restrictions  
- [ ] Test DHCP per VLAN  
- [ ] Test NAT and internet access  
- [ ] Test management VLAN access  
- [ ] Document expected vs actual results

**Deliverables**
- [ ] `docs/testing_and_validation.md`

---

## Phase 14 – Final Review & Packaging

- [ ] Clean configurations  
- [ ] Add comments to all configs  
- [ ] Verify naming conventions  
- [ ] Validate diagrams match topology  
- [ ] Save final Packet Tracer file  
- [ ] Prepare README.md

**Final Deliverables**
- [ ] `packet_tracer/technova_enterprise_network.pkt`  
- [ ] `README.md`  
- [ ] Complete documentation folder

---

## Completion

- [ ] Enterprise-grade simulated network is fully configured  
- [ ] Documentation is complete and organized  
- [ ] Project is portfolio-ready and follows professional methodology
