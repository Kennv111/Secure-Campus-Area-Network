# Lab #3: Secure Campus Area Network (CAN) Design and Implementation

This repository contains the individual design and simulation of a high-capacity, secure Campus Area Network (CAN) for Bicol University. Developed as a lab activity for **Networking 2**, this project focuses on enterprise-level scalability, site-to-site security, and advanced routing protocols.

## Project Overview
The project simulates a geographically dispersed network connecting two campuses (Main and Branch) located 100 miles apart. It is designed to support an initial user base of 30,000, with a scalable architecture prepared to accommodate a 100% growth in user density by 2025.

The infrastructure supports four core faculties across both locations:
* Health and Sciences
* Business
* Engineering/Computing
* Art/Design

## Network Architecture
The topology follows a hierarchical design utilizing Core, Distribution, and Access layers to manage traffic efficiently across the campus.



* **Main Campus (HQ):** Serves as the central administrative hub and hosts the **Server Farm (DMZ)**.
* **Branch Campus:** A fully functional remote site providing autonomous services while maintaining secure connectivity to HQ via a simulated WAN link.
* **Central IT Department:** Located at HQ, providing centralized management for both campuses.

## Technical Implementation (Networking 2 Concepts)

### 1. Advanced Routing & Redundancy
* **OSPF (Open Shortest Path First):** Multi-area OSPF implementation to advertise routes dynamically across all routers and Multilayer Switches (L3).
* **Inter-VLAN Routing:** Configured on Multilayer Switches to facilitate high-speed communication between departmental VLANs.
* **EtherChannel:** Implemented for link aggregation between switches to provide increased bandwidth and hardware redundancy.
* **Static/Default Routing:** Configured for granular control over traffic exit points using next-hop verification for traffic not matching routing table entries.

### 2. Network Security & Tunneling
* **Site-to-Site IPSec VPN:** Established a secure, encrypted tunnel between the HQ and Branch routers to ensure data privacy over the simulated WAN.
* **Extended ACLs:** Utilized to define "interesting traffic" for the VPN tunnel and to enforce departmental traffic policies.
* **NAT/PAT:** Implemented Port Address Translation on the outbound interfaces to optimize public IPv4 address usage for internal departments.
* **Port Security:** Applied to Access Layer switches at the server site using **Sticky MAC** addresses and a violation mode of **Shutdown** to prevent unauthorized hardware access.

### 3. Management & Services
* **Dynamic Addressing:** Centralized DHCP servers provide automated IP allocation for all end-user devices.
* **Secure Management:** SSH (Secure Shell) is enabled on all infrastructure devices (Routers and L3 Switches) for encrypted remote administration.

## How to Run the Simulation
1.  **Requirement:** Use **Cisco Packet Tracer** (v8.0 or higher).
2.  **Download:** Save the `LAB#3.1.pkt` file from this repository.
3.  **Launch:** Open the file and allow **60 seconds** for the network to converge (wait for all link lights to turn green).
4.  **Verification:** * Verify the **IPSec VPN tunnel** status between routers using CLI commands.
    * Test **Inter-VLAN connectivity** by pinging between different departments (e.g., Business to Engineering).
    * Confirm **DHCP success** on end-user PCs across both campuses.

## Course Information
* **Course:** Networking 2
* **Institution:** Bicol University, BS Information Technology
* **Project Type:** Lab Project

--
*Developed by Kenneth B. Borjal*
