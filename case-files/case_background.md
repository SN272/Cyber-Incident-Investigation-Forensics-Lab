# Case Background

## Case ID

DFIR-2026-001

## Incident Title

Simulated Workstation Network Activity Investigation

## Case Type

Simulated Digital Forensics and Incident Response (DFIR) Investigation

## Project Disclaimer

This project is a simulated DFIR investigation developed for academic and cybersecurity portfolio purposes.

The organisational context and incident scenario are fictional.

All evidence was generated or collected within a controlled laboratory environment. No active malicious infrastructure was intentionally contacted.

The investigation focuses on controlled network evidence, and conclusions are limited to the evidence successfully acquired and analysed.

## Background

A simulated Security Operations Center (SOC) scenario identified network activity originating from a workstation within a fictional organisational environment.

The investigation demonstrates how network evidence can be acquired, preserved, verified, and analysed during a controlled forensic investigation.

The laboratory generated controlled network traffic including:

- Baseline ICMP communication.
- An HTTP file-transfer event.

The purpose of the project is to demonstrate a structured network-forensics workflow and establish observable findings from the available evidence.

## Available Evidence

The completed investigation includes:

1. Baseline network packet capture (`NET-001`).
2. Controlled HTTP network packet capture (`NET-002`).
3. SHA-256 integrity records.
4. Evidence metadata and chain-of-custody documentation.

Evidence identifiers, filenames, metadata, and cryptographic hashes are documented in the evidence repository and manifest.

## Investigation Objectives

The investigation aimed to:

- Establish a controlled forensic laboratory environment.
- Define and document the investigation scenario.
- Acquire controlled network evidence.
- Analyse baseline ICMP communication.
- Analyse controlled HTTP traffic.
- Reconstruct the controlled HTTP file transfer.
- Verify evidence integrity using SHA-256.
- Maintain evidence metadata and chain-of-custody documentation.
- Document evidence-based findings without unsupported conclusions.

## Investigation Methodology

The investigation followed a structured workflow:

1. Case definition and investigation scoping.
2. Evidence identification.
3. Evidence acquisition.
4. Evidence integrity verification using SHA-256.
5. Network traffic analysis.
6. HTTP object reconstruction.
7. Evidence metadata documentation.
8. Chain-of-custody documentation.
9. Evidence-based finding development.
10. Final investigation documentation.

The investigation was limited to evidence that could be reliably acquired and analysed within the controlled laboratory environment.

## Tools Used

The completed investigation used:

- Wireshark
- Kali Linux networking utilities
- SHA-256 hashing utilities
- Oracle VirtualBox
- NetworkManager / `nmcli`
- Markdown and CSV documentation

## Investigation Status

**Completed — Final documented scope**

The investigation has reached its final documented scope.

The completed work includes controlled network evidence acquisition and analysis, evidence integrity verification, evidence metadata documentation, and chain-of-custody documentation.

No unsupported conclusions are made regarding forensic evidence that was not acquired or analysed.