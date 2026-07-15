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

Evidence identifiers use the following format:

`E###`

Examples:

* `E001`
* `E002`
* `E003`

Evidence identifiers are assigned sequentially during acquisition.

## Evidence Handling Log

| Date and Time (UTC) | Evidence ID | Action | Tool or Method | Performed By | Integrity Verification | Notes |
| ------------------- | ----------- | ------ | -------------- | ------------ | ---------------------- | ----- |

## Notes

The evidence handling log will be updated as evidence is acquired, verified, copied, or otherwise processed during the investigation.

Routine read-only forensic analysis does not require a separate log entry for every individual tool command. Significant evidence handling actions, integrity verification activities, and creation of designated forensic copies will be documented.
