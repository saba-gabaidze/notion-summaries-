# Chapter 3 Analyzing And Managing Networks

# `iwconfig`

- **Device Name**: The name of your wireless device (e.g., `wlan0`).
- **Wireless Standard**: The wireless standards supported by the device (e.g., `802.11bg` for older standards, `802.11n` for newer ones).
- **Mode**: The mode your device is operating in, such as **Managed** (connected to a Wi-Fi network), **Monitor** (used for capturing packets), or **Promiscuous** (captures all network traffic).
- **Association Status**: Whether the device is connected to an access point (AP). In the example, it’s **Not Associated**.
- **Signal Strength (Tx-Power)**: The strength of the wireless signal (e.g., `20 dBm`).

```mathematica
mathematica
Copy code
wlan0 IEEE 802.11bg ESSID:off/any
Mode:Managed Access Point: Not Associated Tx-Power=20 dBm
lo no wireless extensions
eth0 no wireless extensions

```

- **wlan0**: Your wireless interface, currently in **Managed mode** (not connected to any access point).
- **lo** and **eth0**: These are network interfaces that don’t support wireless features

# Changing Your Network Information

## `ifconfig “eth0” “ip address”` - changing your ip address

`ifconfig eth0 “192.168.181.115” netmask “255.255.0.0” broadcast “192.168.1.255”` - changing subnetmask/broadcast 

## Spoofing Your MAC Address

`ifconfig eth0 down` - take down eth0

`ifconfig eth0 hw ether “mac address”` - enter address

`ifconfig eth0 up` - bring up eth0

## `dhclient “eth0”` - Assigning New IP Addresses from the DHCP Server

# Manipulating the Domain Name System

### `dig “google.com” ns` - to find nameservers

### `dig “g.com” mx` - to find email servers associated with a domain

## **Changing Your DNS Server**

### To change your DNS server in Linux, you can modify the (`vim /etc/resolv.conf`) file.

input -  “nameserver 8.8.8.8”

`echo “nameserver 8.8.8.8”> etc/resolv.conf`

## Mapping Your Own IP Addresses

### `vim /etc/hosts` - and add 192.168.181.131 [bankofamerica.com](http://bankofamerica.com/) for example