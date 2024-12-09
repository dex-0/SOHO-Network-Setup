# SOHO Network Design and Implementation

## Objective

The goal of this project was to design and implement a secure and efficient network for a Small Office/Home Office (SOHO) environment. The network was segmented using VLANs, trunking, and inter-VLAN routing, with security controls implemented using ACLs.

---


## Network Design Details

VLAN Configuration

VLANs Used:

VLAN 10: Engineering Department

VLAN 20: Sales Department

VLAN 30: Administration Department

VLAN 99: Native VLAN for trunking

## IP Addressing and Default Gateways

VLAN 10 (Engineering): Gateway - 10.10.10.1/24

VLAN 20 (Sales): Gateway - 10.10.20.1/24

VLAN 30 (Administration): Gateway - 10.10.30.1/24

Trunking and VTP Configuration

Trunking: Configured trunk ports between switches to carry VLAN traffic.

VTP: Used VLAN Trunking Protocol (VTP) in Server-Client mode for centralized VLAN management.

VTP domain name and password were configured to ensure security and consistency in VLAN propagation.

## Inter-VLAN Routing (ROAS)

Router-on-a-Stick (ROAS):

Configured sub-interfaces on the router for each VLAN:

GigabitEthernet0/0.10 for VLAN 10 (IP: 10.10.10.1)

GigabitEthernet0/0.20 for VLAN 20 (IP: 10.10.20.1)

GigabitEthernet0/0.30 for VLAN 30 (IP: 10.10.30.1)

Assigned the appropriate encapsulation (dot1q) to each sub-interface.

Security Implementation with ACLs

## Access Control Lists (ACLs):

Configured ACLs to restrict access to the Administration VLAN (VLAN 30):

Denied traffic from VLAN 10 (Engineering) and VLAN 20 (Sales) to VLAN 30.

Allowed all other necessary traffic.

---


Conclusion

This project successfully implemented VLAN segmentation, inter-VLAN routing using ROAS, and centralized VLAN management with VTP. Security was enhanced by using ACLs to restrict unauthorized access to the administration network. The design ensures scalability, performance, and secure network access for the SOHO environment.