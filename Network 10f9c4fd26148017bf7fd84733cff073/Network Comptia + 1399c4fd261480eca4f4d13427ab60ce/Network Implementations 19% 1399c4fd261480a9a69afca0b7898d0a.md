# Network Implementations 19%

# 2.1

## **Voice Gateway**

- **Features**: Converts digital voice packets from a VoIP (Voice over IP) network into analog signals and vice versa for traditional telephony networks.
- **Placement**: Positioned between a VoIP network and the Public Switched Telephone Network (PSTN).
- **Use**: Allows communication between IP-based phone systems and traditional telephone systems.

## **VPN Headend**

- **Features**: Terminates VPN tunnels from remote clients or sites, encrypting and decrypting data for secure communication.
- **Placement**: Positioned at the network’s edge, acting as the gateway for remote users or branch offices.
- **Use**: Allows secure remote access to a corporate network or site-to-site VPN communication over the internet.

## **Heating, Ventilation, and Air Conditioning (HVAC) Sensors**

- **Features**: Monitors and controls environmental factors like temperature, humidity, and air quality. Connects to building management systems (BMS) to automate climate control.
- **Placement**: Distributed across various zones or rooms within a building for efficient climate control.
- **Use**: Provides automated HVAC management, optimizing energy usage based on environmental data, especially in commercial and industrial settings.

## **Internet of Things (IoT) Devices**

- **General Features**: IoT devices are connected objects that communicate over a network, often providing automation and remote control.
- **Placement**: Distributed across homes, offices, and industrial settings, often on a dedicated IoT network for secure management.

## **Industrial Control Systems (ICS) / Supervisory Control and Data Acquisition (SCADA)**

- **Features**: Used for monitoring and controlling industrial processes. Typically comprises sensors, control systems, and networked computers that gather and process data.
- **Placement**: Installed in industrial environments, such as manufacturing plants, power grids, and water treatment facilities, often on a dedicated network for enhanced security.
- **Use**: Provides remote control and monitoring of industrial operations. SCADA is crucial in managing and automating processes critical to infrastructure and industrial production.

# 2.2

## **Administrative Distance**

- **Definition**: A metric used to determine the reliability of a route, particularly when multiple routes to the same destination are available. Lower values indicate preferred routes.
- **Use Case**: Used to prioritize routes from different sources, such as preferring a static route over a dynamic route.

## **Traffic Shaping**

- **Definition**: Controls the rate at which data is sent into the network by delaying some packets to meet a desired speed threshold, smoothing out bursts of traffic.
- **Use Case**: Common in environments where a steady flow of traffic is desired, such as for voice or video streaming, preventing bandwidth spikes that can lead to congestion.

# 2.3

## **Port Aggregation and Link Aggregation Control Protocol (LACP)**

: Aggregate multiple physical links into a single logical link for higher bandwidth and redundancy.

- **Example**: Configure LACP on trunk ports connecting core and access switches for enhanced throughput and failover support.

## **Auto MDI-X**

 Automatically configure ports for crossover or straight-through cables, eliminating the need for specific cabling between devices.

## **Carrier-Sense Multiple Access with Collision Detection (CSMA/CD)**

- **Function**: CSMA/CD prevents collisions on Ethernet networks, mainly for legacy systems still using half-duplex connections.
- **Configuration**: Ensure all modern connections are full-duplex, minimizing reliance on CSMA/CD. However, CSMA/CD might still apply in environments with older devices and half-duplex configurations.

# 2.4

## **802.11 Standards and Wi-Fi Generations**

Each 802.11 standard has different speeds, frequencies, and technologies:

- **802.11a**: Operates at 5GHz with a maximum speed of 54 Mbps. Best used for environments with high-density wireless traffic.
- **802.11b**: Operates at 2.4GHz with speeds up to 11 Mbps. It’s older and less efficient due to interference with devices like microwaves.
- **802.11g**: Operates at 2.4GHz with speeds up to 54 Mbps, combining the benefits of 802.11a and 802.11b but still limited by the 2.4GHz range.
- **802.11n (Wi-Fi 4)**: Dual-band (2.4GHz and 5GHz), offering speeds up to 600 Mbps using MIMO (Multiple Input, Multiple Output) technology for better range and throughput.
- **802.11ac (Wi-Fi 5)**: Operates on 5GHz, supporting speeds of up to 1.3 Gbps and offering wider channels (80MHz to 160MHz) and higher efficiency.
- **802.11ax (Wi-Fi 6)**: Dual-band with improved speed (up to 9.6 Gbps) and better efficiency, handling more devices and offering features like OFDMA (Orthogonal Frequency Division Multiple Access) and MU-MIMO (Multi-User MIMO).

## **5GHz Channels**

: 5GHz offers a wider range of channels (36-165). In addition, **channel bonding** (combining 2 channels for 40 MHz or 80 MHz) can increase throughput but may cause more interference.

- **Regulatory Impacts**: Different countries have different regulations on the available channels and power limits. For instance, DFS (Dynamic Frequency Selection) channels may be restricted to avoid interfering with radar systems.

**Recommendation**: Use **80MHz bonding** on **5GHz** for optimal throughput, and configure channels carefully based on the environment and regulatory requirements. Tools like **Wi-Fi analyzers** can assist in selecting the best channels.

## SSID

- **BSS**: One Wi-Fi area with one access point.
- **ESS**: Many Wi-Fi areas that are connected, letting you move around and stay connected.
- **IBSS**: Direct connection between devices, no access point needed, for small, temporary networks.

## **Encryption Standards**

- **WPA/WPA2 Personal**: Provides encryption using **AES** (Advanced Encryption Standard) or **TKIP** (Temporal Key Integrity Protocol). AES is recommended due to its stronger security.
- **WPA/WPA2 Enterprise**: Uses a RADIUS server for authentication, providing more control over security and is typically used in business environments.

## **Cellular Technologies**

Cellular technologies

- Code-division multiple access (CDMA)
- Global System for Mobile
Communications (GSM)
- Long-Term Evolution (LTE)
- 3G, 4G, 5G