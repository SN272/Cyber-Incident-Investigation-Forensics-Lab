# Evidence Handling and Chain of Custody Log

## Case ID

DFIR-2026-001

## Case Type

Simulated DFIR Investigation

## Purpose

This document records the handling of forensic evidence used during the simulated investigation.

The project is an academic and cybersecurity portfolio exercise rather than a legal investigation. This document demonstrates evidence handling and chain-of-custody principles within a controlled forensic laboratory environment.

## Evidence Handling Principles

The following principles were applied during the investigation:

- Each evidence item was assigned a unique evidence identifier.
- Evidence acquisition details were documented.
- Cryptographic hashes were calculated after acquisition.
- Evidence integrity was verified using SHA-256.
- Evidence handling actions were documented in the chain-of-custody record.
- Evidence documentation was maintained throughout the investigation.

## Evidence Identifier Format

Evidence identifiers were assigned according to the type of forensic evidence collected.

| Prefix | Evidence Type |
|---------|---------------|
| NET | Network Capture |

Examples:

- `NET-001`
- `NET-002`

Evidence identifiers were assigned sequentially within the evidence category.

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

## Evidence Handling Summary

- Network evidence was assigned unique evidence identifiers.
- SHA-256 integrity was verified after acquisition.
- Evidence identifiers and metadata were maintained consistently.
- Evidence handling information was documented for the completed investigation scope.

## Notes

The chain-of-custody record represents the handling procedures used within this simulated academic forensic laboratory.

It should not be interpreted as a legal chain-of-custody record for court proceedings.