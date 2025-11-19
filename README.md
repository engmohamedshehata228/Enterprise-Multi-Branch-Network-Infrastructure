Overview
This project demonstrates a real‑world enterprise network deployed on Cisco Packet Tracer. The design includes a Headquarter and two remote branches connected via OSPF (multi‑area), 8 departmental VLANs, wireless coverage per floor using wireless switches, centralized DHCP on the core L3 switch, strict access control using extended ACLs, port security, and LACP EtherChannel between L2 and L3 switches.

Topology & VLANs
Branches: Headquarter + 2 Remote Sites (each branch in a different OSPF area; Area 0 backbone)
VLANs (8): Customer Service, Operations, Marketing, Sales, Accounting, HR, IT, Management
Inter‑VLAN routing: Layer‑3 Core Switch (SVIs configured per VLAN)
Wireless & Access
Each floor is equipped with two wireless switches (access points aggregation) connected to the access/distribution switches. Wireless switches map clients to the correct VLANs so users obtain the same access rights as wired devices.

Wireless switches per floor: 2
SSID & VLAN mapping: SSIDs assigned to department VLANs
Routing & Services
Routing protocol: OSPF multi‑area — each branch on its own area, Area 0 backbone.
DHCP: Centralized on the L3 core switch (DHCP pools for each VLAN).
No NAT/PAT: The lab does not implement NAT or PAT.
Security
ACLs
Extended ACLs were configured to enforce strict access control:

IT department: full network privileges and administrative SSH access to all devices.
Branch Managers + IT: HTTP/HTTPS access to the internet (e.g., Google).
FTP & TFTP: allowed only for IT.
Final rule: permit ip any any for necessary general traffic.
Port Security
Port Security configured on access ports to limit MAC addresses per port and prevent unauthorized devices or MAC spoofing. Violations set to restrict or shutdown the port based on lab policy.

Performance & Redundancy
EtherChannel (LACP) implemented between Layer‑2 and Layer‑3 switches to provide higher bandwidth and redundancy.
Hierarchical design (Core / Distribution / Access) for scalability and fault isolation.
