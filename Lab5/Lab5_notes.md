# Lab 5 – FTP vs SFTP Traffic Analysis

**Environments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (FTP / SFTP Server)
- VMware Host-Only Network

---

## Tasks Completed
- Installed and configured vsftpd FTP server on Ubuntu
- Verified FTP service was running
- Captured FTP traffic using Wireshark
- Transferred files using FTP from Windows to Ubuntu
- Observed cleartext credentials and file transfer data
- Used SSH/SFTP for secure file transfer
- Captured SFTP traffic using Wireshark
- Saved and documented packet captures

---

## Observations
- FTP traffic used TCP port 21
- FTP username and password were visible in cleartext within Wireshark
- FTP file transfer commands (USER, PASS, STOR) were readable
- Initial FTP upload was blocked due to default server permission restrictions
- Modified vsftpd configuration to allow write access for lab purposes
- SFTP traffic used TCP port 22 over SSH
- SFTP authentication and file transfer data were encrypted
- No readable credentials or file contents were visible in SFTP capture
- Clear security differences observed between FTP and SFTP protocols

---

## Security Comparison
- FTP transmits authentication credentials and data in cleartext
- SFTP encrypts authentication and data using SSH
- FTP poses significant security risks on untrusted networks
- SFTP is recommended for secure file transfer operations

---

## Tools Used
- Wireshark
- Windows 10 VM
- Ubuntu 24.04 VM
- vsftpd
- OpenSSH
