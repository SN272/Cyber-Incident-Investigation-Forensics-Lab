# Lab Command Reference

## Case ID

DFIR-2026-001

## Purpose

This document records the Linux and NetworkManager commands used during the DFIR laboratory configuration and explains their purpose, important options, and relevance to the investigation environment.

The command reference is maintained as a technical learning and reproducibility resource for the simulated DFIR investigation.

---

# 1. Display Network Interfaces and Addresses

## Command

`ip addr`

## Purpose

Displays network interfaces and the IP addressing information associated with each interface.

The command was used to identify the network interface connected to the VirtualBox internal network and determine the IPv4 configuration of the Kali Linux analysis node.

## Investigation Relevance

Identifying the correct network interface is necessary before assigning a controlled laboratory IP address or interpreting network-related artifacts.

---

# 2. Display the IPv4 Routing Table

## Command

`ip route`

## Purpose

Displays the system's IPv4 routing table.

The routing table determines where IPv4 network traffic is sent.

## Relevant Routing Terms

| Output Term | Meaning |
|-------------|---------|
| `10.10.50.0/24` | Destination network represented using CIDR notation. |
| `/24` | Network prefix identifying the network portion of the IPv4 address. |
| `dev eth0` | Traffic for the route is sent through the `eth0` interface. |
| `proto kernel` | Route was automatically created by the Linux kernel based on interface configuration. |
| `scope link` | Destination is directly reachable on the local network link. |
| `src 10.10.50.10` | Preferred source IPv4 address for traffic using the route. |
| `metric 100` | Route preference value. |
| `default` | Route used when no more specific route matches a destination. |
| `default via` | Specifies the gateway used for default-routed traffic. |

## Observed Lab Route

`10.10.50.0/24 dev eth0 proto kernel scope link src 10.10.50.10 metric 100`

## Interpretation

The Kali system had a directly connected route to the `10.10.50.0/24` laboratory network through `eth0`.

No IPv4 default route was observed.

## Investigation Relevance

Routing verification established that the laboratory interface was not configured as an IPv4 default route and supported the intended isolated network design.

---

# 3. Display NetworkManager Device Status

## Command

`nmcli device status`

## Purpose

Displays network devices recognised by NetworkManager and their current connection states.

## Output Columns

| Column | Meaning |
|--------|---------|
| `DEVICE` | Network interface or device name. |
| `TYPE` | Type of network device, such as Ethernet or loopback. |
| `STATE` | Current NetworkManager state of the device. |
| `CONNECTION` | NetworkManager connection profile associated with the device. |

## Initial Observation

The `eth0` interface was initially displayed as:

`eth0 ethernet disconnected --`

This indicated that NetworkManager recognised the Ethernet interface but no active connection profile was associated with it.

## Investigation Relevance

The command was used to determine the state of the laboratory network interface before configuring the NetworkManager profile.

---

# 4. Create a NetworkManager Ethernet Profile

## Command

`sudo nmcli connection add type ethernet ifname eth0 con-name DFIR-LAB-KALI ipv4.method manual ipv4.addresses 10.10.50.10/24`

## Purpose

Creates a persistent NetworkManager Ethernet connection profile for the Kali Linux analysis node.

## Command Breakdown

| Term | Meaning |
|------|---------|
| `sudo` | Executes the command with elevated administrative privileges. |
| `nmcli` | NetworkManager command-line interface. |
| `connection` | Performs an operation involving NetworkManager connection profiles. |
| `add` | Creates a new connection profile. |
| `type ethernet` | Defines the connection as an Ethernet connection. |
| `ifname eth0` | Associates the connection profile with the `eth0` interface. |
| `con-name DFIR-LAB-KALI` | Assigns the name `DFIR-LAB-KALI` to the connection profile. |
| `ipv4.method manual` | Configures IPv4 addressing manually rather than using DHCP. |
| `ipv4.addresses` | Specifies the IPv4 address assigned to the connection. |
| `10.10.50.10/24` | Static IPv4 address and network prefix assigned to the Kali analysis node. |

## Why Manual Addressing Was Used

The `DFIR-LAB` VirtualBox internal network used static addressing rather than DHCP.

Static addressing also provides predictable IP identities for network analysis and evidence interpretation.

## Investigation Relevance

A known static IP address allows network traffic associated with the Kali analysis node to be consistently identified during PCAP analysis.

---

# 5. Prevent the Lab Connection from Becoming a Default Route

## Command

`sudo nmcli connection modify DFIR-LAB-KALI ipv4.never-default yes`

## Purpose

Configures the `DFIR-LAB-KALI` connection so that NetworkManager does not use it as an IPv4 default route.

## Command Breakdown

| Term | Meaning |
|------|---------|
| `connection modify` | Changes an existing NetworkManager connection profile. |
| `DFIR-LAB-KALI` | Name of the connection profile being modified. |
| `ipv4.never-default` | Controls whether the connection can provide the IPv4 default route. |
| `yes` | Prevents the connection from becoming the default IPv4 route. |

## Investigation Relevance

This configuration supports the isolated laboratory design by preventing the lab connection from becoming the system's general IPv4 route.

---

# 6. Disable IPv6 on the Lab Profile

## Command

`sudo nmcli connection modify DFIR-LAB-KALI ipv6.method disabled`

## Purpose

Disables IPv6 for the `DFIR-LAB-KALI` connection profile.

## Command Breakdown

| Term | Meaning |
|------|---------|
| `ipv6.method` | Controls the IPv6 configuration method for the connection. |
| `disabled` | Disables IPv6 configuration for the connection profile. |

## Reason for the Lab Configuration

The simulated investigation network was designed around the IPv4 subnet `10.10.50.0/24`.

Disabling IPv6 on the designated laboratory profile reduced unrelated IPv6 traffic during the controlled network capture process.

## Investigation Relevance

Reducing unrelated protocol traffic helped keep the controlled IPv4 communication easier to analyse during initial PCAP examination.

---

# 7. Activate a NetworkManager Connection Profile

## Command

`sudo nmcli connection up DFIR-LAB-KALI`

## Purpose

Activates the specified NetworkManager connection profile.

## Command Breakdown

| Term | Meaning |
|------|---------|
| `connection` | NetworkManager connection profile operation. |
| `up` | Activates the selected connection. |
| `DFIR-LAB-KALI` | Connection profile to activate. |

## Investigation Relevance

Activating the profile applied the configured static IPv4 settings to `eth0`.

---

# 8. Display IPv4 Information for a Specific Interface

## Command

`ip -4 addr show eth0`

## Purpose

Displays IPv4 address information for the `eth0` interface.

## Command Breakdown

| Term | Meaning |
|------|---------|
| `ip` | Linux networking utility. |
| `-4` | Limits displayed information to IPv4. |
| `addr` | Address operation. |
| `show` | Displays the requested information. |
| `eth0` | Network interface being examined. |

## Observed Lab Address

`inet 10.10.50.10/24 brd 10.10.50.255 scope global noprefixroute eth0`

## Investigation Relevance

The command verified the network identity assigned to the Kali analysis node.

---

# 9. Test External IPv4 Reachability

## Command

`ping -c 3 8.8.8.8`

## Purpose

Attempts to send three ICMP Echo Request packets to the IPv4 address `8.8.8.8`.

The command was used as a simple external IPv4 reachability test.

## Command Breakdown

| Term | Meaning |
|------|---------|
| `ping` | Utility used to test IP reachability using ICMP Echo Request and Echo Reply messages. |
| `-c` | Specifies the number of Echo Requests to send. |
| `3` | Sends three Echo Requests. |
| `8.8.8.8` | Destination IPv4 address used for the connectivity test. |

## Observed Result

`ping: connect: Network is unreachable`

## Interpretation

The operating system could not identify a valid IPv4 route to the destination.

This result was consistent with the absence of an IPv4 default route in the routing table.

## Important Limitation

A failed `ping` test alone does not prove complete network isolation.

ICMP traffic may be filtered even when other network protocols remain available.

In this laboratory, the result was interpreted together with the routing table and VirtualBox internal network configuration.

## Investigation Relevance

The test provided an additional validation point supporting the documented laboratory network configuration.

---

# 10. Execute Multiple Commands Sequentially

## Command

`ip -4 addr show eth0 && ip route`

## Purpose

Executes the IPv4 interface verification command followed by the routing table command.

## Command Breakdown

| Term | Meaning |
|------|---------|
| `ip -4 addr show eth0` | Displays IPv4 information for `eth0`. |
| `&&` | Executes the command on the right only if the command on the left completes successfully. |
| `ip route` | Displays the IPv4 routing table. |

## Investigation Relevance

The combined command was used to display the laboratory interface configuration and routing state together for documentation and screenshot capture.

---

# Summary

The commands documented in this reference were used to:

1. Identify the Kali network interface.
2. Examine the initial IP configuration.
3. Examine the IPv4 routing table.
4. Determine NetworkManager device state.
5. Create a persistent laboratory connection profile.
6. Assign a static IPv4 address.
7. Prevent the laboratory profile from providing a default IPv4 route.
8. Disable IPv6 on the designated laboratory profile.
9. Activate the configured network connection.
10. Verify the resulting IPv4 configuration and routing state.
11. Test external IPv4 reachability.
12. Record the validated network state for the investigation documentation.