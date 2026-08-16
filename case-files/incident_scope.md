# Incident Investigation Scope

## Case ID

DFIR-2026-001

## Case Type

Simulated DFIR Investigation

## Investigation Scope

This project focuses on a controlled Digital Forensics and Incident Response (DFIR) investigation involving simulated workstation network activity.

The completed investigation focuses on network evidence acquisition, packet analysis, evidence integrity verification, and forensic documentation within an isolated laboratory environment.

The investigation scope is limited to the evidence successfully acquired and analysed during the project.

## In-Scope Analysis

### Network Forensics

- Packet capture analysis.
- Network protocol analysis.
- Identification of source and destination hosts.
- ICMP traffic analysis.
- HTTP request and response analysis.
- Controlled HTTP file-transfer analysis.
- Examination of packet timestamps and communication details.
- Recovery of the transferred HTTP object.
- Verification of network evidence integrity using SHA-256.

### Evidence Handling

- Evidence identification and organisation.
- Evidence manifest maintenance.
- Evidence metadata documentation.
- Cryptographic integrity verification.
- Chain-of-custody documentation.
- Preservation of documented evidence information.

### Investigation Documentation

- Case definition and scoping.
- Investigation question definition.
- Laboratory architecture documentation.
- Network validation documentation.
- Evidence handling documentation.
- Forensic observations and findings.
- Documentation of investigative limitations.

## Out-of-Scope Activities

The following activities were not included in the final completed scope:

- Live volatile memory acquisition and analysis.
- Full physical disk imaging.
- Filesystem forensic examination.
- Windows memory analysis using Volatility.
- Malware execution or dynamic malware analysis.
- Threat-actor attribution.
- Active command-and-control infrastructure investigation.
- Data-exfiltration investigation.
- Comprehensive MITRE ATT&CK mapping.
- Enterprise-scale incident response activities.

## Evidence Handling Principles

Evidence identifiers, filenames, cryptographic hashes, and relevant acquisition information are documented in the evidence repository.

SHA-256 was used to verify the integrity of the acquired network evidence.

Evidence documentation was maintained separately from the forensic analysis workflow.

## Investigative Limitations

The investigation conclusions are limited to the network artifacts successfully acquired and analysed within the controlled laboratory environment.

The available evidence does not support conclusions regarding activities for which corresponding forensic artifacts were not acquired.

The absence of a particular artifact is not interpreted as proof that the associated activity did not occur.

The project is a controlled academic DFIR exercise and should not be interpreted as a complete legal or enterprise forensic examination.

## Final Outcome

The completed project demonstrates a targeted network-forensics workflow covering:

1. Case definition and investigation scoping.
2. Evidence identification and acquisition.
3. Evidence integrity verification.
4. Network traffic analysis.
5. HTTP object reconstruction.
6. Evidence metadata and chain-of-custody documentation.
7. Evidence-based observation and conclusion development.

The final findings are limited to observable information supported by the available network evidence.