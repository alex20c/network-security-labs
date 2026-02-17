# Lab 13 – Custom Web Server Deployment & HTTP Traffic Analysis

**Environments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (Web Server)
- VMware NAT Network

---

## Tasks Completed
- Verified Apache installation and service status
- Created custom HTML webpage in /var/www/html/index.html
- Confirmed Apache listening on TCP port 80
- Allowed HTTP traffic through UFW firewall
- Accessed custom webpage from Windows browser
- Captured HTTP traffic in Wireshark
- Identified TCP handshake and HTTP request/response
- Blocked port 80 using UFW
- Re-tested web access to observe firewall impact
- Captured blocked connection behavior in Wireshark

---

## Observations (HTTP Allowed)
- Apache was listening on *:80 (all interfaces)
- Windows successfully accessed custom webpage
- Wireshark showed TCP 3-way handshake (SYN, SYN-ACK, ACK)
- Observed HTTP GET request from Windows client
- Server responded with HTTP/1.1 200 OK
- TCP session properly terminated with FIN/ACK sequence
- Verified service binding and successful application-layer communication

---

## Observations (HTTP Blocked via UFW)
- After applying `ufw deny 80`, webpage failed to load
- Browser displayed connection timeout
- Wireshark showed TCP SYN packets with retransmissions
- No SYN-ACK response observed from server
- Behavior confirmed firewall silently dropping packets
- Nmap would identify port 80 as "filtered"

---

## Port & Protocol Analysis
- **Port 80 (TCP)**: Standard HTTP service port
- **Open Port Behavior**: SYN-ACK response indicates active service
- **Filtered Port Behavior**: No response leads to retransmissions
- **HTTP Layer**: GET request followed by 200 OK response
- **TCP Layer**: Full session establishment and termination observed

---

## Security & Administration Concepts Reinforced
- Web server deployment and service management
- Apache configuration and document root modification
- Listening ports and se
