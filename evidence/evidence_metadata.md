# Evidence Metadata

This document records the technical metadata of forensic evidence acquired during the completed investigation.

---

# NET-001 — Baseline Network Connectivity Capture

## General Information

| Property | Value |
|----------|-------|
| Evidence ID | NET-001 |
| Evidence Type | Network Packet Capture |
| File Name | NET-001_baseline_connectivity.pcapng |
| File Format | PCAPNG |
| Encapsulation | Ethernet |
| File Size | 4,842 bytes |

---

## Integrity Information

| Property | Value |
|----------|-------|
| SHA-256 | a114faf5e6b2f98fa2cb441a45f15a5b7a792279071da33e0c546e742c9536e1 |
| SHA-1 | 3132b875cb53c92165e4c08d57dd75c9a6a58631 |
| Integrity Status | Verified |

---

## Capture Timeline

| Property | Value |
|----------|-------|
| First Packet | 2026-08-03 18:28:36 |
| Last Packet | 2026-08-03 18:28:56 |
| Capture Duration | 20 Seconds |

---

## Capture Statistics

| Property | Value |
|----------|-------|
| Interface | eth0 |
| Total Packets Captured | 44 |
| ICMP Packets Displayed | 40 |
| Display Filter Used | icmp |

---

## Observations

- Successful bidirectional ICMP communication was observed.
- No packet loss was detected.
- No malformed packets were observed.
- The capture establishes a controlled baseline of network communication within the isolated laboratory environment.

---

# NET-002 — HTTP File Download Simulation

## General Information

| Property | Value |
|----------|-------|
| Evidence ID | NET-002 |
| Evidence Type | Network Packet Capture |
| File Name | NET-002_http_file_download.pcapng |
| File Format | PCAPNG |
| Encapsulation | Ethernet |

---

## Integrity Information

| Property | Value |
|----------|-------|
| SHA-256 | bf81896d1c542e4115dadf5ba7fed70d0b1f103846c9945b1916f061cd8b5b0f |
| Integrity Status | Verified |

---

## Capture Summary

| Property | Value |
|----------|-------|
| Protocols Observed | HTTP, TCP, ICMP |
| Total Packets Captured | 37 |
| HTTP Packets | 4 |

---

## Key Observations

- An HTTP GET request was successfully captured.
- Requested object: `confidential.txt`
- An HTTP 200 OK response was observed.
- The file transfer was successfully completed.
- The transferred object was recoverable through **File → Export Objects → HTTP**.
- Source Host: `10.10.50.20` (WS-FIN-01)
- Destination Host: `10.10.50.10` (DFIR-ANALYST HTTP Server)

---

## Forensic Value

This capture demonstrates:

- HTTP request and response reconstruction.
- Identification of a transferred resource.
- Network event timeline analysis.
- Recovery of an HTTP-transferred object from packet capture.