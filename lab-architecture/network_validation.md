# Isolated Network Validation

## Case ID

DFIR-2026-001

## Validation Objective

The objective of this validation was to confirm that the Kali Linux simulation node was connected to the designated `DFIR-LAB` VirtualBox internal network with a static IPv4 address and without a configured IPv4 default route.

## Interface Validation

Command executed:

`ip -4 addr show eth0`

Observed IPv4 configuration:

* Interface: `eth0`
* Interface state: `UP`
* IPv4 address: `10.10.50.10/24`
* Broadcast address: `10.10.50.255`

The observed address matched the planned addressing scheme for the Kali simulation node.

## Routing Validation

Command executed:

`ip route`

Observed route:

`10.10.50.0/24 dev eth0 proto kernel scope link src 10.10.50.10 metric 100`

No IPv4 default route was present.

The routing table therefore provided a directly connected route to the `10.10.50.0/24` lab subnet without a configured default IPv4 path to external networks.

## External IPv4 Connectivity Test

Command executed:

`ping -c 3 8.8.8.8`

Observed result:

`ping: connect: Network is unreachable`

The test result was consistent with the absence of an IPv4 default route.

## Validation Result

**PASS**

At the time of validation, the Kali Linux simulation node had the expected static IPv4 identity and no configured IPv4 default route through the `DFIR-LAB` interface.

The node was ready for later direct communication with the planned Windows workstation on the `10.10.50.0/24` subnet.

## Investigative Relevance

Documenting the network configuration before evidence generation establishes the known lab topology and addressing scheme.

This information will later support forensic interpretation of source and destination IP addresses observed in packet captures and other network-related artifacts.
