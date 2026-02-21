# HOME NETWORK PROJECT  
**Author:** Confiance (Confy-Code)

---

## 1. Project Overview

This project demonstrates the design and implementation of a small home/office network using Cisco Packet Tracer.  

It simulates a realistic network topology consisting of multiple LANs interconnected through routers. The objective of this project is to showcase how IP addressing, subnetting, and router configurations are applied in real-world networking environments.

The project includes a fully functional `.pkt` simulation file created in Cisco Packet Tracer, with no traffic yet.

---

## 2. Technologies & Tools Used

- **Cisco Packet Tracer** – Version 8.2.2  
- **IP Addressing Method** – Static IP Addressing  
- **Addressing Scheme** – Classless Inter-Domain Routing (CIDR)  
- **Subnet Mask Used** – /27 (255.255.255.224) and /30 for router-to-router  
- **Topology Type** – Extended Star Topology  
- **Microsoft Excel** – Used for subnet calculations and IP addressing table  

No automation tools or programming languages were used in this project.

---

## 3. Network Topology Description

The network follows an **extended star topology** structure.

### Devices Used
- 8 End Devices (Personal Computers)
- 4 Switches
- 3 Routers

### LAN Structure
- Each pair of two PCs connects to a switch using straight-through Ethernet cables.
- Two LANs connect to one router through separate GigabitEthernet interfaces.
- One PC is directly connected to a router interface.
- Routers are interconnected using a **Serial DCE cable** with a clock rate of **6400**.

**Note**: If the serial interface is not available on the router, a serial module must be added from the Physical tab in Packet Tracer.

<img width="1366" height="557" alt="Assignment_3_pkt_photo" src="https://github.com/user-attachments/assets/dd63ce16-0b78-4468-8a48-1739921bc8e0" />

---

## 4. IP Addressing Design

The subnetting was designed based on the following criteria:

- **Maximum Required Hosts:** 29
- **Chosen Subnet Mask:** /27
- **Total Hosts per Subnet:** 30 usable hosts
- **Block Size:** 32
- **Borrowed Bits:** 3 bits
- **Total Subnets Created:** 8 subnets

The /27 subnet mask was selected because it efficiently supports up to 30 hosts per subnet while minimizing IP address waste.

### The IP Addressing Table Includes:
- Network ID
- First Usable IP Address
- Last Usable IP Address
- Broadcast Address

The **Last Usable IP Address** of each subnet was used as the **Default Gateway**.

---

## 5. End Device Configuration

All end devices were configured manually using static IP addressing.

Each PC was assigned:

- IP Address (first two usable addresses of the subnet)
- Subnet Mask: 255.255.255.224 (/27)
- Default Gateway: Last usable IP address of the subnet

No DHCP server was used in this project.

---

## 6. Router Configuration

Routers were configured via the Command Line Interface (CLI).

### Interfaces Configured:
- GigabitEthernet interfaces (for LAN connections)
- Serial interfaces (for router-to-router communication)

### Basic Router Configuration Example:

    enable
    configure terminal
    
    interface GigabitEthernet0/0/0
    ip address 192.168.10.30 255.255.255.224
    no shutdown
    exit
    
    interface Serial0/1/0
    ip address 10.0.0.1 255.255.255.252
    clock rate 6400
    no shutdown
    exit

    exit
    write

Each router was configured similarly according to its assigned subnet.

**Note**:It is recommended to save your configurations to Non-volantile RAM(NVRAM), so that you do not lose yor work. That is why we encourage you to include the `write` command in your CLI once you are in the privileged EXEC mode(#)

---

## 7. Key Networking Concepts Demonstrated

- Classless Subnetting (CIDR)
- Efficient IP Address Allocation
- Static IP Configuration
- Router Interface Configuration
- Serial DCE/DTE Communication
- Default Gateway Implementation
- Extended Star Topology Design

---

## 8. Challenges Faced

- Ensuring correct subnet calculations and block size alignment.
- Configuring serial interfaces correctly with clock rate.
- Making sure all router interfaces were properly enabled using `no shutdown`.
- Verifying connectivity using `ping` tests across different networks.

These challenges were resolved through careful subnet planning and systematic interface verification.

---

## 9. Conclusion

This project demonstrates a practical implementation of a small-scale network using structured IP addressing and router configuration.  

It reflects foundational networking principles that are essential in real-world home and small office network deployments.

---

## 10. Integrity Statement

I confirm that this project was designed, configured, and documented independently as part of my learning process.

---

© 2026 Confiance – Confy-Code
