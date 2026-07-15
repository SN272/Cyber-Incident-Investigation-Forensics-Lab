# Investigation Questions

## Case ID

DFIR-2026-001

The forensic investigation will attempt to answer the following questions using evidence obtained from network traffic, volatile memory, disk or filesystem artifacts, and publicly available threat intelligence.

Conclusions will be based on observable forensic artifacts and documented investigative findings.

## Initial Compromise

1. What system or user activity preceded the suspected compromise?
2. Is there evidence of a suspicious download, document, executable, script, or archive?
3. Can a potential initial access or infection vector be identified?
4. Can the suspected initial access activity be associated with a specific timestamp or sequence of events?
5. Is there evidence of user interaction preceding suspicious process or network activity?

## Network Activity

6. Which internal hosts are present in the packet capture?
7. Which external IP addresses communicated with the suspected workstation?
8. Which domains were queried by the affected system?
9. Are any DNS requests or responses anomalous or suspicious?
10. Is suspicious HTTP or other application-layer traffic present?
11. Is repeated or periodic network communication present?
12. Does the timing of repeated communication suggest potential beaconing behaviour?
13. Is there evidence consistent with command-and-control communication?
14. Are suspicious files or payloads transferred over the network?
15. Is there evidence suggesting attempted or successful data exfiltration?

## Memory Analysis

16. What operating system information can be identified from the memory image?
17. Which processes were active at the time of memory acquisition?
18. Are any processes anomalous based on their name, path, parent process, or execution context?
19. Are suspicious parent-child process relationships present?
20. Are command-line artifacts associated with suspicious execution present?
21. Can active or historical network connections be associated with specific processes?
22. Are hidden, terminated, or unlinked processes identifiable?
23. Is there evidence of process injection?
24. Are suspicious loaded modules or DLLs present?
25. Can relevant executables, scripts, or other artifacts be extracted from memory?

## Disk and Filesystem Analysis

26. Are suspicious executables, scripts, documents, or archives present on the examined evidence?
27. Can downloaded files relevant to the incident be identified?
28. What filesystem metadata is associated with suspicious files?
29. Are deleted artifacts relevant to the suspected incident recoverable?
30. Are user activity artifacts associated with the suspected compromise?
31. Is there evidence of suspicious PowerShell, command shell, or script execution?
32. Is there evidence of a persistence mechanism?
33. Are relevant startup, scheduled task, registry, or other persistence artifacts available?
34. Can file hashes be extracted from suspicious artifacts?

## Threat Intelligence and OSINT

35. Are identified IP addresses associated with previously reported malicious activity?
36. Are identified domains or URLs associated with suspicious or malicious infrastructure?
37. Are extracted file hashes associated with known malicious files?
38. Can identified Indicators of Compromise be enriched using publicly available intelligence sources?
39. Is there sufficient intelligence to associate the observed behaviour with a documented malware family or campaign?
40. What confidence level can be assigned to the threat intelligence findings?

## Incident Correlation

41. Can suspicious network connections be associated with processes identified in volatile memory?
42. Can suspicious processes be associated with files identified in disk or filesystem evidence?
43. Do timestamps from network, memory, and filesystem artifacts support a common sequence of events?
44. Can the suspected initial access activity be linked to later execution or network communication?
45. Can a complete or partial attack sequence be reconstructed?
46. Which forensic artifacts provide the strongest evidence of compromise?
47. Which MITRE ATT&CK techniques are directly supported by the forensic evidence?
48. Is there evidence of command-and-control activity?
49. Is there sufficient evidence to support a data exfiltration finding?
50. What is the most likely technical conclusion regarding the suspected workstation compromise?

## Evidence Standard

Each answered investigation question should be supported by one or more documented forensic artifacts where possible.

Relevant findings should include artifact identifiers, timestamps, process identifiers, IP addresses, domains, file paths, hashes, packet references, or forensic tool output as applicable.

Questions that cannot be conclusively answered using the available evidence will be documented as inconclusive rather than assumed.
