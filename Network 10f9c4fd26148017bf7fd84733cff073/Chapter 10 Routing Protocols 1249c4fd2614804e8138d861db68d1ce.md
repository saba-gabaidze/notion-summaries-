# Chapter 10 Routing Protocols

# Routing Protocol Basics

- **Routing Overview**:
    - The text introduces a complete routing tree to illustrate how routing works.
- **Types of Routing Protocols**:
    - **Interior Gateway Protocols (IGPs)**:
        - Used for exchanging routing information within the same autonomous system (AS).
        - An AS consists of networks managed under a single administrative domain, meaning all routers share the same routing table information.
    - **Exterior Gateway Protocols (EGPs)**:
        - Used for communication between multiple ASs.
        - An example is the Border Gateway Protocol (BGP), which is not the main focus of the book but will be briefly mentioned.
- **Administrative Distance**:
    - This is an important concept related to routing protocols, indicating the trustworthiness of different routes. Lower values represent more reliable routes.

# AD

**Administrative Distance (AD)** is used to rate the trustworthiness of routing information received by a router from its neighboring routers.

**AD Range:** An AD is an integer from **0 to 255**, where **0** is the most trusted route and **255** means "No traffic is allowed via this route."

**Route Selection:** When a router receives two updates for the same remote network, it first checks the **AD**. The route with the **lower AD** is placed in the routing table. If both routes have the same AD, the router uses **routing-protocol metrics** (like hop count or bandwidth) to determine the best path. If both routes have the same AD and metrics, the router performs **load balancing**, sending packets down each link to test for the best one.

**Enabling All Routing Protocols:** Some administrators mistakenly enable all routing protocols on routers, causing slow network performance. For example, if **Enhanced Interior Gateway Routing Protocol (EIGRP)** is enabled along with other protocols like **RIP**, only EIGRP will appear in the routing table due to its lower default AD, while others run in the background, consuming bandwidth.

**Improving Performance:** Disabling unnecessary routing protocols can significantly improve network performance. In an all-Cisco router network, keeping only EIGRP enabled can increase performance by up to **30%**. Upgrading core routers can further improve efficiency and response times by **50%**.

**Default Administrative Distances:**

- **Connected interface:** 0
- **Static route:** 1
- **EIGRP:** 90
- **IGRP:** 100
- **OSPF:** 110
- **RIP:** 120
- **External EIGRP:** 170
- **Unknown:** 255 (this route will never be used)

**Key Points:**

- If a network is directly connected, the router uses the connected interface.
- A **static route** is preferred over dynamically learned routes due to its lower AD (default is 1).
- If you have a static route, a RIP-advertised route, and an IGRP-advertised route for the same network, the router will always use the **static route** by default unless you change its AD.

# Classes of Routing Protocols

**Distance Vector**:

Distance-vector protocols determine the best path by evaluating distance (measured in hops). Each router hop counts as one, and the route with the fewest hops is considered the best. Examples: RIP, RIPv2, and IGRP. These protocols share their entire routing table with directly connected neighbors.

**Link State**:

Link-state (shortest-path-first) protocols create three tables:

1. Directly attached neighbors
2. Entire network topology
3. Actual routing table.Link-state routers have more detailed knowledge of the network than distance-vector protocols. Examples: OSPF, IS-IS. These protocols send updates about their own links to all routers in the network.

**Hybrid**:

A hybrid protocol combines features from both distance-vector and link-state. The only hybrid protocol is **EIGRP**, which is Cisco proprietary, meaning it only works on Cisco equipment.

Each routing protocol works differently, and there is no single solution for every scenario. Understanding how each protocol functions allows for better decision-making based on specific business needs.

# **Distance-Vector Routing Protocols**

The **distance-vector routing algorithm** passes complete routing-table contents to neighboring routers. Each router then updates its routing table based on the information received, a process often called **"routing by rumor"** because the routers trust the information from their neighbors without verifying it.

If multiple links to the same network exist, the router checks the **Administrative Distance (AD)** first. If the ADs are the same, the protocol uses other **metrics** to choose the best path.

Distance-vector protocols primarily use **hop count** to determine the best path. If two paths have the same hop count, the router will perform **round-robin load balancing** across the available paths.

When a **distance-vector protocol** starts, each router initially knows only its **directly connected networks**. The routing protocol then updates the routers' tables with the complete network information gathered from neighbors.

Once all routers have shared information, they are said to be **converged**, meaning their routing tables are complete and consistent. During this time, **data transmission may pause** until the routers have fully converged. A drawback of protocols like RIP is their **slow convergence time**.

After convergence, each router’s routing table includes:

- The **remote network number**.
- The **interface** used to send packets to reach that network.
- The **hop count** (or metric) to the network.
- 

**Convergence time** is the time it takes for routing protocols to update their forwarding tables after a change in the network.

**Key Points**:

- Routers only know **directly connected networks** at first.
- Distance-vector protocols use **hop count** as the main metric.
- **Routing by rumor** means routers trust the information from neighbors without verification.
- **Convergence** occurs when all routers have consistent and complete routing tables.
- **Round-robin load balancing** is used when multiple paths with the same hop count exist.

# **RIP (120)**

**Routing Information Protocol** 

 is a distance-vector routing protocol that sends the complete routing table to all active interfaces every 30 seconds. It uses **hop count** to determine the best path to a network, with a maximum hop count of **15**—anything beyond that (16 or more) is considered **unreachable**.

While **RIP** works well for **small networks**, it is **inefficient** in larger networks, especially those with **slow WAN links** or many routers.

- **RIP version 1** uses **classful routing**, meaning all devices must use the same subnet mask because it does not send updates with subnet mask information.
- **RIP version 2** supports **classless routing** with **prefix routing**, allowing it to send subnet mask information with route updates.

# RIPv2

is an improvement over RIPv1, but both are distance-vector protocols that share similar features. Here are the key points:

- **Both RIPv1 and RIPv2** send their complete routing tables periodically, use holddown timers, and follow split horizon rules.
- **Classful addressing:** RIPv1 and RIPv2 are configured this way, but RIPv2 is **classless** because it sends subnet information with route updates.
- **Administrative Distance (AD):** Both have an AD of **120**.
- **RIPv2's main advantages:**
    - **Uses Multicast (224.0.0.9)** instead of broadcast.
    - **Supports VLSM** (Variable Length Subnet Mask) and discontiguous networks.
    - **Allows for MD5 authentication**, unlike RIPv1, which has no authentication option.

Although **RIP** is an open standard and compatible with various router brands, it's generally not recommended for modern networks. **RIPv2** is more scalable than **RIPv1** but still has limitations like a **maximum hop count of 15**.

# **VLSM and Discontiguous Networks**

VLSM is **classless**, meaning the routing protocol sends subnet-mask info with route updates, helping to **save address space**. Without VLSM, all interfaces and devices (PCs, printers, routers) would have to use the **same subnet mask**, which is inefficient.

With VLSM, different **subnet masks** can be used on different router interfaces, which optimizes the allocation of IP addresses. In **classful routing** (like RIP or IGRP), all subnets have the same size, wasting space, especially on **WAN links** that need only **two hosts**.

**Classful routing example:**

- Network: **192.168.10.0**
- Subnet mask: **255.255.255.240 (/28)**
- This results in subnets like **192.168.10.0, .16, .32, .48, .64**, but each can handle **14 hosts**, even if not needed (e.g., a WAN link that only needs 2 hosts gets 14).

To solve this waste, we can use **VLSM** to assign subnet masks based on the actual number of required hosts for each interface.

**Classless design with VLSM:**

- Assigning a **/30** mask to WAN links gives exactly **2 hosts**.
- Assigning **/27**, **/28**, and **/29** to different LANs provides **30, 14, and 6 hosts** per LAN, respectively, saving address space.

For **VLSM** to work, a routing protocol like **RIPv2, EIGRP, or OSPF** must be used, as these protocols send subnet-mask information with updates. **RIPv1 and IGRP** do not support VLSM and are considered **classful**.

VLSM doesn't improve performance but **saves IP addresses**.

**Discontiguous Networks:**
A **discontiguous network** consists of two or more subnetworks of a classful network connected by different classful networks. For example, **172.16.10.0** and **172.16.20.0** are connected through a **10.3.1.0** network. In such cases, routers may mistakenly think they own the entire **172.16.0.0** classful network.

Discontiguous networks **do not work** with **RIPv1 or IGRP** and require proper configuration on **RIPv2 or EIGRP**. However, they **work by default** on **OSPF** because it does not auto-summarize like RIPv2 and EIGRP.

# EIGRP (90)

 is a **classless, enhanced distance-vector protocol**, designed to improve upon IGRP, which is now outdated and unsupported by Cisco. It uses the **autonomous system** concept to describe a group of routers sharing routing information. Unlike IGRP, EIGRP includes the **subnet mask** in its route updates, allowing the use of **VLSMs** in network design.

EIGRP is classified as a **hybrid routing protocol**, exhibiting features of both distance-vector and link-state protocols. It sends **traditional distance-vector updates** with network information and costs, while also synchronizing routing tables between neighbors at startup and sending updates only when topology changes occur. This feature makes EIGRP suitable for **large networks**.

Key features of EIGRP include:

- **Support for IP and IPv6** via protocol-dependent modules.
- Considered **classless** like RIPv2 and OSPF.
- **Support for VLSM** and **Classless Inter-Domain Routing (CIDR)**.
- Capable of **summarizing** and handling **discontiguous networks**.
- Efficient **neighbor discovery**.
- Communication through **Reliable Transport Protocol (RTP)**.
- **Best path selection** using the **Diffusing Update Algorithm (DUAL)**.

EIGRP is easy to configure like a distance-vector protocol but maintains more information through additional tables:

- **Neighbor Table**: Records information about adjacent neighbors, including their addresses and interfaces. It uses sequence numbers to match acknowledgments with update packets.
- **Topology Table**: Populated from the neighbor table, it holds all destinations advertised by neighboring routers. It contains a list of neighbors for each destination along with their advertised metrics.
- **Routing Table**: Contains the best route to a remote network, known as the **successor** route, used for forwarding traffic. The best route is backed up by **feasible successors**, which are alternative routes with reported distances less than the feasible distance.

**Feasible successors** are stored in the topology table and provide backup routes, ensuring **instant convergence** and efficient updates. This design contributes to EIGRP's speed, scalability, and **fault tolerance**.

# BGP

 (Border Gateway Protocol) is the **core routing protocol of the Internet** and is essential for managing **multiple connections to different ISPs**. Its design allows it to handle the **growing dependence on the Internet** and the **redundant connections** that many organizations establish.

BGP is more effective than other routing protocols like **OSPF** when dealing with the **complexity of multiple connections**. It serves as an alternative to **default routes** for controlling **path selection**. With the Internet's continued growth, BGP supports **classless routing** and **summarization**, which help to keep routing tables **smaller and more efficient** at the ISP core.

BGP operates as an **Exterior Gateway Protocol (EGP)**, connecting different **Autonomous Systems (AS)**, while Internal Gateway Protocols (IGPs) like **RIP, IGRP, EIGRP, and OSPF** function within a single AS. An **autonomous system** is a collection of networks managed under a common administrative domain.

BGP is particularly useful for **joining large OSPF networks** together when OSPF alone can't handle the load. It is also beneficial for **multi-homing a network**, providing better redundancy to multiple access points from a single ISP or connecting to multiple ISPs.

BGP routers exchange **path vectors** that provide detailed information on the **BGP AS numbers** and the **AS-Path**, indicating the hop-by-hop path to reach a specific destination network. Unlike IGPs, which simply indicate how to reach a specific network, BGP gives a **comprehensive view** of the route to an AS, including:

- **Network prefixes** within the AS
- **Next-hop attribute** (the IP address needed to reach the next AS)
- **Origin code attribute** (the history of how networks were introduced into BGP)

These features make BGP essential for constructing **loop-free autonomous systems**, identifying **routing policies**, and enabling the creation of **restrictions** on routing behavior based on the AS path.

# **Link-state**

 **protocols** are a classless category of routing protocols used in packet-switched networks. Examples include **OSPF** and **IS-IS**

.

To be classless, subnet-mask information must be included in routing updates, allowing neighbor routers to understand the cost of advertised network routes.

**Key differences** between link-state and distance-vector protocols include:

- **Information Maintained**: Link-state protocols maintain more comprehensive data about the internetwork compared to distance-vector protocols, which only keep a basic routing table of destination routes.
- **Neighbor Table**: Link-state protocols have a **neighbor table** maintained through **hello packets** exchanged among routers. This table contains routers that can share routing data.
- **Topology Table**: They also maintain a **topology table**, built using **Link State Advertisements (LSAs)**. This table provides a complete map of the entire internetwork, listing every destination network and reachable neighbors.
- 

After all data is shared, routers run the **Shortest Path First (SPF)** algorithm to determine the best paths to destination networks based on the information in the topology table

# **(OSPF)  110**

**Open Shortest Path First** 

 is an **open standard routing protocol** used by various network vendors, including Cisco. It utilizes the **Dijkstra algorithm** to construct a shortest-path tree and populate the routing table with the best paths. OSPF converges quickly, supports multiple equal-cost routes to the same destination, and maintains separate databases and routing tables for **IP and IPv6**.

**Key Features of OSPF:**

- Consists of **areas and autonomous systems**
- Minimizes **routing update traffic**
- Allows **scalability**
- Supports **VLSM/CIDR**
- Has **unlimited hop count**
- Supports **multi-vendor deployment** (open standard)

**Comparison of OSPF with RIPv2 and RIPv1:**

| Characteristic | OSPF | RIPv2 | RIPv1 |
| --- | --- | --- | --- |
| Type of protocol | **Link state** | **Distance vector** | **Distance vector** |
| Classless support | **Yes** | **Yes** | **No** |
| VLSM support | **Yes** | **Yes** | **No** |
| Auto-summarization | **No** | **Yes** | **Yes** |
| Manual summarization | **Yes** | **No** | **No** |
| Discontiguous support | **Yes** | **Yes** | **No** |
| Route propagation | **Multicast on change** | **Periodic multicast** | **Periodic broadcast** |
| Path metric | **Bandwidth** | **Hops** | **Hops** |
| Hop-count limit | **None** | **15** | **15** |
| Convergence | **Fast** | **Slow** | **Slow** |
| Peer authentication | **Yes** | **Yes** | **No** |
| Hierarchical network | **Yes** (using areas) | **No** (flat only) | **No** (flat only) |
| Updates | **Event triggered** | **Route table updates** | **Route table updates** |
| Route computation | **Dijkstra** | **Bellman-Ford** | **Bellman-Ford** |

**Benefits of Hierarchical OSPF Design:**

- Decreases **routing overhead**
- Speeds up **convergence**
- Confines network instability to **single areas**

In a hierarchical OSPF design, the backbone area is referred to as **Area 0**. All other areas must connect to this backbone area. **Area Border Routers (ABRs)** connect different areas to Area 0, with at least one interface in Area 0. OSPF runs within an **autonomous system** (AS) but can also connect multiple ASs using **Autonomous System Border Routers (ASBRs)**. Typically, **BGP** is used to connect ASs in modern networks.

Creating additional areas helps minimize route updates and limit problem propagation throughout the network.

# **IS-IS Overview**

IS-IS (Intermediate System to Intermediate System) is an **IGP** (Interior Gateway Protocol) used within an administrative domain, not for routing between ASs, which is the role of an EGP like BGP.

**Link-State Routing**

IS-IS is a **link-state routing protocol** that floods topology information throughout the network, allowing each router to build its own view of the network's topology. It forwards packets based on the best path to the destination.

**IS-IS Network Structure**

- **L1**: Level 1 intermediate systems route within an area. They route toward a Level 2 system if the destination is outside their area.
- **L2**: Level 2 intermediate systems route between areas and toward other ASs.
- 

**Connectionless Network Service (CLNS)**

IS-IS uses **CLNS** for connectionless delivery of data packets, unlike OSPF, which uses IP. This allows IS-IS to easily send information about multiple routed protocols (e.g., IP and IPv6) without maintaining separate databases for each, making it more efficient for large networks.

**Features**

IS-IS supports **VLSM** (Variable Length Subnet Masking) and converges quickly, similar to OSPF and EIGRP. These features enhance its scalability for large-scale networks.

**ISP Preference**

Although not as common as OSPF, IS-IS is preferred by **ISPs** due to its ability to run IP and IPv6 without separate databases, improving efficiency in very large networks.

# **IPv6 Routing Protocols**

Many routing protocols have been upgraded for IPv6 networks, and most functions and configurations remain similar to those in IPv4. Since IPv6 eliminates broadcasts, protocols that rely entirely on broadcast traffic are no longer used, which helps improve bandwidth and performance.

**Key Protocols for IPv6:**

- **RIPng (Routing Information Protocol next generation):** This protocol continues to be used for smaller networks, similar to its function in IPv4.
- **EIGRPv6 (Enhanced Interior Gateway Routing Protocol for IPv6):** EIGRP was already designed with protocol-dependent modules, making it easy to add support for IPv6.
- **OSPFv3 (Open Shortest Path First version 3):** OSPF for IPv4 was version 2, and its upgrade for IPv6 is designated as version 3.

These protocols ensure effective routing in IPv6 networks, maintaining important functions from their IPv4 counterparts while adapting to the new standards.

# **RIPng**

 is a distance-vector routing protocol similar to RIPv2, with the following key features:

- **Max hop count**: 15
- **Loop avoidance mechanisms**: Split horizon, poison reverse, and others
- **Transport protocol**: Uses **UDP port 521**
- **Multicast updates**: Uses **FF02::9** as the multicast address for IPv6 (compared to **224.0.0.9** in RIPv2 for IPv4)

**Key differences**:

- RIPng uses **link-local addresses** for next-hop addresses instead of global addresses, which helps maintain local network communication.

Overall, RIPng operates similarly to RIPv2, adapted for IPv6.

# !!!!!!!!!!

**EIGRPv6**

- EIGRPv6 functions similarly to its IPv4 predecessor.
- It is an **advanced distance-vector protocol** with some **link-state features**.
- The **neighbor-discovery process** uses hello packets.
- It provides **reliable communication** with a transport protocol, ensuring **loop-free fast convergence** using **DUAL**.
- Hello packets and updates are sent via **multicast transmission**.
- The multicast address for EIGRPv6 is **FF02::A** (compared to IPv4’s **224.0.0.10**).

**OSPFv3**

- OSPFv3 retains similarities with its IPv4 version.
- It is a **link-state routing protocol** that divides an internetwork into **areas**, creating a hierarchy.
- Adjacencies now use **link-local addresses**.
- OSPFv3 also uses multicast traffic for updates and acknowledgments, with addresses **FF02::5** for OSPF routers and **FF02::6** for OSPF-designated routers (replacing **224.0.0.5** and **224.0.0.6** from OSPFv2).