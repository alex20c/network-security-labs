# Lab 4 - Cleartext TCP Traffic Capture (Netcat)

**Enviroments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (Netcat Listener)
- VMware Host-Only Network

**Tasks Completed**
- Started Netcat listener on Ubuntu VM
- Initiated TCP connection from Windows VM using Ncat
- Transmitted test credentials and commands over TCP
- Captured cleartext TCP traffic in Wireshark
- Saved packet capture for documentation

**Observations**
- TCP handshake observed between Windows and Ubuntu on port 4444
- Raw TCP session established with no authentication or encryption
- User input, including test credentials, visible in plaintext
- Commands transmitted and readable in packet capture
- Clean Host-Only traffic with no external network interference

**Tools Used**
- Wireshark
- Windows 10 VM
- Ubuntu 24.04 VM
- Netcat (Ubuntu)
- Ncat (Windows)
