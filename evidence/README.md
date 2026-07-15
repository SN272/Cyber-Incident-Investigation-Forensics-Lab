# Forensic Evidence

## Case ID

DFIR-2026-001

## Purpose

This directory is used to organise forensic evidence associated with the simulated Digital Forensics and Incident Response investigation.

The evidence structure separates original acquired evidence, forensic working copies, and artifacts extracted during analysis.

## Directory Structure

### `original/`

Contains original forensic evidence acquired during the simulated incident investigation.

Original evidence should not be intentionally modified after acquisition.

Cryptographic hashes are calculated and documented to establish evidence integrity.

### `working-copies/`

Contains forensic copies designated for analysis.

Where tool compatibility or investigative workflow requires direct access to an evidence file, a working copy should be used instead of intentionally modifying the original evidence.

### `extracted-artifacts/`

Contains files and artifacts extracted during forensic analysis.

Examples may include:

* Network objects.
* Executable files.
* Scripts.
* Documents.
* Memory-extracted processes.
* Configuration artifacts.
* Relevant filesystem artifacts.

Extracted artifacts are considered investigation outputs and are stored separately from the original evidence.

## Evidence Handling Workflow

The following evidence handling process is used in this project:

1. Identify the evidence source.
2. Acquire or generate the evidence within the controlled investigation environment.
3. Assign a unique evidence identifier.
4. Record acquisition details.
5. Calculate cryptographic hashes.
6. Document the evidence in the evidence manifest.
7. Preserve the original evidence.
8. Create a working copy where required.
9. Verify the working copy against the original evidence.
10. Perform forensic analysis on the designated evidence copy.
11. Store extracted artifacts separately.

## Evidence Integrity

SHA-256 will be used as the primary cryptographic hashing algorithm for evidence integrity verification.

Additional hashes may be recorded where required by a forensic tool or evidence format.

A hash mismatch between an original evidence file and its expected value will be investigated before further analysis.

## Repository Storage Notice

Large forensic evidence files may not be committed directly to the public GitHub repository due to file size, licensing, privacy, or security considerations.

Where evidence is excluded from version control, the evidence manifest and investigation documentation will retain the evidence identifier, filename, description, cryptographic hash, and relevant acquisition information.

Potentially suspicious extracted artifacts will not be published as directly executable files in the public repository.
