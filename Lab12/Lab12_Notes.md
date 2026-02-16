# Lab 12 – SSH Hardening & Key-Based Authentication

**Environments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (SSH Server)
- VMware NAT Network

---

## Tasks Completed
- Generated SSH key pair on Windows using ssh-keygen
- Located public key in Windows .ssh directory
- Manually copied public key to Ubuntu authorized_keys file
- Created ~/.ssh directory on Ubuntu (if not present)
- Set proper permissions on .ssh and authorized_keys
- Verified successful key-based SSH login
- Edited sshd_config to disable password authentication
- Ensured PubkeyAuthentication was enabled
- Restarted SSH service
- Tested login behavior after hardening
- Captured proof screenshots for documentation

---

## Observations
- SSH key pair was successfully generated on Windows
- Public key was added to ~/.ssh/authorized_keys on Ubuntu
- Proper permissions (700 for .ssh, 600 for authorized_keys) were required for key authentication to function
- SSH login succeeded without prompting for password when using correct private key
- After disabling PasswordAuthentication, password-based logins were rejected
- Attempting login with incorrect username resulted in immediate access denial
- SSH traffic remained encrypted and secure
- Hardening reduced exposure to brute-force password attacks
- Combined with UFW and Fail2Ban, SSH service is now layered and secured

---

## Security Concepts Reinforced
- Public / Private Key Cryptography
- SSH Authentication Methods
- Principle of Least Privilege
- Service Configuration Hardening
- Defense-in-Depth Strategy
- Eliminating Password-Based Attack Vectors
- Secure Remote Administration Practices
