# Network & Security Home Lab Portfolio

## Overview
This repository contains hands-on networking and security labs performed in virtualized environments using Windows and Ubuntu.  
The labs focus on traffic analysis, protocol behavior, and security implications of encrypted vs unencrypted communication.

All labs were performed using VMware virtual machines and documented with packet captures and written observations.

---

## Lab Environment
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (Server)
- VMware Host-Only Networking
- Wireshark
- Netcat / Ncat
- OpenSSH
- Apache2

---

## Labs

### Lab 1 – DNS & HTTPS Traffic Capture
**Concepts:**
- DNS name resolution
- HTTPS traffic analysis
- Encrypted web communication

**Skills Demonstrated:**
- Wireshark filtering
- Protocol identification
- TCP/IP fundamentals

---

### Lab 2 – HTTP Traffic Capture
**Concepts:**
- Cleartext HTTP communication
- Client-server interaction
- TCP handshake analysis

**Skills Demonstrated:**
- Packet inspection
- Web traffic analysis
- Host-only network isolation

---

### Lab 3 – SSH Traffic Capture
**Concepts:**
- Secure remote administration
- Encryption and key exchange
- SSH protocol behavior

**Skills Demonstrated:**
- Secure protocol analysis
- Authentication flow understanding
- Network security principles

---

### Lab 4 – Cleartext TCP Traffic (Netcat)
**Concepts:**
- Raw TCP communication
- Cleartext data exposure
- Security risks of unencrypted services

**Skills Demonstrated:**
- Netcat/Ncat usage
- Packet-level data inspection
- Security comparison and analysis

---

## Key Takeaways
- Not all network protocols provide encryption by default
- Cleartext traffic can expose sensitive information
- Packet captures are critical for understanding and troubleshooting network behavior
- Secure protocols like SSH protect data from interception

---

## Tools Used
- Wireshark
- VMware Workstation / Player
- Windows 10
- Ubuntu 24.04
- Netcat / Ncat
- OpenSSH
