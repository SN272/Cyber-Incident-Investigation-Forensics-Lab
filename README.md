# Cyber Incident Investigation & Forensics Lab

## Overview

This project documents a simulated Digital Forensics and Incident Response (DFIR) investigation conducted within a controlled virtual environment.

The project demonstrates a structured forensic workflow involving network evidence acquisition and analysis, evidence integrity verification, evidence handling, and investigation documentation.

The investigation was designed around a simulated workstation network-activity scenario and focused on generating and analysing controlled network forensic artifacts rather than interacting with real malicious infrastructure.

> **Project Status: Completed**

---

## Investigation Scenario

A workstation within a fictional organisational environment was involved in controlled network activity within an isolated forensic laboratory.

The investigation was designed to examine network communication generated between the laboratory systems and demonstrate how packet-capture evidence can be acquired, preserved, verified, and analysed.

Two controlled network events were captured:

- Baseline ICMP communication.
- A controlled HTTP file-download activity.

All activity was performed within the isolated `DFIR-LAB` virtual network.

The project does not involve exploitation of unauthorised systems or interaction with active malicious infrastructure.

---

## Investigation Objectives

The project objectives were to:

- Establish a controlled DFIR laboratory environment.
- Define and document the investigation scenario.
- Acquire controlled network evidence.
- Analyse ICMP and HTTP traffic using Wireshark.
- Verify evidence integrity using SHA-256.
- Maintain evidence metadata and chain-of-custody documentation.
- Document evidence-based findings and limitations.

---

## Lab Architecture

The investigation used Oracle VirtualBox with an isolated internal network named `DFIR-LAB`.

| System | Role | IPv4 Address |
|---|---|---|
| Kali Linux | Analysis / network node | `10.10.50.10` |
| Windows workstation | Simulated workstation | `10.10.50.20` |

The laboratory network used:

- Network: `10.10.50.0/24`
- No IPv4 default gateway
- No external routing through the lab network

Detailed configuration is documented in [`lab-architecture/lab_architecture.md`](lab-architecture/lab_architecture.md).

---

## Network Evidence Analysis

### Baseline ICMP Traffic — NET-001

A baseline network capture was acquired to establish controlled ICMP communication within the isolated laboratory.

The capture was analysed using Wireshark to verify the expected communication between the laboratory systems.

![Baseline ICMP Analysis](lab-architecture/screenshots/03_baseline_icmp_analysis.png)

**Figure 1. Baseline ICMP traffic analysis.**

The evidence integrity was verified using SHA-256.

---

### HTTP File Download — NET-002

A controlled HTTP file transfer was performed within the isolated laboratory to generate a network forensic artifact.

The resulting PCAP was analysed using Wireshark to examine:

- HTTP request and response traffic
- Source and destination hosts
- Transfer timing
- The transferred object
- Reconstructed HTTP communication

![HTTP File Download Analysis](lab-architecture/screenshots/04_http_file_download_analysis.png)

**Figure 2. Controlled HTTP file-transfer analysis.**

The evidence integrity was verified using SHA-256.

---

## Evidence Integrity

SHA-256 was used to verify the integrity of the acquired network evidence.

The documented evidence items are:

- `NET-001` — Baseline Network Connectivity Capture
- `NET-002` — HTTP File Download Simulation

Evidence identifiers, filenames, hashes, and acquisition details are documented in the evidence manifest and metadata files.

Original evidence is kept separate from working documentation where applicable.

---

## Forensic Workflow

The completed investigation followed this workflow:

Case Definition and Scoping
            ↓
Evidence Identification
            ↓
Evidence Acquisition
            ↓
SHA-256 Integrity Verification
            ↓
Network Traffic Analysis
            ↓
Evidence Documentation
            ↓
Evidence-Based Findings

---

## Completed Work

- [x] Defined the simulated investigation scenario.
- [x] Defined the investigation scope and questions.
- [x] Established the DFIR laboratory environment.
- [x] Configured and validated the isolated `DFIR-LAB` network.
- [x] Acquired baseline network evidence (`NET-001`).
- [x] Acquired controlled HTTP evidence (`NET-002`).
- [x] Analysed ICMP traffic using Wireshark.
- [x] Analysed HTTP request and response traffic.
- [x] Reconstructed the controlled HTTP file transfer.
- [x] Verified evidence integrity using SHA-256.
- [x] Documented evidence metadata and chain of custody.
- [x] Documented the investigation findings and limitations.

---

## Evidence

The completed investigation contains two documented network evidence items:

| Evidence ID | Evidence |
|---|---|
| `NET-001` | Baseline Network Connectivity Capture |
| `NET-002` | HTTP File Download Simulation |

Evidence details are maintained in:

- `evidence/working-copies/evidence_manifest.csv`
- `evidence/working-copies/evidence_metadata.md`

---

## Repository Structure

Cyber-Incident-Investigation-Forensics/
│
├── README.md
├── .gitignore
│
├── case-files/
│   ├── case_background.md
│   ├── incident_scope.md
│   └── investigation_questions.md
│
├── chain-of-custody/
│   └── chain_of_custody.md
│
├── evidence/
│   └── working-copies/
│       ├── evidence_manifest.csv
│       ├── evidence_metadata.md
│       └── README.md
│
└── lab-architecture/
    ├── lab_architecture.md
    ├── lab_command_reference.md
    ├── network_validation.md
    └── screenshots/
        ├── 03_baseline_icmp_analysis.png
        ├── 04_http_file_download_analysis.png
        └── kali_network_configuration.png

---

## Tools and Technologies

### Network Forensics

- Wireshark
- Linux networking utilities

### Laboratory Environment

- Kali Linux
- Windows 10
- Oracle VirtualBox
- NetworkManager / `nmcli`

### Evidence Handling

- SHA-256
- Markdown
- CSV
- Chain-of-custody documentation

---

## Investigation Documentation

The repository contains documentation covering:

- [Case Background](case-files/case_background.md)
- [Incident Investigation Scope](case-files/incident_scope.md)
- [Investigation Questions](case-files/investigation_questions.md)
- [Evidence Handling](evidence/working-copies/README.md)
- [Evidence Metadata](evidence/working-copies/evidence_metadata.md)
- [Evidence Manifest](evidence/working-copies/evidence_manifest.csv)
- [Chain of Custody](chain-of-custody/chain_of_custody.md)
- [DFIR Lab Architecture](lab-architecture/lab_architecture.md)
- [Network Validation](lab-architecture/network_validation.md)
- [Lab Command Reference](lab-architecture/lab_command_reference.md)

---

## Findings

The available network evidence demonstrates:

- Successful baseline ICMP communication.
- Controlled HTTP communication.
- HTTP GET request and response activity.
- Controlled file-transfer activity.
- Recovery of the transferred object from the HTTP capture.

The investigation conclusions are limited to observations directly supported by the available evidence.

No unsupported claims are made regarding memory, disk, malware, persistence, command-and-control, or data exfiltration because those evidence sources were not acquired as part of the final project scope.

---

## Ethical and Safety Statement

This repository documents a controlled cybersecurity laboratory created for academic and portfolio purposes.

All simulated activity was conducted within an isolated virtual environment.

The project does not target unauthorised systems or interact with active malicious infrastructure.

---

## Scope and Limitations

This project represents a controlled academic DFIR investigation rather than a legal or enterprise forensic examination.

The final scope is limited to the network evidence successfully acquired and analysed.

The project does not include:

- Live memory acquisition or analysis
- Full disk imaging
- Filesystem forensic examination
- Malware execution or analysis
- Threat-actor attribution
- Comprehensive MITRE ATT&CK mapping
- Enterprise-scale incident response

Where evidence was unavailable, no unsupported conclusions were drawn.

---

## Author

**Nandini Sharma**

B.Tech Computer Science and Engineering  
Cyber Security

---

## Project Status

**Completed**

The project has reached its final documented scope. The acquired network evidence, forensic observations, integrity records, and investigation documentation have been preserved in the repository.

---

## Final Project Summary

This project demonstrates a controlled DFIR workflow for network evidence acquisition, preservation, integrity verification, and packet-level analysis.

The investigation successfully established an isolated forensic laboratory, generated controlled network evidence, analysed the resulting PCAP files using Wireshark, and documented the evidence-handling process.

The final project scope is intentionally limited to the evidence and findings that were successfully obtained during the investigation.

**Status: Completed**
