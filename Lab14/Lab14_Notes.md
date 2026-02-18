# Lab 14 – HTTPS Deployment & TLS Encryption Analysis

**Environments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (Web Server)
- VMware NAT Network

---

## Tasks Completed
- Enabled Apache SSL module (a2enmod ssl)
- Generated self-signed SSL certificate using OpenSSL
- Configured Apache default-ssl virtual host
- Assigned custom certificate and private key paths
- Restarted Apache service
- Allowed HTTPS (port 443) through UFW firewall
- Accessed web server using HTTPS from Windows client
- Captured encrypted HTTPS traffic in Wireshark
- Compared HTTP vs HTTPS packet visibility

---

## Observations (HTTPS Enabled)
- Apache successfully listening on TCP port 443
- Browser displayed certificate warning (self-signed certificate)
- HTTPS connection established after proceeding
- Custom webpage loaded over encrypted connection
- Wireshark showed TCP 3-way handshake (SYN, SYN-ACK, ACK)
- TLS handshake observed (Client Hello, Server Hello, Certificate)
- Application data displayed as "Encrypted Application Data"
- No readable HTTP GET or 200 OK visible due to encryption

---

## Observations (Certificate Behavior)
- Browser warning triggered due to self-signed certificate
- Certificate not issued by trusted Certificate Authority (CA)
- Encryption functional despite lack of public trust validation
- Demonstrated difference between encryption and certificate trust

---

## Protocol & Security Analysis
- **Port 443 (TCP)**: Standard HTTPS service port
- **TLS Handshake**: Negotiates encryption parameters
- **Client Hello**: Client proposes supported cipher suites
- **Server Hello**: Server selects encryption method
- **Certificate Exchange**: Server presents public key
- **Encrypted Application Data**: HTTP content secured within TLS
- HTTPS prevents packet-level inspection of web content

---

## HTTP vs HTTPS Comparison

HTTP (Port 80):
- Plaintext traffic
- GET requests visible
- 200 OK responses visible
- No encryption

HTTPS (Port 443):
- Encrypted traffic
- TLS handshake required
- HTTP content hidden
- Secure communication channel established

---

## Security & Administration Concepts Reinforced
- SSL/TLS certificate generation
- Apache SSL configuration
- Virtual host management
- Firewall rule configuration
- Encrypted vs unencrypted traffic analysis
- TLS handshake structure
- Certificate trust model
- Network security fundamentals

---

## Tools Used
- Apache2
- OpenSSL
- Wireshark
- UFW (Uncomplicated Firewall)
- ss (Socket Statistics)
- Windows Web Browser
- Ubuntu 24.04 VM
- Windows 10 VM
