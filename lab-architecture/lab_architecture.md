# DFIR Lab Architecture

## Case ID

DFIR-2026-001

## Purpose

A controlled virtual lab environment is used to generate and examine the forensic artifacts associated with this simulated Digital Forensics and Incident Response investigation.

The lab is designed to produce correlated network, volatile memory, and filesystem evidence from a common simulated incident scenario.

The environment separates simulated incident traffic from external network infrastructure and provides known system roles and addressing for later forensic correlation.

## Architecture Overview

The investigation lab uses Oracle VirtualBox to provide an isolated virtual network named `DFIR-LAB`.

The planned lab contains two virtual systems:

| System              | Role                                 | IPv4 Address  |
| ------------------- | ------------------------------------ | ------------- |
| Kali Linux          | Controlled simulation node           | `10.10.50.10` |
| Windows workstation | Simulated victim and evidence source | `10.10.50.20` |

The Kali Linux system is used as a controlled endpoint for generating benign network activity associated with the simulated incident.

The Windows virtual machine will act as the simulated affected workstation and primary evidence source.

Forensic analysis will be performed separately from the simulated incident environment.

## Network Design

The virtual incident network uses the following IPv4 configuration:

* Network: `10.10.50.0/24`
* VirtualBox network type: Internal Network
* VirtualBox network name: `DFIR-LAB`
* IPv4 default gateway: Not configured
* External routing: Not configured
* Kali simulation node: `10.10.50.10`
* Planned Windows workstation: `10.10.50.20`

Both virtual systems are intended to communicate directly within the same IPv4 subnet.

A default IPv4 route is not configured for the isolated incident network.

This design reduces the possibility of controlled simulation traffic being routed to external network infrastructure.

## Kali Linux Simulation Node

### System Role

The Kali Linux virtual machine is designated as the controlled simulation node.

Its purpose is to provide lab-controlled services and receive benign simulated incident traffic from the Windows workstation.

The system is not used to exploit unauthorised external systems as part of this project.

### Network Configuration

The Kali network interface used for the lab is:

* Interface: `eth0`
* NetworkManager profile: `DFIR-LAB-KALI`
* IPv4 address: `10.10.50.10/24`
* IPv4 gateway: None
* IPv4 default route: None
* IPv6 on lab profile: Disabled

### Routing Verification

The configured IPv4 routing table contained only the directly connected lab subnet:

`10.10.50.0/24 dev eth0`

No IPv4 default route was present through the lab interface.

An external IPv4 connectivity test to `8.8.8.8` returned `Network is unreachable`, consistent with the absence of an IPv4 default route.

## Windows Workstation

### Planned System Role

The Windows virtual machine will represent the suspected compromised workstation in the simulated incident.

The system will be used to generate controlled forensic artifacts associated with:

* User download activity.
* Script and command-line execution.
* Parent-child process relationships.
* Repeated network communication.
* Controlled persistence-like artifacts.
* Test-data staging and transfer.

All generated activity will remain within the controlled lab scenario.

### Planned Network Configuration

The Windows workstation is assigned the following planned network identity:

* IPv4 address: `10.10.50.20/24`
* IPv4 gateway: None
* VirtualBox network: `DFIR-LAB`

The Windows system has not yet been introduced into the lab at the current investigation stage.

## Evidence Correlation Objective

The architecture is designed to support correlation between multiple forensic evidence sources.

The intended correlation workflow is:

1. Identify suspicious communication in captured network traffic.
2. Determine the source and destination systems associated with the communication.
3. Identify the process associated with the network activity in volatile memory.
4. Examine process parent-child relationships and command-line artifacts.
5. Associate suspicious execution with files or artifacts identified in filesystem evidence.
6. Compare timestamps across network, memory, and filesystem sources.
7. Reconstruct the simulated incident sequence.
8. Map evidence-supported activity to relevant MITRE ATT&CK techniques.

## Resource Constraints

The forensic lab is hosted on a Windows 11 system with 8 GB of physical memory.

To reduce resource contention, virtual machines and forensic analysis applications will not necessarily operate simultaneously.

The investigation workflow uses staged evidence generation, acquisition, and analysis.

Large full-disk forensic acquisitions may also be limited by available storage capacity. Where targeted or logical acquisition is used instead of a full physical disk image, the acquisition scope and resulting forensic limitations will be explicitly documented.

## Current Lab Status

The Kali Linux simulation node has been configured on the isolated `DFIR-LAB` VirtualBox internal network.

The Kali node has been assigned the static IPv4 address `10.10.50.10/24`.

The lab interface has no configured IPv4 default gateway or IPv4 default route.

External IPv4 connectivity through the lab interface was tested and was not available.

The Windows workstation has not yet been introduced into the virtual incident network.

## Next Phase

The next phase of the project will introduce the Windows workstation, configure its isolated network identity, and validate controlled communication between the two lab nodes before incident evidence generation begins.
