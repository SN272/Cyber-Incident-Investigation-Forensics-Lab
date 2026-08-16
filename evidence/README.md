# Forensic Evidence

## Case ID

DFIR-2026-001

## Purpose

This directory documents the organisation and handling of forensic evidence associated with the simulated DFIR investigation.

The repository separates original evidence, working documentation, and extracted-artifact storage.

## Directory Structure

### `original/`

Reserved for original forensic evidence acquired during the investigation.

The directory is empty in the final published repository. Evidence excluded from the repository is documented through the evidence manifest, metadata, and integrity records.

### `working-copies/`

Contains evidence documentation and designated working material used during the investigation.

### `extracted-artifacts/`

Reserved for artifacts extracted or derived during forensic analysis.

The directory is empty in the final published project scope.

## Evidence Handling Workflow

The completed workflow was:

1. Identify the evidence source.
2. Acquire or generate the evidence in the controlled laboratory.
3. Assign a unique evidence identifier.
4. Record acquisition details.
5. Calculate a cryptographic hash.
6. Document the evidence in the manifest.
7. Preserve the evidence according to the laboratory workflow.
8. Verify evidence integrity.
9. Perform forensic analysis.
10. Document the resulting observations and findings.

## Evidence Integrity

SHA-256 was used to verify the integrity of the acquired network evidence.

The calculated hashes are documented in the evidence manifest, metadata, and chain-of-custody documentation.

## Repository Storage Notice

Large forensic evidence files may not be committed to the public GitHub repository due to file size, licensing, privacy, or security considerations.

Where evidence is excluded from version control, the repository retains relevant metadata including:

- Evidence identifier
- Filename
- Description
- Cryptographic hash
- Evidence type
- Acquisition information

The `original/` and `extracted-artifacts/` directories are retained for evidence organisation but are empty in the final published project scope.