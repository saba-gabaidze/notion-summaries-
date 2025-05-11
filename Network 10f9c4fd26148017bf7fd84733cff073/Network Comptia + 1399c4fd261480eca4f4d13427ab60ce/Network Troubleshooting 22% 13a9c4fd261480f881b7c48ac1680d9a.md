# Network Troubleshooting 22%

# 5.1

## 7 steps

# 5.2

## **Cable Considerations**

- **Shielded vs. Unshielded**: Shielded cables (STP) reduce electromagnetic interference (EMI), while unshielded cables (UTP) are suitable for low-EMI environments.
- **Plenum vs. Riser-Rated**: Plenum-rated cables are necessary for spaces with strict fire codes; riser-rated cables work in vertical applications like walls.
- **Common Tools**: Use **Spectrum Analyzers** to detect and measure EMI if there’s interference suspicion.

## **Common Issues and Fixes**

- **Attenuation**: Signal weakening over long distances. Solutions include reducing cable length or using a **Fiber Light Meter** for optical cables.
- **Interference**: Signal disruptions from nearby devices. Shielded cables help, and **Spectrum Analyzers** can identify interference sources.
- **Decibel (dB) Loss**: Check for excessive dB loss which can degrade signal quality, often assessed with an **OTDR** for fiber cables.
- **Incorrect Pinout**: Miswired connectors can cause connectivity issues. Use a **Cable Tester** or **Wire Map** to verify pinouts.
- **Bad Ports/Connections**: Inspect for damaged ports and connectors. Replace damaged components and use a **Multimeter** to verify connections.
- **Open/Short Circuits**: Open circuits mean broken wires, and shorts are unintended connections. A **Multimeter** or **Cable Tester** helps identify these.
- **LED Status Indicators**: LEDs can indicate connectivity (e.g., solid for active, flashing for transmitting data). Follow device documentation for interpretation.
- **Incorrect Transceivers**: Ensure transceivers match cable specifications (e.g., copper vs. fiber).
- **Duplexing Issues**: Full duplex supports bidirectional communication, while half duplex does not. Duplex mismatch can slow connections.
- **TX/RX Reversal**: Incorrect transmitter/receiver wiring affects data transmission. Use a **Loopback Adapter** or **Cable Tester**.
- **Dirty Optical Cables**: Clean fiber optic connectors to prevent loss or distortion. Use fiber-safe cleaners.

### **Common Tools**

- **Cable Crimper**: To attach RJ45 connectors to UTP/STP cables.
- **Punchdown Tool**: Secures wires in patch panels.
- **Tone Generator and Probe**: Useful for tracing cable paths.
- **Loopback Adapter**: Tests connectivity by looping the signal back to the device.
- **OTDR**: Analyzes fiber optic cables for dB loss and breaks.
- **Multimeter**: Measures electrical values like voltage and continuity.
- **Cable Tester**: Checks for faults like open/short circuits, pinouts, and PoE.
- **Wire Map**: Verifies that cables are wired in the correct order.
- **Fiber Light Meter**: Measures signal strength in fiber optic cables.
- **Snips/Cutters and Cable Stripper**: For cutting and stripping cable jackets.
- **Fusion Splicers**: For joining fiber optic cables.
- **Spectrum Analyzers**: Identifies interference in the electromagnetic spectrum.

# 5.3

## `nslookup` / `dig`: Verify DNS resolution for a domain.

# 5.4?

### 1. **Specifications and Limitations**

- **Throughput & Speed:** Wireless connections have theoretical speeds (e.g., 300 Mbps for Wi-Fi 5). However, obstacles, device capabilities, and interference can reduce actual speeds. Check the network specifications and the device’s maximum throughput.
- **Distance:** Wireless signal strength and speed degrade over distance. Ensure devices are within the optimal range of the access point (AP).
- **Received Signal Strength Indication (RSSI):** This measures signal strength. If RSSI is too low (usually below -70 dBm), connectivity may be unstable. Try moving closer to the AP or reducing interference.
- **Effective Isotropic Radiated Power (EIRP):** The AP’s power settings impact signal reach. Increasing EIRP can boost coverage, but avoid excessive power settings, as they may cause interference.

### 2. **Considerations**

- **Antennas:** Antenna type (omnidirectional, directional), placement, and polarization are crucial. Ensure AP antennas are optimally placed and properly polarized to match client device orientations. Adjust if necessary.
- **Channel Utilization:** Congestion on specific channels can degrade performance. Use a tool like a Wi-Fi analyzer to check channel usage and switch to a less crowded one.
- **AP Association Time:** Delays in AP association may indicate configuration issues. Confirm proper AP configuration and check for firmware updates.
- **Site Survey:** Conduct a site survey to assess signal strength, interference, and coverage in various locations. This helps identify dead zones or areas of weak coverage.

### 3. **Common Issues**

- **Interference (Channel Overlap):** Nearby networks or devices on the same frequency band can cause interference. Switch channels or use the 5 GHz band to reduce overlap.
- **Antenna Cable & RF Attenuation:** Check for cable quality and signal loss, especially with long antenna cables. Ensure cables are appropriate for the installation.
- **Wrong SSID or Incorrect Passphrase:** Double-check SSID and passphrase to ensure correct network access.
- **Encryption Protocol Mismatch:** Confirm compatible encryption protocols (e.g., WPA2 or WPA3) between APs and client devices. Incompatibility can prevent connections.
- **Insufficient Wireless Coverage:** Use additional APs or range extenders to improve coverage in dead zones.
- **Captive Portal Issues:** Captive portals on guest networks may require user interaction for access. Ensure the captive portal is correctly configured and accessible.
- **Client Disassociation Issues:** Frequent disconnections may occur if signal strength is poor or if the AP has limited client support.

# 5.5

### 1. **Device Configuration Review**

- **Verify basic settings**: Ensure IP addresses, subnet masks, default gateways, and DNS settings are configured correctly on all devices. Common issues can include incorrect IP addresses, gateways, or DNS.
- **Check for duplicate IPs or MAC addresses**: These conflicts can cause connectivity issues and intermittent network problems.
- **Review VLAN assignments**: Ensure devices are assigned to the correct VLANs as mismatches can prevent network access or cause segmentation issues.

### 2. **Check Routing Tables and Paths**

- **Examine routing tables**: Look for missing or incorrect routes that might prevent proper network traffic flow. Missing routes could result in unreachable network segments.
- **Review asymmetrical routing**: Routing inconsistencies may cause traffic to take different paths, impacting latency and performance.
- **Identify potential routing loops**: These loops can degrade network performance by causing packets to circulate indefinitely.

### 3. **Interface Status and Layer 1 Issues**

- **Check physical connections**: Inspect cables and fiber optics for physical damage or loose connections.
- **Monitor interface status**: Verify if interfaces are up and operational, paying attention to error counters for signs of collisions or low link budgets (signal degradation).
- **Low optical link budget**: Check optical power levels to confirm that the signal is strong enough for reliable data transmission.

### 4. **Switching and Layer 2 Issues**

- **Switching loops**: Ensure spanning tree protocol (STP) is correctly configured to prevent loops in your network.
- **Broadcast storms**: If broadcast traffic is overwhelming the network, consider optimizing switch settings and using VLANs to limit broadcast domains.
- **Multicast flooding**: Verify proper multicast group memberships and configurations on switches to prevent excessive multicast traffic.
- **VLAN tagging issues**: Incorrect VLAN assignments may result in devices being unable to access the right network segments.

### 5. **Network Layer and IP Configuration**

- **IP conflicts and DHCP settings**: Duplicate IP addresses or rogue DHCP servers can cause network disruptions. Check DHCP scopes to prevent exhaustion and assign IPs only within the designated range.
- **Check IP configuration**: Ensure devices have the correct IP address, subnet mask, default gateway, and DNS server.
- **Firewall and Access Control Lists (ACLs)**: Confirm that firewall settings, both host-based and network-based, allow necessary traffic. Ensure ACLs aren’t blocking required ports, services, or IP addresses.

### 6. **Higher-Layer Services and Protocols**

- **DNS and NTP issues**: Verify DNS functionality to ensure devices can resolve names correctly. Also, check NTP configurations to synchronize network device clocks.
- **Certificate and license management**: Ensure SSL/TLS certificates are valid and properly configured, and confirm that any licensed features on network equipment are active.
- **Blocked services or ports**: Use tools like Telnet, SSH, or Ping to test connectivity over specific ports and ensure necessary services are accessible.

### 7. **Performance Troubleshooting**

- **Establish network performance baselines**: Compare current performance metrics to baselines to identify unusual network behavior. This can reveal performance drops due to issues like asymmetrical routing or packet loss.
- **Analyze traffic**: Use network analyzers to detect patterns like high collision rates or broadcast storms, indicating possible network congestion or misconfigurations.

### 8. **Security and Policy-Related Issues**

- **Inspect BYOD policies and settings**: Confirm security policies for bring-your-own-device environments, as personal devices may introduce security or performance challenges.
- **Rogue DHCP detection**: Unauthorized DHCP servers can cause network disruptions by issuing incorrect IP addresses, leading to connectivity issues.

By systematically addressing each category, you can isolate and resolve most networking issues. For complex cases, use monitoring tools to help visualize traffic and detect specific points of failure.