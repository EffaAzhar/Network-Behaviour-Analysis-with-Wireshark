# Packet Capture Basics

Before analysing individual network protocols, it is important to understand the following concepts.

## What is Packet Capture?

Packet capture is the process of intercepting and recording network traffic as it travels across a network interface. Wireshark captures these packets and presents them for detailed analysis. Every packet transmitted across a network contains information such as:

* Source IP address
* Destination IP address
* Protocol type
* Packet size
* Communication details


## Understanding Network Interfaces

A network interface is the connection through which a computer sends and receives network traffic. An easy way to think about this is:

* Computer = House
* Network Interface = Front Door
* Network Packets = People entering and leaving the house

Wireshark listens at one of these "doors" to observe all network traffic passing through it. When Wireshark starts, all available interfaces are displayed. The active interface is usually identified by a small traffic graph showing network activity. Common network interfaces found on Ubuntu include following:

| Interface | Description                                                        |
| --------- | ------------------------------------------------------------------ |
| `eth0`    | Ethernet connection (legacy naming)                                |
| `enp0s3`  | Wired Ethernet interface commonly used in virtual machines         |
| `ens33`   | Ethernet interface used by some virtualisation platforms           |
| `wlan0`   | Wireless (Wi-Fi) interface                                         |
| `lo`      | Loopback interface used for communication within the local machine |

## Starting a Packet Capture

To begin capturing packets:

1. Open Wireshark.
2. Select the active network interface.
3. Double-click the interface.
4. Observe packets appearing in real time.

Once capturing begins, Wireshark continuously records packets until the capture is stopped.


## Understanding the Wireshark Interface

The Wireshark interface consists of three primary sections.

### 1. Packet List Pane

Displays every captured packet in chronological order and following information about packets is included in display,
* Packet number
* Time
* Source
* Destination
* Protocol
* Packet summary

### 2. Packet Details Pane

Displays protocol information for the selected packet.
* Ethernet
* Internet Protocol (IP)
* TCP
* UDP
* DNS
* ICMP
  
### 3. Packet Bytes Pane

Displays the raw packet data in hexadecimal and ASCII format. This allows analysts to inspect the actual bytes transmitted across the network.

## Generating Test Traffic with Ping

To verify that Wireshark is successfully capturing traffic, a simple network test can be performed using the `ping` command. This command checks whether another device on the network is reachable. Running `ping` generates predictable network traffic gives us starting point for learning packet analysis.

```bash
ping google.com
```
When the command does the following:
1. The system resolves `google.com` to an IP address using DNS.
2. An ICMP Echo Request packet is sent to the destination.
3. Google responds with an ICMP Echo Reply.
4. The round-trip time is measured and displayed.

![Ping Command](../screenshots/02-ping-command-terminal.png)

*Figure 1: Executing the `ping google.com` command to generate ICMP network traffic for packet capture.*
### Observations
* The terminal output confirms that:
* The domain google.com was successfully resolved to an IP address.
* 35 ICMP packets were transmitted and received.
* No packet loss occurred.
* The average round-trip time was approximately 27 ms, indicating successful network connectivity.

## Capturing Network Traffic

While the `ping` command was running  Wireshark captured the generated network traffic on the active network interface. To stop network traffic capture red square button on the left side is selected.

![Packet Capture Overview](../screenshots/03-packet-capture-overview.png)

*Figure 2: Wireshark capturing live network traffic generated during the ping operation.*

### Observations

Several protocols can be observed in the capture:

- **DNS** packets resolve `google.com` into its IP address before communication begins.
- **ICMP Echo Request** packets are sent from the Ubuntu virtual machine to Google's server.
- **ICMP Echo Reply** packets are returned by Google's server, confirming successful communication.
- Additional background traffic, including **NTP** and **ARP**, is also visible because Wireshark captures all traffic passing through the selected network interface.

This demonstrates that Wireshark records both the requested test traffic and other normal network activity occurring on the system.

## Saving Packet Captures

Packet captures can be saved for future analysis.

Wireshark uses the following file format:

```text
.pcapng
```

Example:

```text
pcaps/icmp.pcapng
```

Saving captures allows network traffic to be reviewed without generating new packets.

## Conclusion

This introduced the basic concepts required for network traffic analysis using Wireshark. Understanding network interfaces, packet capture and the generation of test traffic provides the foundation for analysing protocols such as ICMP, DNS, TCP, HTTP and HTTPS in subsequent sections of this project.

