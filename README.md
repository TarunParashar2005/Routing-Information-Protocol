# Routing-Information-Protocol

This lab demonstrates the configuration of RIP v2 to enable dynamic routing between multiple routers. Using RIP, networks automatically exchange routing tables, allowing devices across different subnets to communicate without manual static routes.

Lab Topology
Routers: 3 (Router0, Router1, Router2)
PCs: 2 (PC0 and PC1)
Networks:
  192.168.10.0/24 (PC0 – Router0)
  192.168.20.0/24 (Router0 – Router1)
  192.168.30.0/24 (Router1 – Router2)
  PC1 connected to Router2

Steps & Procedure:-

1. Assign IP Addresses
   Configure IP addresses on all router interfaces.
   Assign IP addresses to PCs.

Example:
Router0(config)# interface g0/0
Router0(config-if)# ip address 192.168.10.1 255.255.255.0
Router0(config-if)# no shutdown

2. Enable RIP on Routers
   Activate RIP v2 on each router.
   Advertise directly connected networks.

Router0(config)# router rip
Router0(config-router)# version 2
Router0(config-router)# network 192.168.10.0
Router0(config-router)# network 192.168.20.0

3. Verify RIP Updates
   Use show ip route to check dynamic entries.
   Ensure learned networks appear with an R (RIP) code.

  4. Test Connectivity
     Ping between PC0 and PC1.
     Traceroute to verify the path across routers.

! Outcomes
  Routers dynamically share routing information.
  Full end-to-end communication is achieved without static routes.
  RIP routing table entries are visible on all routers.

! Learnings & Benefits
  Understand how distance-vector protocols like RIP work.
  Learn RIP configuration commands and verification.
  Observe dynamic routing convergence in real-time.
  Build foundational knowledge for advanced protocols like EIGRP and OSPF.
