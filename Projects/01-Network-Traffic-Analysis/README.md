# Network Traffic Investigation

## Project Overview

A hands-on network traffic investigation using Wireshark to analyze a real-world Windows endpoint captured in a malware traffic analysis training exercise.

The investigation focused on identifying the affected endpoint, analyzing network communications, extracting indicators of interest, and investigating a suspicious HTTP-delivered artifact.

## Objectives

- Identify the potentially affected Windows endpoint.
- Determine the endpoint's IP address, MAC address, hostname, and user account.
- Analyze DNS, TLS, HTTP, Kerberos, SMB, and SAMR traffic.
- Identify suspicious external communications.
- Extract and examine a suspicious HTTP artifact.
- Perform initial static analysis of the extracted artifact.
- Document findings using an evidence-based investigation process.

## Tools

- Wireshark
- 7-Zip
- Detect It Easy (DIE)
- FLOSS
- Ghidra

## Key Findings

- Investigated endpoint: `10.9.11.135`
- Hostname: `DESKTOP-6T17ZFM`
- User account: `gmcdowell`
- Suspicious external IP: `86.106.87.134`
- Suspicious HTTP host: `know.mom-nower.com`
- HTTP communication included binary data transferred using `application/octet-stream`.
- A large HTTP object was extracted for further analysis.

## Investigation

The investigation included:

1. Endpoint identification using Wireshark statistics and packet analysis.
2. DNS analysis to identify domain resolution and subsequent connections.
3. TLS analysis and Server Name Indication (SNI) inspection.
4. Kerberos analysis to identify the Windows user and hostname.
5. SAMR analysis to obtain additional account information.
6. HTTP traffic analysis and identification of suspicious communications.
7. TCP stream analysis of suspicious HTTP traffic.
8. HTTP object extraction from the PCAP.
9. Initial static analysis of the extracted artifact using multiple security tools.

## Final Assessment

The network investigation identified suspicious communications and an extracted binary artifact associated with the investigated Windows endpoint.

Initial static analysis did not provide sufficient evidence to conclusively classify the extracted artifact as malware. Further controlled dynamic analysis and deeper reverse engineering would be required for a definitive malware determination.

## Skills Demonstrated

- Network traffic analysis
- Packet analysis
- DNS and TLS investigation
- HTTP investigation
- Windows/Active Directory traffic analysis
- IOC identification
- Artifact extraction
- Initial malware analysis
- Evidence-based security reporting
