
README: SCO300 Subnetting & Network Design
Project Overview
This repository contains a Cisco Packet Tracer simulation and design documentation for a multi-branch enterprise network. The project demonstrates the implementation of Variable Length Subnet Masking (VLSM) to efficiently allocate IP addresses across a Headquarters (HQ) and two branch offices, minimizing address waste on point-to-point WAN links.

Network Architecture
The design connects three primary locations through a star-and-mesh topology:


Headquarters (HQ): Serving the largest LAN.


Branch 1: Supporting two separate LAN segments.


Branch 2: Supporting two separate LAN segments.


WAN Links: Three point-to-point serial connections linking HQ to the branches.

Requirements Analysis

Total Subnets Required: 8.


Max Hosts per Subnet: 30 (HQ LAN).


Total IP Addresses Needed: 96.

IP Addressing Scheme
The project utilizes the 192.168.1.0/24 address space. To optimize efficiency, VLSM is applied as follows:

Subnet Allocation Table
Subnet	Network Address	Subnet Mask	Usable Host Range
HQ LAN	192.168.1.0/27	255.255.255.224	
192.168.1.1 - .30 

BRANCH1 LAN 1	192.168.1.32/27	255.255.255.224	
192.168.1.33 - .62 

BRANCH1 LAN 2	192.168.1.64/27	255.255.255.224	
192.168.1.65 - .94 

BRANCH2 LAN 1	192.168.1.96/27	255.255.255.224	
192.168.1.97 - .126 

BRANCH2 LAN 2	192.168.1.128/27	255.255.255.224	
192.168.1.129 - .158 

WAN HQ to BR1	192.168.1.160/30	255.255.255.252	
192.168.1.161 - .162 

WAN HQ to BR2	192.168.1.164/30	255.255.255.252	
192.168.1.165 - .166 

WAN HQ to BR3	192.168.1.168/30	255.255.255.252	
192.168.1.169 - .170 

Implementation Details

Routing Protocols: The design is compatible with classless protocols such as RIPv2, OSPF, or EIGRP to support the VLSM prefixes.


Hardware: 2911 Routers and 2960-24TT Switches.


Verification: Successful end-to-end connectivity has been verified via ICMP ping tests between all LANs and WAN interfaces.

Repository Contents

SCO300_Assignment.pkt: The Packet Tracer source file.


Subnet_Design.pdf: Detailed addressing design and requirements analysis.


Screenshots/: CLI output for show ip interface brief and show ip route for all routers.

