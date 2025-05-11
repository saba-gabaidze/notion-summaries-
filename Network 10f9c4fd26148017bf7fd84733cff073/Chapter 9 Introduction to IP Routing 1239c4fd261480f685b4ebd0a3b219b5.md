# Chapter 9 Introduction to
IP Routing

# router needs

- The destination address of the packet.
- Information from neighboring routers about other networks.
- The best route to each network.
- How to keep its routing information up to date.

# IP Routing Process

![image.png](Chapter%209%20Introduction%20to%20IP%20Routing%201239c4fd261480f685b4ebd0a3b219b5/image.png)

### Step 1: Host_A Checks Its Own Network

- Host_A knows its IP address is 172.16.10.2 and its subnet mask. Based on the subnet mask (let’s assume it's 255.255.255.0 for this example), Host_A determines that Host_B (172.16.20.2) is on a different network.
- Since Host_B is on a different network, Host_A needs to send the data to its default gateway (router) to reach Host_B.

### Step 2: Host_A Sends the Data to Its Default Gateway

- Host_A will send the packet to the IP address of the default gateway (in this case, 172.16.10.1, the IP address of the router interface E0) to handle the routing to the destination network.
- Host_A creates a packet that includes:
    - Source IP: 172.16.10.2 (Host_A’s IP)
    - Destination IP: 172.16.20.2 (Host_B’s IP)

### Step 3: Router Lab_A Receives the Packet on E0

- The Lab_A router receives the packet on its E0 interface (IP: 172.16.10.1).
- The router inspects the destination IP address in the packet (172.16.20.2) and checks its routing table to determine where to forward the packet.

### Step 4: Router Forwards the Packet to E1

- Lab_A determines that 172.16.20.2 belongs to the network 172.16.20.0/24, which is reachable via its E1 interface (IP: 172.16.20.1).
- The router forwards the packet through its E1 interface towards Host_B.

### Step 5: Host_B Receives the Packet

- Host_B (172.16.20.2) receives the packet. Host_B inspects the packet’s destination IP address and sees it matches its own IP.
- Host_B processes the packet and can now respond back to Host_A.

### Step 6: Host_B Sends a Response

- When Host_B responds, it follows a similar process. Host_B will send the packet to its own default gateway (172.16.20.1) to reach Host_A.

In summary, Host_A knows that Host_B is on a different network, sends the packet to its default gateway (the Lab_A router), the router forwards the packet to the correct network, and finally, Host_B receives it. The entire process hinges on routing decisions made by the router based on its routing table.

# Detailed ip routing

### Step 1: ICMP Echo Request

- **Host_A** creates an **ICMP Echo Request** packet, which contains some basic data (like the alphabet) to send to **Host_B**.

### Step 2: IP Packet Creation

- The **ICMP** payload is encapsulated in an **IP packet**, which includes:
    - Source IP (Host_A: 172.16.10.2)
    - Destination IP (Host_B: 172.16.20.2)
    - Protocol field set to ICMP (0x01 in hex)

### Step 3: Determine if the Destination is Local or Remote

- **Host_A** checks if the destination (172.16.20.2) is on the same network. It sees that it's on a different network, so it must send the packet to its **default gateway** (Lab_A router).

### Step 4: ARP Lookup or Request

- To send the packet to the **default gateway**, **Host_A** needs the MAC address of the router's Ethernet interface (E0, 172.16.10.1).
- **Host_A** checks its **ARP cache**. If the MAC address is not found, an **ARP broadcast** is sent to get the router's MAC address.

### Step 5: Frame Creation

- **Host_A** creates a **frame** that includes:
    - Destination MAC: **Router’s E0 MAC address**
    - Source MAC: **Host_A’s MAC**
    - Ether-Type field (indicating the Network Layer protocol, IP)
    - **FCS** for error-checking

### Step 6: Frame Transmission

- The frame is sent out onto the physical network (like Ethernet cables) towards the **router**.

### Step 7: Router Receives the Frame

- The **router** receives the frame, checks the **FCS** for errors, and ensures the **destination MAC** matches its own E0 MAC.
- It then removes the frame and processes the **IP packet** inside.

### Step 8: Router Routes the Packet

- The **router** checks its **routing table** and finds the destination network (172.16.20.0) is reachable via its E1 interface (172.16.20.1).
- It forwards the packet to **Host_B** by first checking its **ARP cache** for **Host_B’s MAC address**. If not found, it sends out an **ARP request**.

### Step 9: Frame for Host_B

- A new frame is created with:
    - Destination MAC: **Host_B’s MAC address**
    - Source MAC: **Router’s E1 MAC**
- The frame is sent to **Host_B**.

### Step 10: Host_B Receives the Frame

- **Host_B** receives the frame, checks the **FCS**, confirms the **MAC address**, and passes the packet up to **IP**.
- **IP** gives the packet to **ICMP**, which recognizes it as an **Echo Request** and sends back an **Echo Reply**.

### Step 11: Return Trip to Host_A

- The return trip follows the same process in reverse. **Host_B** sends the **Echo Reply** packet to **Host_A** through the **router**, encapsulated in new frames for each hop.

### Step 12: ICMP Response

- When **Host_A** receives the **Echo Reply**, it knows that **Host_B** is reachable and displays a response (like `!`) indicating success.

# Router Packet Forwarding

1. **Routing Table Lookup**:
    - When a router receives a packet for a remote network, it checks its routing table to find the best path to that network.
2. **Handling Unknown Networks**:
    - If the network isn’t listed in the routing table, the router **discards** the packet instead of broadcasting it to find the network.

### Types of Routing Protocols

1. **Dynamic Routing Protocols**:
    - These are divided into:
        - **Interior Gateway Protocols (IGPs)**: Used within a single organization’s network (autonomous system).
        - **Exterior Gateway Protocols (EGPs)**: Used to connect different organizations or networks.
2. **Example Protocols**:
    - **EGP**: Border Gateway Protocol (BGP), commonly used by ISPs and large corporations.
    
    # **IGP Categories**
    
    ### 1. **RIP (Routing Information Protocol)**
    
    - **Type**: Distance-Vector Routing Protocol.
    - **Function**: RIP helps routers share routing information with each other, determining the best path based on hop count (the number of routers a packet must pass through).
    
    ### Key Features:
    
    1. **Hop Count Limit**: The maximum number of hops allowed is 15; 16 is considered unreachable.
    2. **Periodic Updates**: Routers send updates every 30 seconds to share their routing tables.
    3. **Simplicity**: Easy to configure and understand, but not suitable for large networks due to its hop count limit.
    4. **RIP Versions**: Includes RIP version 1 (classful) and RIP version 2 (classless, supports VLSM and authentication).
    
    ---
    
    ### 2. **OSPF (Open Shortest Path First)**
    
    - **Type**: Link-State Routing Protocol.
    - **Function**: OSPF shares detailed information about the network's topology, allowing routers to calculate the best paths based on link states.
    
    ### Key Features:
    
    1. **Areas**: Supports hierarchical network design using areas to optimize routing.
    2. **Cost Metric**: Uses link cost based on bandwidth to determine the best path.
    3. **Fast Convergence**: Quickly adapts to changes in the network.
    4. **Scalability**: Suitable for large and complex networks.
    
    ---
    
    ### 3. **IS-IS (Intermediate System to Intermediate System)**
    
    - **Type**: Link-State Routing Protocol.
    - **Function**: Similar to OSPF, IS-IS finds optimal paths using link information without the need for hierarchical areas.
    
    ### Key Features:
    
    1. **Protocol Independence**: Can support multiple network layer protocols.
    2. **Flat Structure**: Lacks a hierarchical area structure, which simplifies configuration.
    3. **Fast Convergence**: Quickly adapts to changes in network topology.
    4. **Link Metrics**: Uses various metrics to calculate the best paths.
    
    ---
    
    ### 4. **EIGRP (Enhanced Interior Gateway Routing Protocol)**
    
    - **Type**: Advanced Distance-Vector Routing Protocol (also known as a hybrid protocol).
    - **Function**: EIGRP uses a combination of distance-vector and link-state principles, providing efficient and rapid convergence.
    
    ### Key Features:
    
    1. **Metric Calculation**: Uses a composite metric based on bandwidth, delay, load, and reliability.
    2. **Rapid Convergence**: Uses Diffusing Update Algorithm (DUAL) to quickly adapt to changes.
    3. **Neighbor Discovery**: Establishes relationships with neighboring routers to share information.
    4. **Support for Multiple Protocols**: Can support multiple Layer 3 protocols (IP, IPX, AppleTalk).
    
    ---
    
    ### 5. **IGRP (Interior Gateway Routing Protocol)**
    
    - **Type**: Distance-Vector Routing Protocol (predecessor to EIGRP).
    - **Function**: A Cisco proprietary protocol used to manage routing in smaller networks.
    
    ### Key Features:
    
    1. **Metric Calculation**: Uses bandwidth, delay, load, and reliability for route calculations.
    2. **Limited Use**: Mostly phased out in favor of EIGRP due to scalability issues.
    3. **Simplicity**: Easier to configure than some more complex protocols.
    
    ---
    
    ### 6. **OSPFv3**
    
    - **Type**: Link-State Routing Protocol (specific for IPv6).
    - **Function**: OSPFv3 is an updated version of OSPF designed to work with IPv6 networks.
    
    ### Key Features:
    
    1. **Support for IPv6**: Designed to handle the complexities and features of IPv6.
    2. **Similar Structure**: Retains many features of OSPF for ease of migration.
    3. **Link-Local Addresses**: Uses link-local addresses for communication between OSPF routers.
    
    ---
    
    ### Summary
    
    - **RIP**: Simple and easy, but limited to small networks. (Distance vector)!
    - **OSPF**: Scalable and efficient for large networks with hierarchical design. Link-State
    - **IS-IS**: Flexible, protocol-independent, and effective in large networks.  Link-State!
    - **EIGRP**: Combines the best of distance-vector and link-state protocols, offering rapid convergence and flexibility.
    - **IGRP**: An older protocol, mainly replaced by EIGRP. Distance vector!
    - **OSPFv3**: Tailored for IPv6, maintaining OSPF's efficient structure.

# EGP Categories

### **1) BGP**

**(Border Gateway Protocol)**

- **Definition**: BGP is an **Exterior Gateway Protocol (EGP)** used to exchange routing information between different **autonomous systems (AS)** on the Internet.
- **Type**: It’s a **path-vector protocol** that chooses the best route based on the **AS-PATH** (the list of autonomous systems the data passes through).
- **Purpose**: BGP ensures data can be routed across the Internet by selecting the best paths based on policies and attributes like path length.
- **How it Works**:
    - BGP routers (peers) exchange routing information.
    - They select the best path based on routing policies and attributes.

# Commands

## 1)  arp -a

# Note!!!!!!!!!

## N1

Just a quick note to mention that when (if) the packet is lost on the way
back to the originating host, you will typically see a request-timed-out
message because it is an unknown error. If the error occurs because of a
known issue, such as a route that is not in the routing table on the way to
the destination device, you will see a destination-unreachable message.
This should help you determine if the problem occurred on the way to the
destination or on the way back

# **Convergence**

in networking refers to the process by which all routers in a network come to agree on the best paths to all destinations. When a network change occurs (like a link going down or a new router being added), routers exchange updated information until they all have consistent and accurate routing tables.

In other words, convergence is when the network stabilizes after a change, and every router "knows" the current topology of the network. Faster convergence is critical for minimizing downtime and ensuring quick adaptation to changes in the network.