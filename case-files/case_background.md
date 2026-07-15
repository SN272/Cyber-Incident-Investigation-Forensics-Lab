# Case Background

## Case ID

DFIR-2026-001

## Incident Title

Suspected Workstation Compromise and Command-and-Control Activity

## Case Type

Simulated Digital Forensics and Incident Response (DFIR) Investigation

## Project Disclaimer

This project is a simulated Digital Forensics and Incident Response (DFIR) investigation developed for academic and cybersecurity portfolio purposes.

The investigation uses publicly available forensic datasets and controlled evidence sources. The organisational context and incident scenario described in this project are fictional unless explicitly stated otherwise.

No active malicious infrastructure is intentionally contacted during the investigation. All forensic analysis is performed on acquired evidence using passive and offline investigation techniques wherever applicable.

## Background

A simulated Security Operations Center (SOC) monitoring scenario identified unusual outbound network activity originating from a Windows workstation within a fictional corporate environment.

The affected workstation was observed communicating with external network infrastructure at repeated intervals. Initial observations also indicated potentially suspicious DNS requests and HTTP traffic following user activity involving an externally obtained file.

According to the simulated incident context, the user reported that a document briefly opened and closed unexpectedly. No additional visible symptoms were reported.

Based on the observed activity, the workstation was considered potentially compromised and selected for forensic examination.

The purpose of this project is to investigate the available forensic evidence and determine whether the network, volatile memory, and filesystem artifacts support the suspected compromise scenario.

## Available Evidence

The investigation may use the following publicly available or controlled forensic evidence:

1. Network packet capture (PCAP) associated with suspicious workstation activity.
2. Volatile memory image acquired from a Windows system.
3. Disk image or filesystem artifacts relevant to the investigation.
4. System and user activity artifacts.
5. Publicly available threat intelligence sources for Indicator of Compromise (IOC) enrichment.

The exact evidence sources and cryptographic hashes will be documented in the evidence manifest during the evidence acquisition phase.

## Investigation Objectives

The investigation aims to determine:

* Whether the examined workstation contains evidence of compromise.
* The possible initial access or infection vector.
* Whether suspicious network communications are present.
* Whether malicious or anomalous processes can be identified in volatile memory.
* Whether suspicious files, scripts, or execution artifacts exist.
* Whether persistence mechanisms are present.
* Whether command-and-control behaviour can be identified.
* Whether evidence suggests attempted or successful data exfiltration.
* Which Indicators of Compromise can be extracted from the available evidence.
* Whether network, memory, and filesystem artifacts can be correlated.
* Which MITRE ATT&CK techniques are supported by the forensic findings.

## Investigation Methodology

The investigation follows a structured digital forensic workflow consisting of:

1. Case definition and investigation scoping.
2. Evidence identification and acquisition.
3. Evidence integrity verification using cryptographic hashing.
4. Network traffic analysis.
5. Volatile memory forensic analysis.
6. Disk and filesystem forensic analysis.
7. Indicator of Compromise extraction.
8. Open-Source Intelligence (OSINT) and threat intelligence enrichment.
9. Cross-source forensic artifact correlation.
10. Incident timeline reconstruction.
11. MITRE ATT&CK technique mapping.
12. Technical incident reporting and conclusion development.

## Planned Tools

The following tools may be used during the investigation depending on evidence compatibility and investigative requirements:

* Wireshark
* Volatility 3
* Volatility Workbench
* Autopsy
* FTK Imager
* Python
* Public OSINT and threat intelligence resources

Additional forensic utilities may be introduced where technically justified and will be documented in the relevant analysis notes.

## Investigation Status

Simulated Case - Evidence Acquisition and Forensic Analysis Pending
