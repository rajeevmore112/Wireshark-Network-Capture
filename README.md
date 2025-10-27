## Wireshark-Network-Capture

Author: Rajeev More
Date: October 27, 2025

## Objective
Capture live packets using Wireshark on Windows (Ethernet interface) and identify common network protocols such as DNS, TCP, and TLS.

## Tools Used
- Wireshark v4.x
- OS: Windows 10
- Interface: Ethernet 

## Capture Summary
- Duration: ~2 minutes
- File: Wireshark_Ethernet_2025_10_27.pcapng
- Total packets: ~56,000
- Protocols observed: DNS, TCP, TLSv1.2

## Protocols Identified

## 1. DNS (Domain Name System)
- Queries to domains like `googleapis.com`, and `spotify.com`
- Protocol: UDP port 53
- Purpose: Resolving domain names to IP addresses  
- Example:  
  Standard query 0x5f49 HTTPS www.googleapis.com
  Standard query response 0x5f49 AAAA 2404:6800:4002:884::200a

## 2. TCP (Transmission Control Protocol)
- Observed SYN, ACK, PSH flags during 3-way handshakes
- Example:  
  192.168.29.14 → 52.168.117.174:443 [SYN, ACK]
- Purpose: Reliable data transport and connection establishment

## 3. TLS/SSL (Transport Layer Security)
- Version: TLSv1.2
- Example packets: “Client Hello”, “Server Hello”, “Change Cipher Spec”
- Indicates HTTPS encryption of web traffic  
- Example:  
  2405:201:e:3066:28d2:70f4:8cdf:48a4 → 2606:4700:81f7:dbb7 TLSv1.2 Server Hello

## Observations
- Most internet traffic uses HTTPS (TLSv1.2) for encryption.
- DNS lookups occur before TCP connections.
- TCP retransmissions occasionally appear (normal in background activity).

## Screenshots
Included in `/screenshots`:
1. DNS traffic view  
2. TCP traffic view  
3. TLS handshake view

## Conclusion
Wireshark successfully captured and displayed live Ethernet traffic.
The capture confirmed DNS for domain resolution, TCP for reliable transport, and TLS for secure communication.

Wireshark-Network-Capture
 ├─ README.md 
 ├─ Wireshark_Ethernet_2025_10_27.pcapng
 └─ screenshots
