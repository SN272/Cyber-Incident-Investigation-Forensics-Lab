# Evidence Handling and Chain of Custody Log

## Case ID

DFIR-2026-001

## Case Type

Simulated DFIR Investigation

## Purpose

This document records the handling of forensic evidence used during the simulated investigation.

The project is an academic and cybersecurity portfolio exercise rather than a legal investigation. Therefore, this document demonstrates chain-of-custody and evidence handling principles within a controlled forensic lab environment.

## Evidence Handling Principles

The following principles are applied during the investigation:

* Each acquired evidence item is assigned a unique evidence identifier.
* Evidence acquisition details are documented.
* Cryptographic hashes are calculated after acquisition.
* Original evidence is preserved wherever technically possible.
* Working copies are created for analysis where required.
* Extracted artifacts are stored separately from original evidence.
* Relevant evidence handling actions are recorded in the log below.
* Evidence integrity is verified before forensic analysis.

## Evidence Identifier Format

Evidence identifiers are assigned according to the type of forensic evidence collected.

| Prefix | Evidence Type |
|---------|---------------|
| NET | Network Capture |
| MEM | Memory Acquisition |
| DISK | Disk Image |
| LOG | System/Event Logs |
| ART | Extracted Artifacts |

Examples:

- `NET-001`
- `MEM-001`
- `DISK-001`
- `LOG-001`

Evidence identifiers are assigned sequentially within each evidence category.

# Chain of Custody

## Evidence Log

| Evidence ID | Evidence Description | Date & Time (Local) | Collected By | Acquisition Method | SHA-256 Hash | Storage Location | Status |
|-------------|----------------------|---------------------|--------------|--------------------|--------------|------------------|--------|
| NET-001 | Baseline network connectivity capture between WS-FIN-01 and DFIR-ANALYST | 2026-08-03 18:28 | Investigator | Wireshark Packet Capture | a114faf5e6b2f98fa2cb441a45f15a5b7a792279071da33e0c546e742c9536e1 | ~/DFIR-Lab/evidence/original/NET-001_baseline_connectivity.pcapng | Original Evidence Preserved |
| NET-002 | HTTP file download simulation between WS-FIN-01 and DFIR-ANALYST | 2026-08-03 18:3X IST | Investigator | Wireshark Packet Capture | bf81896d1c542e4115dadf5ba7fed70d0b1f103846c9945b1916f061cd8b5b0f | ~/DFIR-Lab/evidence/original/NET-002_http_file_download.pcapng | Original Evidence Preserved |

---

## Integrity Verification

| Evidence ID | Verification Method | Result |
|-------------|---------------------|--------|
| NET-001 | SHA-256 Hash Verification | Verified Successfully |
| NET-002 | SHA-256 Hash Verification | Verified Successfully |


---

## Notes

- Original evidence remains unmodified.
- Integrity verified immediately after acquisition.
- Analysis will be performed on forensic working copies whenever applicable.
- Evidence IDs are maintained consistently throughout the investigation.