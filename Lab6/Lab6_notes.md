# Lab 6 – DHCP Traffic & IP Assignment Analysis

**Environments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (DHCP Server)
- VMware Host-Only Network

---

## Tasks Completed
- Installed and configured isc-dhcp-server on Ubuntu
- Identified active network interface (ens33) on Ubuntu
- Configured DHCP scope for Host-Only network
- Disabled VMware Host-Only DHCP to isolate lab environment
- Assigned static IP address to Ubuntu DHCP server
- Captured DHCP traffic using Wireshark
- Forced DHCP lease renewal from Windows client
- Observed successful DHCP IP assignment
- Stopped DHCP server to simulate failure condition
- Captured DHCP failure traffic and client behavior

---

## Observations
- DHCP traffic uses UDP ports 67 (server) and 68 (client)
- Windows client broadcasted DHCP Discover packets to request an IP address
- Ubuntu DHCP server responded with Offer, followed by Request and Acknowledgment (DORA process)
- Windows client successfully received an IP address from the Ubuntu DHCP server during normal operation
- VMware Host-Only DHCP initially provided IP leases and was disabled to prevent interference
- When the DHCP server was stopped, the Windows client sent repeated DHCP Discover broadcasts
- No DHCP Offer responses were observed during failure testing
- Windows client failed to obtain a lease and self-assigned an APIPA address (169.254.0.0/16)
- Packet captures clearly demonstrated dependency on DHC
