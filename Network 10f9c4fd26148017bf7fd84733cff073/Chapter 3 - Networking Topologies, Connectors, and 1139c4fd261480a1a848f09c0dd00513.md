# Chapter 3 - Networking
Topologies,
Connectors, and
Wiring Standards

# physical media&

# ***1)coaxial&***

three types of popular cables used in modern networking designs :

Coaxial cable consists of a central conductor surrounded by insulation, a metallic shield, and an outer jacket. It is commonly used for cable TV, internet, and radio signals, providing good protection against interference and supporting high-frequency data transmission. uses BNC connector

- A type of cable used for transmitting data, consisting of:
    - **Center Conductor(material that allows the flow of electrical current.)**: Made of copper, this innermost part carries the electrical signal.
    - **plastic jacket&** : The outer layer that provides insulation& insulated& and protects the inner components.
    - **braided shield&** : A layer of braided metal surrounding the plastic jacket to prevent interference and provide grounding.
- **Polyvinyl Chloride (PVC)**: A common type of plastic used for insulation in coaxial cables, known for its durability.
- **Fluoroethylene propylene (FEP)**: Commonly known as teflon&, it offers excellent thermal resistance and is often used in high-performance applications.
- plenum rated coating& - A coaxial cable coating that does not produce toxic gas when
burned. A safety standard for cables used in plenum spaces that minimizes smoke and toxic emissions in case of a fire.
- ***plenum&*** - Many large multi-story buildings are designed to circulate air through the spaces between the ceiling of one story and the floor of the next; this
space between floors is referred to as the plenum

## ***type of*** coaxial ***cables***

thinnet& - Thinnet, also known as 10Base2, is a type of coaxial cable network technology used for local area networks (LANs). It operates at a data transmission speed of 10 megabits per second (Mbps) and has a maximum length of 200 meters (about 656 feet) per segment.

### **Types of Coaxial Cable**

- **RG-6**: The most common type for TV signals, internet, and satellite communications. It has a thicker core for better signal quality over longer distances.
- **RG-59**: Used for analog video and lower-frequency signals, suitable for short distances.
- RG-8&(thicknet) -  thick coaxial cable used for radio transmissions, early Ethernet networks like 10BASE5 (Thicknet), and high-frequency telecommunications. It is ideal for long-distance and high-power applications because of its low signal loss and durability.
- attenuation& .

## **Devices and systems that use coaxial cable today:**

1. Cable TV
2. Satellite TV
3. Cable Internet (modem to ISP)
4. Radio transmitters and antennas
5. CCTV (security cameras)
6. Home theater digital audio (S/PDIF)

### **Advantages**

- **EMI Protection**: Coaxial cables are less susceptible to electromagnetic interference due to the shielding, making them reliable for carrying signals in environments with a lot of electrical noise.
- **Bandwidth**: Coaxial cables support a wide range of frequencies, making them versatile for both analog and digital data transmission.
- **Durability**: With their rugged design, coaxial cables can withstand harsh conditions like outdoor installations.

### **Disadvantages**

- **Cost and Bulk**: Coaxial cables are bulkier than twisted-pair cables (used in Ethernet networks), and installing them can be more expensive.
- **Signal Degradation**: Over long distances, coaxial cables experience greater signal loss than fiber optics.
- **Limited Scalability**: While coaxial cables are still used, modern networks rely more on fiber optics and twisted-pair cables (e.g., Ethernet) for higher-speed and more scalable networks

////////////////////////////////////////////////////////////

# ***2)twisted pair&***

Twisted pair cables consist of two insulated copper wires twisted together to reduce interference. They are commonly used for telephone and Ethernet networks, providing reliable data transmission over short to medium distances. There are two types: unshielded (UTP) and shielded (STP).

**Twisted-Pair Cable** is made up of multiple pairs of insulated copper wires that are twisted together. There are two main types:

1. **shielded twisted pair& (STP)**:
    - This type has a metallic shield around the twisted pairs, providing extra protection against interference.
2. **unshielded twisted pair& (UTP)**:
    - This type does not have any outer shielding. It’s commonly used in Ethernet networks, including:
        - **10Base-T**: 10 Mbps Ethernet
        - **100Base-TX**: 100 Mbps Fast Ethernet
        - **1000Base-T**: 1 Gbps Gigabit Ethernet

### **Transmission Characteristics**

- **Impedance:** Typically 100 ohms.
- **Maximum Length:** The maximum length for Ethernet over twisted-pair cables is usually 100 meters (328 feet).
- **Data Rates:** Varies based on the cable category; higher categories support higher data rates.

### **Applications**

- **Voice Communication:** Telephone systems.
- **Data Communication:** Ethernet networks, local area networks (LANs).
- **Video Transmission:** In some cases, twisted-pair cables can carry video signals.

## **ethernet cable descriptions&**:

Ethernet cables are labeled using a code like **N<Signaling>-X**:

- **N**: Signaling rate in megabits per second (Mbps).
- **<Signaling>**: Type of signaling (baseband or broadband).
- **X**: Unique identifier for the cabling scheme.

**Example**: **100Base-T**

- **100**: Transmission speed of 100 Mbps.
- **Base**: Indicates baseband signaling.
- **T**: Stands for twisted-pair cables, commonly used with Category 5, 5e, or 6 UTP cables.

## UTP cable categories

1. cat1& - early type of twisted pair cabling primarily used for voice transmission in telephone lines.
2. cat2& -  for telephone lines and basic data communication. It handles up to 4Mbps, with a frequency limitation of 10MHz, and is now obsolete. Four twisted wire pairs (eight wires).
3. standard for twisted pair cabling used in networking and telecommunications. It was commonly used for voice and data communication Four twisted wire pairs (eight wires) with three twists per foot. This type can handle transmissions up to 16MHz.
4. Category 4 Four twisted wire pairs (eight wires), rated for 20MHz. Also obsolete. 
5. Category 5 Four twisted wire pairs (eight wires), rated for 100MHz. But why use
Cat 5 when you can use Cat 5e for the same price? I am not sure you can even buy
plain Cat 5 anymore!
6. Category 5e (enhanced) Four twisted wire pairs (eight wires), rated for 100MHz, but
capable of handling the disturbance on each pair that’s caused by transmitting on all four pairs at the same time—a feature that’s needed for Gigabit Ethernet. Any category below 5e shouldn’t be used in today’s network environments.
7. Category 6 Four twisted wire pairs (eight wires), rated for 250MHz. Cat 6 became a standard back in June 2002. You would usually use it as riser cable to connect floors together.
If you’re installing a new network in a new building, there’s no reason to use anything but
Category 6 UTP cabling as well as running fiber runs between floors.

## **Registered Jack (RJ)**

**RJ 11&**: This is used for telephones and typically connects using four wires. It’s a smaller connector.

- **RJ 45&**: This is used for Ethernet and has eight wires organized into four pairs. It's larger than the RJ-11 and is commonly found in network connections.
    
    

### **Advantages**

- **Cost-Effective:** Generally less expensive than fiber optic cables.
- **Ease of Installation:** Flexible and easy to work with.
- **Support for High Speeds:** Higher categories support gigabit and faster Ethernet.
- **Reduced Interference:** Twisting reduces interference and crosstalk&.

### **Disadvantages**

- **Distance Limitations:** Signal degradation over longer distances.
- **Susceptibility to Interference:** While twisting helps, UTP is more susceptible to EMI compared to STP or fiber optics.
- **Bandwidth Limitations:** Lower categories may not support higher bandwidth applications.

//////////////////////////////////////////////////

# ***3)fiber optic&***

Fiber-optic cables use light signals to transmit data at very high speeds over long distances. They consist of thin strands of glass or plastic that carry light, offering faster and more reliable connections compared to traditional copper cables.

**Here are the pros:**
1) Is completely immune to EMI and RFI
2) Can transmit up to 40 kilometers (about 25 miles)

**And here are the cons:**
1) Is difficult to install
2) Is more expensive than twisted-pair
3) Troubleshooting equipment is more expensive than twisted-pair test equipment
4) Is harder to troubleshoot

## Single-mode fiber-optic cable (SMF)

**is a type of optical fiber designed for long-distance communication, using a single light path or mode to transmit data.**

## **Multimode fiber-optic cable (MMF)**

a type of optical fiber designed to carry multiple light modes or rays simultaneously. It is commonly used in short-distance communication due to its cost-effectiveness and ease of installation.

## Fiber-Optic Connectors

![image.png](Chapter%203%20-%20Networking%20Topologies,%20Connectors,%20and%201139c4fd261480a1a848f09c0dd00513/image.png)

 straight tip (ST)

![image.png](Chapter%203%20-%20Networking%20Topologies,%20Connectors,%20and%201139c4fd261480a1a848f09c0dd00513/image%201.png)

subscriber connector (SC)

![image.png](Chapter%203%20-%20Networking%20Topologies,%20Connectors,%20and%201139c4fd261480a1a848f09c0dd00513/image%202.png)

## **Small Form Factor Fiber-Optic Connectors (SFP)**

Types:

1) mechanical transfer registered jack(MTRJ)

![image.png](Chapter%203%20-%20Networking%20Topologies,%20Connectors,%20and%201139c4fd261480a1a848f09c0dd00513/image%203.png)

2)Local Connector(LC) terminating&

![image.png](Chapter%203%20-%20Networking%20Topologies,%20Connectors,%20and%201139c4fd261480a1a848f09c0dd00513/image%204.png)

## Serial Cables

### 1)rs 232

![image.png](Chapter%203%20-%20Networking%20Topologies,%20Connectors,%20and%201139c4fd261480a1a848f09c0dd00513/image%205.png)

2)**Universal Serial Bus (USB)**

widely used standard for connecting and transferring data and power between computers, peripherals, and other electronic devices. Here’s a detailed breakdown to help you organize all the important aspects of USB into your notes.

# ***cable properties&***

## distance&

A deciding factor used in choosing what cable type to use is often the topology of a network
and the distance between its components. Some network technologies can run much further
than others without communication errors, but all network communications technologies are
prone to attenuation& —the degradation of signal due to the medium itself and the distance
signals have to travel. Some cable types suffer from attenuation more than in others. For
instance, any network using twisted-pair cable should have a maximum segment length of
only 328 feet (100 meters).

## duplex&

All communications are either half-duplex or full-duplex. The difference is whether the
communicating devices can “talk” and “listen” at the same time.
During half-duplex communication, a device can either send communication or receive
communication, but not both at the same time. Think walkie-talkie—when you press the
button on the walkie-talkie, it turns the speaker off, and you can’t hear anything the other
side is saying.
In full-duplex communication, both devices can send and receive communication at the
same time. This means that the effective throughput is doubled and communication is much
more efficient. Full-duplex is typical in most of today’s switched networks.

## Noise Immunity (Security, EMI)

When electricity flows through wires, it creates a magnetic field. This magnetic field can cause two problems for communication:

1. **Wire tapping**: Since the magnetic field carries the data (1s and 0s), someone with the right tools can tap into the wire and read the signal without cutting or exposing the wire. This is a security risk. Shielded cables like STP (Shielded Twisted Pair) offer some protection, but they aren't perfect. Fiber-optic cables are much more secure because they use light instead of electricity, making them much harder to tap.
2. **External interference (EMI)**: Wires can pick up extra electrical current from nearby magnetic sources, like motors or speakers, which can interfere with the data being transmitted. To avoid this, cables should be kept away from strong magnetic fields to reduce interference.

In short, electricity in wires can cause security and interference issues, which is why fiber-optic cables, using light instead of electricity, are a more secure and interference-free option.

frequency&

Each cable type has a specified maximum frequency that gives you the transmission bandwidth it can handle. Cat 5e cable is tested to 100MHz maximum frequency and can run
1Gbps signals for relatively short distances. That’s maxing it out, but it’s still good for connecting desktop hosts at high speeds. On the other hand, Cat 6 is a 250MHz cable that
can handle 1Gbps data flow all day long with ease. Cat 6 has a lot more twists and thicker
cables, so it is best used when connecting floors of a building.

# **wiring standards&**

There are different types of wiring standards available:
* Straight-through cable (586A)
* Crossover cable (586B)
* Rolled cable (rollover)
* Hardware loopback

## **568A(Straight-Through Cable) vs 568B(Crossover cable)**

In a **UTP cable**, there are **eight wires**, but only **four wires** are used for data transmission (the pairs connected to **pins 1, 2, 3, and 6**).

### Wiring Options:

1. **568A& Standard (Straight Through Cable)**:
    - If you connect the wires as follows:
        - **Pin 1**: Green with white
        - **Pin 2**: Green
        - **Pin 3**: Orange with white
        - **Pin 6**: Orange
    - This creates a **straight-through cable**, which is commonly used as a patch cable& in networks.
2. **568B& crossover cable&**: (3x)
    - If you switch the connections for pins 1 and 3, and pins 2 and 6 on one side, you create a **crossover cable**.
    - This type of cable is used to connect similar devices directly, like connecting two computers or two switches.

In summary, connecting wires in the 568A standard creates a straight-through cable, while switching certain connections makes it a crossover cable. NOTE!

## rolledover over cable&

A **rollover cable** is a special type of cable used for connecting a computer to a router or switch's console port, allowing you to manage the device. Here’s a breakdown of its features and uses:

1. **Purpose**: Rollover cables are primarily used to connect a computer (running terminal software like HyperTerminal) to the console port of networking devices like routers and switches. This connection allows for configuration and management of the device.
2. **Wiring**: The cable consists of eight wires, but unlike Ethernet cables, not all of these wires are used for data transmission. The wiring is "rolled," meaning the pin connections are reversed on each end of the cable:
    - Pin 1 on one end connects to Pin 8 on the other end.
    - Pin 2 connects to Pin 7, and so on.
3. **Connection Type**: Rollover cables use a **DB-9** or **RJ-45** connector, depending on the device. The connection is typically to the console port of a router or switch, which is different from the Ethernet ports used for network connections.
4. **Usage Scenario**: When you want to configure a router or switch directly, you would connect the rollover cable from your computer to the console port of the device. Then, you can use terminal-emulation software on your computer to send commands and configure the device.

In summary, a rollover cable is essential for managing network devices directly through their console ports, enabling network administrators to configure and troubleshoot routers and switches.

## hardware loopback&—————————————————-

A **loopback plug** is a small device used to test whether your computer's network card (called a **NIC** or Network Interface Card) is working properly. It does this by **redirecting** (or "looping back") the computer's own data back into itself.

- **Normally**: Your computer sends data out to a network, and then receives data back from the network.
- **With a loopback plug**: The data the computer sends out is redirected back to itself, so the computer thinks it's receiving data from a network, when in reality, it's just receiving its own data.

### 2. **Why is it Used?**

- It's used when you want to **test** your computer's ability to send and receive data without needing a real network connection.
- This is helpful for **diagnostic testing**—making sure the NIC (network card) can send and receive data properly, especially when setting up a new computer or troubleshooting problems.

### 3. **How Does It Work?**

- **Normally**: A network cable has two types of pins—**transmit pins** (send data) and **receive pins** (get data).
- **In a loopback plug**: The transmit pins are directly connected to the receive pins inside the plug. So when the computer sends out data, the plug immediately sends it back to the receive pins, tricking the computer into thinking it’s getting data from a network.

### 4. **How to Use It?**

- You plug the **loopback plug** into the **RJ-45 port** (where you'd normally plug in a network cable) on the back of the NIC.
- Then, you run the **diagnostic software** that comes with your NIC.
- The software will test if the NIC can both send and receive data by sending the data through the loopback plug.

### In Summary:

A **loopback plug** is used to test if your network card is functioning by tricking the computer into thinking it’s connected to a network when it’s actually just looping its own data back. It helps with diagnostics, ensuring your NIC can send and receive data correctly.

# Vertical and Horizontal Cross Connects&

A **cross-connect** is a physical location where all the cables in a building come together. It’s like a central hub where cables can be connected, reconnected, or managed using tools like **jumpers** (short cables), **termination blocks**, or **patch panels**.

### 2. **Types of Cables**:

- **Horizontal cables**: These are the cables that run **across the same floor** in a building, connecting communication closets (where network equipment is kept) to wall outlets in different rooms. They are called "horizontal" because they run sideways or across the floor.
- **Backbone/Vertical cables**: These are the cables that run **between different floors** of a building, connecting important areas like equipment rooms or telecom rooms. They are called "vertical" because they often run up and down, between floors.

### 3. **How It All Connects**:

All these different types of cables—horizontal and vertical—eventually meet at the **cross-connect** and are connected together to complete the network for the building. The exact setup and equipment used depend on how big the building is and the specific needs of the company.

In short:

- **Cross-connect**: Where all the cables come together.
- **Horizontal cables**: Connect areas on the same floor.
- **Backbone/vertical cables**: Connect different floors.
- All these cables work together to finish the building’s network.

# Patch Panels&——————-

A **patch panel** is a **device** that's usually mounted on a wall or in a rack and helps organize and connect network cables. It has two sides:

- **Front side**: You plug in **patch cables** (short, flexible cables).
- **Back side**: Holds the **longer, permanent cables** that run through the building's walls.

### 2. **Why is it Useful?**

- The purpose of the patch panel is to make it **easy to manage** and **change network connections** without messing with permanent cables.
- If you need to **change the path** of a network signal, you can just switch the connections on the front of the panel.

### 3. **What Happens if a Cable Breaks?**

- If a cable inside the wall gets damaged or stops working, the network admin can simply **"patch around"** the bad cable.
- This means they can **redirect the connection** by changing how the cables are plugged in on the patch panel, avoiding the need to replace the broken cable right away.

In short:

- A **patch panel** makes managing network connections easier and quicker, especially if something goes wrong with the cables inside walls.

# MDF/IDF&

The main distribution frame (MDF) is a wiring point that’s generally used as a reference
point for telephone lines. It’s installed in the building as part of the pre-wiring, and the
internal lines are connected to it. After that, all that’s left is to connect the external (telephone company) lines to the other side to complete the circuit. Often, another wire frame
called an intermediate distribution frame (IDF) is located in an equipment or telecommunications room. It is connected to the MDF and is used to provide greater flexibility for the
distribution of all the communications lines to the building. It is typically (and better be) a
sturdy metal rack designed to hold the bulk of cables coming from all over the building!

# 25 pair&

100 pair&

# 110 Block&

A 110 block is a modern wiring distribution point that has largely replaced older telephone wire installations and is now used for computer networking as well. One side of the block has wires punched down, while the other side features RJ-11 (for phones) or RJ-45 (for networks) connections. 110 blocks come in various sizes, accommodating 25 to over 500 wire pairs, and can support speeds up to 1 Gbps with Category 6 cables. However, using Cat 6 with a 110 block can be challenging due to the larger size of the Cat 6 wiring.

# Demarc / Demarc Extension———-

The **demarc** (short for demarcation) is the point where the service provider's responsibility ends and your responsibility begins. It's usually found at the main distribution frame (MDF) in larger buildings or as a simple RJ-45 jack where your router connects to the wide area network (WAN) via a channel service unit/data service unit (CSU/DSU).

When network administrators troubleshoot issues, they check connectivity on both sides of the demarc to see if the problem is inside your network or outside. The **demarc extension** refers to the length of copper or fiber cable that comes after the demarc but doesn't reach all the way to your office.

# Smart jack&

A **smart jack**, also known as a **network interface device (NID)** or **network interface unit**, is owned by the Public Switched Telephone Network (PSTN). It serves as a special connection point between the service provider’s network and your internal network. Unlike a simple demarc, which is just an RJ-45 jack and cannot be physically tested, a smart jack can include power and testing features.

Smart jacks may also convert codes and protocols, allowing signals from the service provider to be used by devices on your internal network, such as the **channel service unit/data service unit (CSU/DSU)**.