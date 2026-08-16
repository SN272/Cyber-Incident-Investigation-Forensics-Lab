# DFIR Lab Architecture

## Case ID

DFIR-2026-001

## Purpose

A controlled virtual laboratory environment was established to generate and examine forensic network evidence associated with this simulated Digital Forensics and Incident Response investigation.

The lab was designed to isolate the simulated investigation traffic from external network infrastructure while providing defined system roles and static network addressing.

The completed project focuses on controlled network evidence generation and analysis.

## Architecture Overview

The investigation lab uses Oracle VirtualBox and an isolated internal network named `DFIR-LAB`.

The laboratory systems used for the completed investigation were:

| System | Role | IPv4 Address |
| ------------------- | -------------------------------- | ------------- |
| Kali Linux | Analysis and controlled network node | `10.10.50.10` |
| Windows workstation | Simulated workstation and network endpoint | `10.10.50.20` |

Both systems communicated within the isolated laboratory network.

The Kali Linux system was used for network configuration, analysis, and controlled network activity.

The Windows workstation was used as the simulated workstation endpoint during controlled network evidence generation.

## Network Design

The virtual investigation network used the following IPv4 configuration:

* Network: `10.10.50.0/24`
* VirtualBox network type: Internal Network
* VirtualBox network name: `DFIR-LAB`
* IPv4 default gateway: Not configured
* External routing: Not configured
* Kali Linux: `10.10.50.10/24`
* Windows workstation: `10.10.50.20/24`

Both systems communicated directly within the same IPv4 subnet.

No IPv4 default route was configured for the isolated investigation network.

This design reduced the possibility of controlled investigation traffic being routed to external network infrastructure.

## Kali Linux Analysis Node

### System Role

The Kali Linux virtual machine served as the primary analysis and controlled network node for the investigation.

It was used to:

* Configure and validate the isolated investigation network.
* Generate or receive controlled network activity.
* Capture network traffic using Wireshark.
* Analyse the resulting packet captures.

The system was not used to exploit unauthorised external systems as part of the project.

### Network Configuration

The Kali network interface used for the lab was:

* Interface: `eth0`
* IPv4 address: `10.10.50.10/24`
* IPv4 gateway: None
* IPv4 default route: None

### Routing Verification

The configured IPv4 routing table contained the directly connected laboratory subnet:

`10.10.50.0/24 dev eth0`

No IPv4 default route was present through the laboratory interface.

An external IPv4 connectivity test to `8.8.8.8` returned `Network is unreachable`, consistent with the absence of an IPv4 default route.

## Windows Workstation

### System Role

The Windows virtual machine served as the simulated workstation endpoint for controlled network evidence generation.

The system participated in the isolated `DFIR-LAB` network and was used during the generation of the documented network captures.

The completed evidence includes:

* Baseline ICMP communication.
* Controlled HTTP file-transfer activity.

The Windows system was not used as the source of a completed volatile-memory or full-disk forensic acquisition within the final project scope.

### Network Configuration

The Windows workstation used:

* IPv4 address: `10.10.50.20/24`
* IPv4 gateway: None
* VirtualBox network: `DFIR-LAB`

## Evidence Generation and Analysis

The laboratory architecture supported the generation and analysis of controlled network evidence.

The completed workflow was:

1. Configure the isolated laboratory network.
2. Assign static IPv4 addresses to the laboratory systems.
3. Validate connectivity between the systems.
4. Capture baseline ICMP traffic.
5. Capture controlled HTTP file-transfer traffic.
6. Preserve the resulting PCAP evidence.
7. Calculate and verify SHA-256 hashes.
8. Analyse the captures using Wireshark.
9. Document the resulting observations.

The corresponding evidence items are:

* `NET-001` — Baseline Network Connectivity Capture.
* `NET-002` — HTTP File Download Simulation.

## Network Isolation

The investigation network was configured without an IPv4 default gateway.

The isolated design prevented the laboratory network from using the configured interface to reach external IPv4 networks.

This was verified through network configuration and connectivity testing.

The resulting network configuration is documented in:

[`network_validation.md`](network_validation.md)

## Resource Constraints

The laboratory was operated within the available host-system resources.

The investigation used staged network evidence generation and analysis rather than requiring multiple resource-intensive virtual machines to operate simultaneously.

The final project scope was intentionally limited to the network evidence that could be reliably generated, acquired, preserved, and analysed within the laboratory environment.

## Current Lab Status

The laboratory environment was successfully established for the completed investigation scope.

The following components were successfully configured and validated:

* Kali Linux analysis node.
* Windows workstation endpoint.
* Isolated `DFIR-LAB` VirtualBox internal network.
* Static IPv4 addressing.
* Bidirectional network connectivity.
* Network packet capture and analysis workflow.

The resulting network evidence was acquired and documented as `NET-001` and `NET-002`.

## Final Scope

The laboratory architecture supported the completed network-focused DFIR investigation.

The project does not claim completion of live memory acquisition, full disk imaging, or multi-source memory/disk correlation.

The final documented architecture and evidence are limited to the controlled network investigation successfully performed.