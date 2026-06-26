# Essential Wireshark Filters

## Overview

Throughout this project, Wireshark display filters were used to isolate specific protocols and analyse network behaviour. This chapter summarises the most useful filters encountered during the lab exercises. Display filters do **not** modify the packet capture. They allow analysts to focus on packets relevant to a particular protocol, host, port or network event.

# Filters Used Throughout This Repository

| Chapter | Primary Filter |
|----------|----------------|
| DNS Analysis | `dns` |
| TCP Three-Way Handshake | `tcp` |
| TLS Handshake | `tls` |
| HTTP vs HTTPS | `http`, `tls` |
| ARP Analysis | `arp` |
| ICMP Analysis | `icmp` |
| DHCP Analysis | `dhcp` |
| FTP Analysis | `ftp` |
| SSH Analysis | `ssh` |
| Network Troubleshooting | `dns`, `icmp`, `tcp.flags.reset == 1`, `http.response.code == 404` |
# Further Important Filters
## Protocol Filters

| Display Filter | Purpose |
|----------------|---------|
| `arp` | Display ARP packets |
| `dns` | Display DNS queries and responses |
| `icmp` | Display ICMP Echo Requests and Replies |
| `dhcp` | Display DHCP traffic |
| `tcp` | Display all TCP packets |
| `udp` | Display all UDP packets |
| `http` | Display HTTP traffic |
| `tls` | Display TLS handshake traffic |
| `ftp` | Display FTP packets |
| `ssh` | Display SSH traffic |


## TCP Analysis Filters

| Display Filter | Purpose |
|----------------|---------|
| `tcp.flags.syn == 1` | Display SYN packets |
| `tcp.flags.reset == 1` | Display TCP Reset (RST) packets |
| `tcp.flags.fin == 1` | Display TCP connection termination |
| `tcp.analysis.retransmission` | Display TCP retransmissions |
| `tcp.analysis.duplicate_ack` | Display Duplicate ACKs |
| `tcp.analysis.lost_segment` | Display lost TCP segments |


## Port Filters

| Display Filter | Purpose |
|----------------|---------|
| `tcp.port == 21` | FTP |
| `tcp.port == 22` | SSH |
| `tcp.port == 53` | DNS over TCP |
| `udp.port == 53` | DNS over UDP |
| `tcp.port == 80` | HTTP |
| `tcp.port == 443` | HTTPS |
| `udp.port == 67 || udp.port == 68` | DHCP |


## IP Address Filters

| Display Filter | Purpose |
|----------------|---------|
| `ip.addr == 192.168.64.4` | Display traffic to or from a specific host |
| `ip.src == 192.168.64.4` | Display packets sent by the host |
| `ip.dst == 192.168.64.4` | Display packets received by the host |

## Search Filters

| Display Filter | Purpose |
|----------------|---------|
| `frame contains "google"` | Search for text inside packets |
| `http.request.method == "GET"` | Display HTTP GET requests |
| `http.response.code == 404` | Display HTTP 404 responses |


## Useful Logical Operators

| Filter | Description |
|---------|-------------|
| `&&` | AND |
| `||` | OR |
| `!` | NOT |

### Examples

Display DNS traffic from a specific host:

```text
dns && ip.addr == 192.168.64.4
```

Display HTTP traffic on port 80:

```text
http && tcp.port == 80
```

Display TCP Reset packets:

```text
tcp.flags.reset == 1
```

Display ICMP packets:

```text
icmp
```

# Tips

- Begin with broad protocol filters before applying more specific filters.
- Combine filters using logical operators to reduce unrelated traffic.
- Right click a packet field and choose **Apply as Filter** to create filters automatically.
- Use **Follow TCP Stream** to reconstruct application layer conversations.
- Save commonly used filters for quicker future analysis.


# Key Takeaways

- Display filters simplify packet analysis without modifying the original capture.
- Combining protocol, port and IP filters helps isolate specific network events.
- Display filters are an essential skill for efficient network troubleshooting and forensic analysis.
- Mastering a small set of commonly used filters significantly improves productivity when analysing packet captures.
