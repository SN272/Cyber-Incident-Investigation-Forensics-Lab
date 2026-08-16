# Isolated Network Validation

## Case ID

DFIR-2026-001

## Validation Objective

The objective of this validation was to confirm that the Kali Linux analysis node was connected to the designated `DFIR-LAB` VirtualBox internal network with a static IPv4 address and without a configured IPv4 default route.

## Interface Validation

Command executed:

`ip -4 addr show eth0`

Observed IPv4 configuration:

* Interface: `eth0`
* Interface state: `UP`
* IPv4 address: `10.10.50.10/24`
* Broadcast address: `10.10.50.255`

The observed address matched the addressing scheme used for the Kali Linux analysis node.

## Routing Validation

Command executed:

`ip route`

Observed route:

`10.10.50.0/24 dev eth0 proto kernel scope link src 10.10.50.10 metric 100`

No IPv4 default route was present.

The routing table therefore provided a directly connected route to the `10.10.50.0/24` laboratory subnet without a configured default IPv4 path to external networks.

## External IPv4 Connectivity Test

Command executed:

`ping -c 3 8.8.8.8`

Observed result:

`ping: connect: Network is unreachable`

The test result was consistent with the absence of an IPv4 default route through the isolated laboratory interface.

## Laboratory Connectivity Validation

The Kali Linux node was subsequently validated against the Windows workstation configured within the isolated laboratory network.

The Windows workstation used the address:

`10.10.50.20/24`

Connectivity between the two laboratory systems was successfully established.

This validated the intended direct communication path within the `10.10.50.0/24` subnet.

## Validation Result

**PASS**

The Kali Linux analysis node had the expected static IPv4 identity and no configured IPv4 default route through the `DFIR-LAB` interface.

The isolated network successfully supported direct communication between the laboratory systems and was subsequently used for controlled network evidence generation.

## Investigative Relevance

Documenting the network configuration before evidence generation establishes the known laboratory topology and addressing scheme.

This information supports forensic interpretation of source and destination IP addresses observed in the network packet captures.

The validated network configuration provides context for the evidence items:

* `NET-001` — Baseline Network Connectivity Capture.
* `NET-002` — HTTP File Download Simulation.