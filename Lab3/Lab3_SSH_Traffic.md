# Lab 3 - SSH Traffic Capture

**Enviroments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (SSH Server)
- VMware Host-Only Network

**Tasks Completed**
- Verified SSH service was installed and running on Ubuntu VM
- Initiated SSH connection from Windows VM to Ubuntu VM
- Authenticated using Ubuntu user credentials
- Executed basic commands over SSH
- Captured SSH traffic in Wireshark

**Observations**
- TCP handshake visible between Windows and Ubuntu on port 22
- SSH protocol version exchange visible in plaintext
- SSH key exchange observed during session setup
- All authentication and command traffic encrypted after key exchange
- Clean Host-Only traffic with no external network interference

**Tools Used**
- Wireshark
- Windows 10 VM
- Ubuntu 24.04 VM