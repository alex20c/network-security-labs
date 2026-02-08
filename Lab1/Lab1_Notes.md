Lab 1 - Wireshark DNS & HTTPS Capture

**VM IPv4:** 192.168.152.128

**TASK** 
- Captured traffic from windows 10 VM
- Filtered DNS Queries: 'dns and ip.addr == 192.168.152.128'
- Filtered HTTPS traffic 'tcp.port == 443 and ip.addr == 192.168.152.128'

**Observations**
- DNS queries to resolve youtube.com, google.com, facebook.com, amazon.com 
- TCP handshake observed on port 443 for HTTPS
- Source/Destination IPs show communication between VM and websites
- All traffic captured saved for documentation.

**Tools used**
- Wireshark (4.6.3.0)
- Windows 10 VM 