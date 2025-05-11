# Chapter 11 Switching and Virtual LANs (VLANs)

# Switching Services

**Directly connected interfaces** refer to network interfaces on routers or switches that are physically linked to a device or another network through cables or wireless connections. These interfaces appear in the device's routing table because they are directly reachable without needing an intermediary device.

**Layer 2 switches** and **bridges** are similar in purpose: both break up **collision domains**. However, switches use **application-specific integrated circuits (ASICs)** for faster processing compared to bridges, which rely on software to manage their filter tables.

**Advantages of Layer 2 switches over routers:**

- They do not analyze **Network-layer** header information, which saves time.
- They only read the **hardware addresses** in the frame to decide whether to forward, flood, or drop it.

**Switches vs. Hubs:**

- Switches create **private, dedicated collision domains** and provide **independent bandwidth** on each port.
- Unlike hubs, where bandwidth is shared, each host connected to a switch can have its own dedicated bandwidth (e.g., **10Mbps**).

**Benefits of Layer 2 switching:**

- **Hardware-based bridging** (using ASICs).
- **Wire speed** operation for fast data transfer.
- **Low latency**, improving communication efficiency.
- **Low cost** compared to other solutions.

**Efficiency of Layer 2 switching:**

- No modification to the data packet occurs during switching, which makes the process faster and less error-prone than routing.
- Using Layer 2 switching allows for better **workgroup connectivity** and **network segmentation**, creating a flatter network design with more segments.

**Increased bandwidth**: Each connection to the switch functions as its own collision domain, allowing multiple devices to connect to each interface efficiently.

# Bridging vs LAN Switching

- **Bridges are software-based; switches are hardware-based, using ASIC chips for filtering decisions.**
- **A switch can be considered a multiport bridge.**
- **Only one spanning-tree instance can exist per bridge, while switches can support multiple spanning-tree instances.**
- **Switches generally have more ports than bridges.**
- **Both bridges and switches forward Layer 2 broadcasts.**
- **Bridges and switches learn MAC addresses by examining the source address of each received frame.**
- **Both make forwarding decisions based on Layer 2 addresses.**

# **Three Switch Functions at Layer 2**

Layer 2 switching has three main functions:

- **Address learning**
- **Forward/filter decisions**
- **Loop avoidance**

**Address Learning**

Layer 2 switches and bridges learn addresses by remembering the source hardware address of each frame they receive. This information is stored in a MAC database known as a forward/filter table. When a switch is powered on, this table is empty.

When a device transmits, the switch adds the frame’s source address to the MAC forward/filter table, allowing it to track where devices are located. If the destination address is not in the table, the switch floods the frame out of all ports except the source port. When the destination device responds, the switch updates the MAC database with the new address. This process enables point-to-point connections between devices, allowing for more efficient communication compared to hubs, which send frames to all ports.

If Host A sends a frame to Host B, the switch will:

1. Add Host A's MAC address to the table.
2. Flood the frame out to all ports since Host B's address is not yet in the table.
3. When Host B responds, the switch updates the table with Host B's MAC address.

The switch will eventually remove inactive entries from the table to keep it current.

**Forward/Filter Decisions**

When a frame arrives, the switch checks the destination hardware address against its MAC database:

- If the address is known, the frame is forwarded only to the specific exit interface.
- If the address is not known, the frame is flooded out of all active ports except the source port.

Broadcasts sent by a host will be flooded across the network, keeping in mind that switches create smaller collision domains but maintain one large broadcast domain by default.

**Loop Avoidance**

Redundant links between switches help prevent network failures but can also cause issues like broadcast storms and frame duplication, leading to network loops. Problems include:

- Endless flooding of broadcasts, causing a broadcast storm.
- Receiving multiple copies of the same frame from different segments, causing confusion.
- MAC address tables being constantly updated, resulting in failures to forward frames (known as thrashing the MAC table).

To address these issues, the **Spanning Tree Protocol (STP)** is implemented. STP helps prevent loops and other problems associated with redundant links by ensuring only one active path exists between switches at any given time, maintaining network stability.

# **(STP)**

**Spanning Tree Protocol** 

STP was originally developed by Digital Equipment Corporation (DEC) before being purchased by Compaq. The IEEE later created a version called **802.1D**, which is commonly used, but it is not compatible with DEC's version. There is also a newer standard, **802.1w**, which is faster but not enabled by default on switches.

The main function of STP is to **prevent network loops** in Layer 2 networks (bridges or switches). It does this by:

- Monitoring the network to identify all links.
- Shutting down any redundant links to avoid loops.

STP uses the **spanning-tree algorithm (STA)** to create a topology database and eliminate redundant links. With STP enabled, frames are only forwarded on the selected links determined by STP. Switches send out **Bridge Protocol Data Units (BPDUs)** through all ports to discover all connections between switches.

STP is essential in networks with a redundant topology to avoid issues like **broadcast storms** and **multiple frame copies**. Without a Layer 2 mechanism like STP, the network could still function but would operate extremely slowly due to looping problems, making it difficult to diagnose and resolve.

# **Spanning-Tree Port States**

Ports on a bridge or switch running STP can be in five different states:

- **Blocking**: The port won’t forward frames; it only listens to BPDUs and drops all other frames. This state prevents looped paths. All ports are in blocking state by default when the switch powers up.
- **Listening**: The port listens to BPDUs to avoid network loops before forwarding data frames. It prepares to forward data frames but does not populate the MAC address table.
- **Learning**: The port listens to BPDUs and learns the paths in the network. It populates the MAC address table but does not forward data frames. The forward delay is the time taken to transition from listening to learning mode, typically set to 15 seconds.
- **Forwarding**: The port sends and receives all data frames. If still a designated or root port after the learning state, it enters forwarding mode.
- **Disabled**: The port does not participate in frame forwarding or STP and is virtually nonoperational.

Switches populate the MAC address table only in learning and forwarding modes. Ports usually stay in either blocking or forwarding states. A forwarding port has the best cost to the root bridge. During network topology changes, ports may enter listening and learning states.

Blocking ports prevent network loops. Once a switch determines the best path to the root bridge, all other redundant ports enter blocking mode. Blocked ports can receive BPDUs but do not send frames.

If a blocked port becomes the designated or root port due to a topology change, it enters listening mode to check BPDUs and ensure no loops occur before going back to forwarding mode.

# **STP Convergence**

Convergence occurs when all ports on bridges and switches transition to either forwarding or blocking modes. During this phase, no data is forwarded until the convergence is complete, meaning all host data stops transmitting. To ensure minimal disruption, it's crucial to design the network well for quick STP convergence.

**Key Points:**

- **STP Root:** Create a core switch as the STP root for faster convergence.
- **Bridge Priority:** Assign lower bridge priority values (e.g., 4096 for the root and higher for others) to determine the STP root.
- **Convergence Time:** Typically takes **50 seconds** to transition from blocking to forwarding mode.
- **Default Timers:** It's generally not recommended to change the default STP timers, but they can be adjusted if necessary.
- **Hierarchical Design:** A well-designed hierarchical switch network helps achieve efficient STP convergence.
- **Timeout Issues:** Slow convergence can cause timeout problems on servers or hosts, especially during reboots.
- **Port Configuration:** Consider disabling spanning tree on individual ports to address timeout issues.

# VLAN

- **Switches break up collision domains, while routers break up broadcast domains.**

- **A Virtual Local Area Network (VLAN)** is a logical grouping of network users and resources on a switch, creating smaller broadcast domains within a Layer 2 switched network by assigning different ports to different subnets.
- **VLANs are treated like their own subnets**, meaning broadcast frames are only sent between ports within the same VLAN.
- **Hosts in different VLANs cannot communicate directly**. A router or Layer 3 device is needed for inter-VLAN communication.
- **Flat network design**, characterized by switches, leads to all broadcast packets being seen by every device on the network, increasing unnecessary traffic.
- **Each switch port creates an individual collision domain**, allowing larger networks to be built without Ethernet's distance limitations.
- **VLANs improve security** by limiting broadcast traffic and controlling which devices can communicate. In a traditional hub setup, any device can see all broadcasts, creating security vulnerabilities.
- **Each VLAN requires its own subnet number**. If using IPv6, each VLAN must have its own IPv6 network number as well.
- **VLAN 1 is the default administrative VLAN** for switches, and all ports are members of VLAN 1 until changed. It is recommended to use VLAN 1 only for administrative purposes.
- **To enable communication between different VLANs**, a router or Layer 3 device is necessary, similar to connecting different physical networks.

# VLAN Memberships

VLANs are typically created by a system administrator who assigns switch ports to each VLAN, known as **static VLANs**. Alternatively, if you store all host devices' hardware addresses in a database, switches can assign VLANs **dynamically** whenever a host is plugged in. This type of VLAN is referred to as a **dynamic VLAN**.

Key Points:

- **Static VLANs**: Admin assigns switch ports to VLANs manually.
- **Dynamic VLANs**: VLANs are assigned automatically based on the hardware addresses stored in a database.

## **Dynamic VLANs**

 automatically assign a host’s VLAN based on criteria like hardware (MAC) addresses, protocols, or applications.

**Example**: When a new host connects to an unassigned switch port, a centralized VLAN management application can look up its MAC address and automatically assign it to the correct VLAN.

**Benefits**: This simplifies management and configuration. If a user moves, the switch automatically assigns them to the correct VLAN without manual reconfiguration.

**Setup**: Initial setup requires significant work to create the MAC address database. However, it can be worthwhile for easier future management.

**VLAN Management Policy Server (VMPS)**: This service helps set up a database that maps MAC addresses to VLANs for dynamic addressing.

# Identifying VLANs!!!

- **Switch ports are Layer 2 interfaces associated with a physical port.**
- **An access port can belong to only one VLAN.**
- **A trunk port can belong to all VLANs.**
- **You can configure a port as either an access or trunk port manually.**
- **Dynamic Trunking Protocol (DTP) can negotiate the switch port mode on a per-port basis.**
- **DTP operates by negotiating with the port on the other end of the link.**
- **Switches must keep track of different frame types and their associated hardware addresses.**
- **Frames are handled differently based on the type of link they traverse.**
- **There are two types of links in a switched environment: access ports and trunk ports.**

# Access Ports

**Access Ports**

An access port belongs to only one VLAN and carries traffic in its native format without VLAN tagging. When an access port receives a tagged packet (like IEEE 802.1Q), it drops the packet because it doesn’t process VLAN tags. Access ports assume that any incoming traffic belongs to the configured VLAN.

**VLAN Membership**

Devices connected to access ports are unaware of VLAN membership and think they are part of the same broadcast domain. Access-link devices cannot communicate with devices outside their VLAN unless packets are routed.

**Frame Forwarding**

Switches remove VLAN information from frames before forwarding them to access-link devices. A switch port can be configured as either an access port or a trunk port, but not both.

**Connectivity Issues**

If users cannot access server resources when plugged into an access port, it may be due to the port being in the wrong VLAN or because Spanning Tree Protocol (STP) has shut down the port to prevent a loop.

# **Trunk Ports**

- The term **trunk port** is inspired by telephone system trunks that carry multiple conversations simultaneously.
- **Trunk ports** can carry traffic for multiple **VLANs** (up to 4,094).
- A **trunk link** is a **100- or 1000-Mbps point-to-point link** between devices (e.g., switches, routers, servers).
- **Advantages of trunking**:
    - Allows a single port to be part of multiple VLANs.
    - Supports servers in two separate broadcast domains without needing a Layer 3 device (router) for user access.
    - Carries various VLAN information between switches.
- If links are not trunked, only traffic from the configured VLAN is allowed across that link.
- Hosts connected to switches can communicate with all ports in their VLAN through trunk links.
- Using **access links** between switches allows only one VLAN to communicate, restricting communication to that VLAN without a router.
- Hosts can send data over trunked links to hosts on another switch in the same VLAN.

# VLAN Identification Methods

VLAN identification is what switches use to keep track of all those frames as they’re traversing a switch fabric. It’s how switches identify which frames belong to which VLANs,
and there’s more than one trunking method.

# **ISL)**

**Inter-Switch Link** is a method for tagging **VLAN information** onto **Ethernet frames**. This allows VLANs to be multiplexed over a **trunk link**, enabling switches to identify the **VLAN membership** of frames as they travel between switches.

- ISL maintains VLAN information over trunk links, connecting multiple switches.
- It operates at **Layer 2**, encapsulating data frames with a new **header** and **cyclic redundancy check (CRC)**.
- ISL is **proprietary** to Cisco switches and is used for **Fast Ethernet** and **Gigabit Ethernet** links only.
- It can be used on **switch ports**, **router interfaces**, and **server interface cards** to trunk a server.

# IEEE 802.1Q

is a standard for VLAN tagging on network frames. It inserts a field into the frame to identify the VLAN. When trunking between a Cisco switch and a switch from another vendor, **802.1Q must be used**.

- **Trunk Ports**: Each port you want to use as a trunk must be configured with 802.1Q encapsulation.
- **Native VLAN**: Each trunk port is assigned a VLAN ID, making it part of the native VLAN. The default native VLAN is **VLAN 1**.
- **VLAN Tagging**: Each port on the trunk is tagged with an identification number corresponding to its VLAN.
- **Native VLAN Communication**: The native VLAN allows transmission of untagged frames (frames without VLAN tags).

This process ensures VLAN information can be properly transferred across different switches.

# **Switching and Network Security**

Security is crucial, especially when it comes to preventing unauthorized devices from accessing your network. To stop people from simply plugging in a device, such as a host, hub, switch, or access point into your network, you need to implement **port security**.

By default, **MAC addresses** will dynamically show up in your switch’s **MAC address table**. Without controls, this can lead to unauthorized access. Here’s how you can secure your network:

- **Port Security**: This allows you to control which devices can connect to a switch port by limiting the number of MAC addresses that can be learned on that port.
- **MAC Filtering**: You can configure the switch to only allow specific **MAC addresses** on a given port, blocking any others from accessing the network.
- **Action on Violations**: When an unauthorized device attempts to connect, the switch can either **shut down the port**, **drop the traffic**, or **send an alert** to network administrators.

By controlling **which devices** can connect to your network ports, you ensure better protection of your network resources.

# Port Security/Authentication

**Port Security:**

- A switch can restrict port access based on MAC addresses.
- Unauthorized MAC addresses will be denied access.

**Implementing Port Security:**

- You can manually configure port security on each switch.
- This is manageable for small networks but becomes difficult for large networks with many switches.

**Using 802.1x Authentication:**

- For larger networks, 802.1x authentication allows centralized port security.
- Clients must be authenticated through a server before they can access the network.
- More details on 802.1x authentication will be covered in Chapter 13.

# How VLANs Enhance Network Security

- **Flat Networks and Security Issues**: In traditional flat networks, security was maintained by routers. This had problems:
    1. Anyone connecting to the physical network could access resources on that LAN.
    2. Users could observe traffic by plugging a network analyzer into the hub.
    3. Simply connecting a workstation to a hub would allow access to the workgroup.
- **How VLANs Improve Security**:
    - VLANs allow total control over each port and user, preventing unauthorized access just by plugging into the network.
    - VLANs create separate broadcast domains, restricting access based on user needs and network resources.
    - Switches can be configured to alert a network management station of unauthorized access attempts.
    - **Inter-VLAN Communication**: You can implement security restrictions on routers for inter-VLAN communication, including filtering by hardware addresses, protocols, and applications.

# **(PoE)**

**Power over Ethernet** is a technology that allows electrical power and data to be transmitted over standard Ethernet cables. It is commonly used to power devices like IP phones, wireless access points, network cameras, and remote switches, eliminating the need for separate power sources, which may be expensive or difficult to install.

The **IEEE 802.3af** standard defines how PoE devices are detected and how power is delivered. There are two methods for providing PoE:

1. **Through an Ethernet port on a PoE-capable switch**
2. **Via a power injector**

**IEEE 802.3at (PoE Plus)** was introduced to increase the power delivered over Ethernet. However, it is important not to use both methods (Ethernet port and injector) simultaneously, as this can cause problems.

**Key considerations for PoE:**

- For long-distance connections or outdoor setups, enterprise-grade switches with PoE are necessary to ensure sufficient power. Lower-end switches may fail to provide enough power, leading to device instability (e.g., network access points going up and down).
- Always verify that PoE switches provide the correct power level for the devices being used.

If your switch doesn't support PoE, you can use a **power injector** to supply power to the device. However, ensure the injector provides the correct voltage to avoid damaging the equipment.

PoE is commonly integrated into wireless networks, particularly for large-scale outdoor networks, where electrical outlets may be scarce.

# **Port Mirroring/Spanning (SPAN)**

Port mirroring, or SPAN, lets you sniff traffic on a network using a switch. Normally, switches send frames only to the destination port, which makes sniffing traffic difficult.

To sniff traffic, you can temporarily place a hub between two hosts, but this will disrupt the network.

**Port mirroring** solves this by placing a switch port in spanning mode, allowing traffic from Host A to be captured by both Host B and the sniffer.

**Key considerations**:

- Port mirroring can cause **overhead** on the switch, so use it strategically and for short periods to avoid network crashes.