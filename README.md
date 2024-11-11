# Computer Networks Project

## Project Overview
This project presents a comprehensive network topology designed and implemented in Cisco Packet Tracer. The network is segmented into multiple blocks, each utilizing different routing protocols and addressing schemes to simulate a realistic enterprise network environment. The network supports inter-VLAN communication, dynamic IP addressing, network address translation (NAT), and route redistribution to enable seamless connectivity across different segments.

### Network Topology
The network is structured into three primary blocks, each configured with a distinct routing protocol:
- **First Block**: Configured with EIGRP.
- **Second Block**: Configured with OSPF in Area 1.
- **Third Block**: Configured with RIP.
- **Fourth Block**: Configured with OSPF in Area 0.

Each block is assigned a unique network address, and variable-length subnet masking (VLSM) is applied to optimize IP address usage within each segment.

### Key Features and Configurations

1. **Routing Protocols and Redistribution**:
   - EIGRP is used within the first block, providing efficient, scalable routing.
   - OSPF is deployed in two separate areas (Area 1 and Area 0) across different blocks, enabling hierarchical structuring and efficient route management.
   - RIP is configured within the third block to simulate a simple, distance-vector-based routing environment.
   - Redistribution is implemented between different routing protocols:
     - **Router5** and **Router8** facilitate redistribution between EIGRP and OSPF.
     - **Router8** and **Router21** handle redistribution between OSPF (Area 1) and RIP.
  
2. **Dynamic IP Address Allocation**:
   - Two DHCP servers are configured to assign IP addresses dynamically within the network:
     - The main **DHCP Server** provides IP addresses to hosts in the EIGRP, OSPF Area 1, and RIP segments.
     - The **DHCP Server for VLANs** supplies IP addresses to hosts within OSPF Area 0, supporting network segmentation with VLANs.

3. **NAT Configuration**:
   - NAT is configured on the router connected to Network G, translating private IP addresses to a designated public IP, allowing external access to specific network resources.

4. **VLANs and VTP Configuration**:
   - VLANs are created to logically segment the network for different departments or functions, each identified by a color-coded scheme:
     - **VLAN 10**: Green
     - **VLAN 20**: Yellow
     - **VLAN 30**: Magenta
     - **VLAN 40**: Blue
   - The **3560 Multi-Level Switch** is configured as the VTP server, with all other switches as clients. The light blue switch does not participate in VTP, isolating it from VLAN updates.
   - Inter-VLAN communication is enabled between VLAN 20 and VLAN 40, allowing selective connectivity between these segments.

5. **Access Control and Restrictions**:
   - Access restrictions are implemented to control connectivity between specific hosts and servers:
     - **PC 0** is restricted from accessing the **TFTP Server**.
     - **PC 13** is restricted from accessing the **Data Server**.
     - Hosts on the purple-shaded switch are denied access to **Data Server 3**.
     - Hosts on the pink-shaded switch cannot communicate with hosts in **VLAN 40**.

7. **Router on a Stick Configuration**:
   - VLAN routing is configured using the router-on-a-stick technique on the **3560 Multi-Level Switch**. This allows VLAN traffic to route through a single router interface, enhancing network efficiency and reducing hardware costs.

8. **Addressing Scheme**:
   - VLSM is employed across all three blocks, efficiently utilizing IP address space and supporting the required number of hosts per subnet. An address table is maintained to document IP configurations for all network devices.

## Conclusion
This project serves as a well-rounded demonstration of advanced networking concepts, including dynamic routing protocols, NAT, DHCP, VLANs, and IP security. Through careful segmentation and controlled connectivity, the network is both secure and flexible, simulating the requirements of a scalable enterprise network. The design and configurations provide a robust framework for learning and simulating real-world networking scenarios.
