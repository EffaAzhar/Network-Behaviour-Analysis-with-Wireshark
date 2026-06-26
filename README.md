# Network Behaviour Analysis with Wireshark

## Project Overview

This project explores network traffic analysis using **Wireshark** within a controlled Ubuntu Linux laboratory environment. The objective is to develop practical skills in packet capture, protocol analysis, network troubleshooting and behavioural observation through the inspection of real network traffic. The project progresses from analysing fundamental network protocols to investigating real world troubleshooting scenarios, providing hands-on experience in understanding how systems communicate across modern TCP/IP networks.
Rather than focusing solely on protocol theory this repository demonstrates how Wireshark can be used to analyse packet level communication, troubleshoot connectivity issues and investigate network behaviour in practical cybersecurity scenarios.
## Lab Environment

| Component              | Details                                               |
| ---------------------- | ----------------------------------------------------- |
| Host System            | macOS                                                 |
| Virtualisation         | UTM                                                   |
| Guest Operating System | Ubuntu Linux                                          |
| Network Analysis Tool  | Wireshark                                             |
| Protocols Analysed     | DNS, TCP, TLS, HTTP, HTTPS, ARP, ICMP, DHCP, FTP, SSH |


## How a Secure Web Connection is Established

One of the core objectives of this project is understanding how multiple network protocols work together to establish a secure web connection. The communication process analysed throughout this repository is illustrated below.

```text
User enters https://google.com
           │
           ▼
DNS
Resolve the domain name to an IP address
           │
           ▼
TCP Three-Way Handshake
Establish a reliable connection
           │
           ▼
TLS Handshake
Negotiate encryption and authenticate the server
           │
           ▼
HTTPS Request
Request the webpage securely
           │
           ▼
HTTPS Response
Receive the encrypted webpage
```

Each protocol involved in this communication process is analysed using real packet captures collected with Wireshark.

## Learning Objectives

* Capture and inspect live network traffic.
* Analyse packet-level communication using Wireshark.
* Understand common network protocols and their interactions.
* Examine secure and insecure communication protocols.
* Investigate network connectivity and performance issues.
* Apply Wireshark display filters to isolate specific traffic.
* Develop practical network troubleshooting skills.
* Document packet analysis using a structured investigation methodology.

## Technologies Used

* Ubuntu Linux
* Wireshark
* TCP/IP Networking
* DNS
* TCP
* TLS
* HTTP
* HTTPS
* ARP
* ICMP
* DHCP
* FTP
* SSH


## Repository Structure

```text
Network-Behaviour-Analysis-with-Wireshark/

README.md

01-wireshark-installation.md
02-packet-capture-basics.md
03-dns-analysis.md
04-tcp-three-way-handshake.md
05-tls-handshake.md
06-http-vs-https.md
07-arp-analysis.md
08-icmp-analysis.md
09-dhcp-analysis.md
10-ftp-analysis.md
11-ssh-analysis.md
12-network-troubleshooting.md
13-essential-wireshark-filters.md

screenshots/
```

## Network Troubleshooting Investigations

The repository also includes practical troubleshooting exercises demonstrating how Wireshark can be used to investigate common networking issues. Completed investigations are following

* DNS Resolution Failure
* TCP Connection Refused (RST)
* High Network Latency
* HTTP 404 Not Found
Each investigation follows a structured workflow:

```text
Generate the Issue
        │
        ▼
Capture Network Traffic
        │
        ▼
Apply Wireshark Filters
        │
        ▼
Analyse Packets
        │
        ▼
Identify Root Cause
        │
        ▼
Document Findings
```

## Skills Demonstrated

* Network Traffic Analysis
* Packet Capture
* Packet Inspection
* TCP/IP Analysis
* DNS Analysis
* TLS Handshake Analysis
* HTTP/HTTPS Analysis
* ARP Analysis
* ICMP Analysis
* DHCP Analysis
* FTP Analysis
* SSH Analysis
* Network Troubleshooting
* Linux Administration
* Cybersecurity Documentation
* Network Visibility and Monitoring

## Learning Outcomes

By completing this project I developed practical experience in:

* Capturing and analysing live network traffic.
* Understanding communication between common network protocols.
* Interpreting packet level behaviour using Wireshark.
* Troubleshooting network connectivity and application layer issues.
* Investigating secure and insecure communication protocols.
* Applying protocol analysis techniques commonly used by cybersecurity professionals.

## Disclaimer

All packet captures and network activities were performed within a controlled laboratory environment for educational and research purposes. No unauthorised systems or production networks were analysed during this project.

## Future Improvements
Potential future enhancements include:
- IPv6 traffic analysis
- HTTP/2 and HTTP/3 analysis
- DNS over HTTPS (DoH)
- Network performance visualisation
- Malware traffic analysis
- Packet capture automation using Tshark

# Author

**Effa Azhar**

Cybersecurity Research Portfolio

GitHub: https://github.com/EffaAzhar
