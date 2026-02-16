# Lab 11 – Intrusion Detection & Automated IP Banning (Fail2Ban)

**Environments**
- Windows 10 VM (Client / Attacker)
- Ubuntu 24.04 VM (Target Server)
- VMware NAT Network

---

## Tasks Completed
- Installed Fail2Ban on Ubuntu
- Verified Fail2Ban service status
- Created local jail configuration file
- Enabled SSH (sshd) protection
- Configured max retry and ban time settings
- Restarted Fail2Ban service
- Simulated failed SSH login attempts from Windows
- Triggered automatic IP ban after exceeding retry limit
- Verified banned IP using fail2ban-client
- Monitored Fail2Ban logs for security events

---

## Observations
- Fail2Ban monitors authentication logs for repeated failed login attempts
- SSH brute-force attempts were generated from Windows using incorrect credentials
- After exceeding the configured maxretry value, the Windows IP address was automatically banned
- Subsequent SSH attempts were immediately blocked
- The banned IP appeared in the sshd jail status output
- Fail2Ban dynamically inserted firewall rules to block malicious traffic
- Log entries confirmed detection, ban action, and enforcement
- Demonstrated automated intrusion prevention based on behavioral patterns
- Verified layered security approach alongside UFW firewall
