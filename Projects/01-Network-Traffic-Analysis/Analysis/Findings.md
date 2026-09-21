# Investigation Findings

## Endpoint Identification

The investigated Windows endpoint was identified as:

- **IP Address:** `10.9.11.135`
- **MAC Address:** `08:d4:0c:7a:29:1e`
- **Hostname:** `DESKTOP-6T17ZFM`
- **User Account:** `gmcdowell`

The hostname and user account were identified through Kerberos traffic, while additional account information was obtained through SAMR traffic.

## Network Traffic Analysis

The endpoint generated significant network traffic and communicated with multiple internal and external systems.

High traffic volume was treated as an investigation lead rather than direct evidence of malicious activity.

## DNS Investigation

DNS traffic showed the endpoint querying the internal DNS server for external domains.

One observed resolution was:

- **Domain:** `quadcinema.com`
- **Resolved IP:** `104.196.13.170`

The endpoint subsequently established encrypted traffic to the resolved address.

## TLS Investigation

TLS traffic was examined using Server Name Indication (SNI).

An observed TLS connection contained:

- **SNI:** `nodejs.org`

This connection was investigated separately from the `quadcinema.com` DNS activity.

## HTTP Investigation

Clear-text HTTP traffic revealed communication between the investigated endpoint and:

- **Remote IP:** `86.106.87.134`
- **Host:** `know.mom-nower.com`

The traffic included HTTP requests using:

`application/octet-stream`

A POST request transferred a large binary payload, which was investigated as a suspicious artifact.

## Suspicious Artifact

HTTP objects were exported from the PCAP.

The largest relevant object was:

- **Filename:** `hfwniayzki`
- **Size:** approximately 4.45 MB
- **Source:** `know.mom-nower.com`
- **Content-Type:** `application/octet-stream`

The artifact was extracted and analyzed in an isolated Windows virtual machine.

## Initial Static Analysis

The extracted artifact was examined using:

- Detect It Easy (DIE)
- FLOSS
- Ghidra

The artifact did not present a confirmed standard Windows PE executable structure during the initial analysis.

Static analysis also did not provide sufficient evidence to conclusively classify the artifact as malware.

## Assessment

The investigation identified suspicious network communication and a suspicious binary artifact transferred over HTTP.

However, the available static-analysis evidence was insufficient to make a definitive malware determination.

A definitive classification would require additional controlled analysis, such as dynamic execution in an isolated malware-analysis environment and deeper reverse engineering.

## Key Skills Demonstrated

- Network traffic analysis
- Wireshark investigation
- DNS and TLS analysis
- HTTP analysis
- Kerberos investigation
- SMB/SAMR analysis
- Endpoint attribution
- IOC identification
- HTTP object extraction
- Initial malware analysis
- Evidence-based assessment
