# Incident Investigation Scope

## Case ID

DFIR-2026-001

## Case Type

Simulated DFIR Investigation

## Investigation Scope

This project focuses on the forensic examination of a suspected compromised Windows workstation using publicly available or controlled forensic evidence.

The investigation will examine network traffic, volatile memory, and disk or filesystem artifacts to identify potential malicious activity and reconstruct the sequence of events associated with the simulated incident.

The project is intended to demonstrate a structured Digital Forensics and Incident Response (DFIR) investigation methodology through evidence preservation, technical artifact analysis, and cross-source forensic correlation.

## In-Scope Analysis

The following investigative activities are within the scope of this project:

### Network Forensics

* Packet capture analysis.
* Network protocol analysis.
* Identification of internal and external hosts.
* Suspicious IP address and domain identification.
* DNS request and response analysis.
* HTTP and other relevant application-layer traffic analysis.
* Network flow and communication pattern analysis.
* Periodic communication and potential beaconing identification.
* Command-and-control traffic investigation.
* Investigation of possible data exfiltration indicators.

### Memory Forensics

* Operating system and memory image identification.
* Process enumeration and analysis.
* Process parent-child relationship analysis.
* Process command-line examination.
* Network connection analysis from volatile memory.
* Suspicious or anomalous process identification.
* Hidden or terminated process investigation where supported by the evidence.
* Process injection investigation where supported by the evidence.
* Loaded module and DLL analysis where relevant.
* Extraction of relevant memory artifacts.

### Disk and Filesystem Forensics

* Filesystem examination.
* File metadata analysis.
* Suspicious executable, script, archive, and document identification.
* Downloaded file investigation.
* Deleted file analysis where recoverable.
* User activity artifact examination.
* Persistence mechanism investigation.
* Relevant Windows artifact analysis where available.
* File hash extraction and comparison.

### Threat Intelligence and OSINT

* IP address enrichment.
* Domain and URL investigation.
* File hash reputation analysis.
* Indicator of Compromise validation.
* Correlation with publicly documented malicious infrastructure or campaigns where supported by available intelligence.

### Incident Correlation

* Cross-correlation of network, memory, and filesystem artifacts.
* Timestamp normalisation and event sequencing.
* Master incident timeline development.
* Attack sequence reconstruction.
* MITRE ATT&CK technique mapping.
* Development of evidence-supported incident conclusions.

## Out-of-Scope Activities

The following activities are outside the scope of this investigation:

* Active exploitation of external systems.
* Deployment of malware against live systems.
* Unauthorised vulnerability scanning.
* Unauthorised network reconnaissance.
* Interaction with active command-and-control infrastructure.
* Execution of suspicious samples on the host operating system.
* Modification of original forensic evidence.
* Attribution of activity to a specific threat actor without sufficient supporting evidence.

## Evidence Handling Principles

Original forensic evidence will be preserved in its acquired state wherever possible.

Cryptographic hashes will be calculated and documented before analysis to establish evidence integrity.

Analysis will be conducted using forensic images, mounted evidence, or designated working copies depending on the evidence format and tool requirements.

Any extracted artifacts created during the investigation will be stored separately from the original evidence.

The evidence source, acquisition details, cryptographic hashes, and relevant handling information will be documented in an evidence manifest.

## Investigative Limitations

The investigation conclusions will be limited to the artifacts available within the selected forensic datasets.

The absence of an artifact will not automatically be interpreted as proof that an activity did not occur.

Where evidence is incomplete or multiple interpretations are technically possible, the uncertainty and investigative limitations will be documented.

## Expected Outcome

The investigation is expected to produce an evidence-supported technical assessment of the suspected compromise.

The final investigation report will document identified forensic artifacts, Indicators of Compromise, correlated events, the reconstructed attack sequence, relevant MITRE ATT&CK techniques, investigative limitations, and the most likely incident conclusion.
