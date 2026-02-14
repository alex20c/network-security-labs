# Lab 7 – Firewall Rules & Port Blocking (UFW)

**Environments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (Server)
- VMware Host-Only Network

---

## Tasks Completed
- Verified SSH service was running on Ubuntu
- Captured baseline SSH traffic using Wireshark
- Enabled UFW (Uncomplicated Firewall) on Ubuntu
- Configured firewall rule to deny inbound traffic on port 22
- Attempted SSH connection from Windows while port 22 was blocked
- Captured blocked SSH traffic in Wireshark
- Re-allowed port 22 and verified restored connectivity
- Saved packet captures for documentation

---

## Observations
- SSH uses TCP port 22 for secure remote access
- When SSH was allowed, a full TCP three-way handshake (SYN, SYN-ACK, ACK) was observed
- SSH session traffic was encrypted after successful connection
- After blocking port 22 using UFW, Wireshark captured repeated TCP SYN retransmissions from the Windows client
- No SYN-ACK responses were received from the Ubuntu server while the firewall rule was active
- Windows Command Prompt displayed a "Connection timed out" error
- The timeout behavior confirmed the firewall was silently dropping inbound SSH traffic
- Re-enabling port 22 restored normal TCP handshake behavior and SSH connectivity

---

## Firewall Behavior Analysis
- Firewall drop rules result in no response to connection attempts
- TCP retransmissions occur when the client does not receive an expected response
- A timeout indicates packet filtering (silent drop), not service failure
- Differentiated firewall blocking from service shutdown based on packet behavior

---

## Tools Used
- Wireshark
- Windows 10 VM
- Ubuntu 24.04 VM
- UFW (Uncomplicated Firewall)
- OpenSSH
