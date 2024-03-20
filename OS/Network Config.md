
### Network Interfaces
- **ifconfig**: Tool for configuring network interfaces.
  - **Usage**: `ifconfig -a` to list all interfaces.
  - **Configuring IP**: `ifconfig eth0 192.168.2.1 netmask 255.255.255.0 up` assigns an IP and netmask to eth0 and activates it.
  - **Interface Names**: Commonly eth0 (Ethernet), wlan0 (wireless), lo (loopback).

### The `ip` Command
- More modern than `ifconfig` for network configuration.
  - **Show interfaces**: `ip link show`.
  - **Interface stats**: `ip -s link show eth0`.
  - **IP addresses**: `ip address show`.
  - **Up/Down**: `ip link set eth0 up/down`.
  - **Adding IP**: `ip address add 192.168.1.1/24 dev eth0`.

### Route Management
- **Adding/Deleting routes**:
  - `sudo route add -net 192.168.2.1/23 gw 10.11.12.3`.
  - `sudo route del -net 192.168.2.1/23`.
- **Using ip for routes**:
  - `ip route add 192.168.2.1/23 via 10.11.12.3`.
  - `ip route delete 192.168.2.1/23`.

### DHCP Configuration
- **dhclient**: Automatically configures IP using DHCP.
  - **Usage**: `sudo dhclient` to obtain a fresh IP.

### Network Manager
- Automates network configuration.
- **GUI and CLI tools**:
  - `nm-tool` to report state and devices.
  - `nmcli` for controlling NetworkManager.

### ARP Cache
- **View ARP cache**: `arp` or `ip neighbour show`.
- **Cache usage**: Populated as packets are sent, used for MAC address resolution.

### ARP Cache Overview

- **ARP Cache Inspection**: Use `arp` or `ip neighbour show` to view the ARP cache, displaying mappings between IP addresses and MAC addresses.
- **Cache Initialization**: Initially empty, the ARP cache is populated dynamically as the system communicates with other network hosts.
- **Populating Process**:
    - **Packet Transmission to New Destination**: Triggers an ARP request if the destination MAC is unknown.
    - **ARP Request Broadcast**: The request, encapsulated in an Ethernet frame, is broadcast across the network.
    - **Receiving ARP Reply**: A host with the matching IP address replies with its MAC address.
    - **Cache Update**: The source host updates the ARP cache with the new mapping and continues with packet transmission.
