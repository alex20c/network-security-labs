# Lab 8 – DNS Server Deployment & Failure Analysis (Bind9)

**Environments**
- Windows 10 VM (Client)
- Ubuntu 24.04 VM (DNS Server)
- VMware Host-Only Network

---

## Tasks Completed
- Installed Bind9 DNS server on Ubuntu
- Verified DNS service status using systemctl
- Created a custom forward lookup zone (lab.local)
- Configured zone file with SOA, NS, and A records
- Validated configuration using named-checkconf and named-checkzone
- Restarted Bind9 and confirmed service operation
- Configured Windows VM to use Ubuntu as primary DNS server
- Tested name resolution using nslookup
- Captured successful DNS query and response traffic in Wireshark
- Stopped Bind9 service to simulate DNS failure
- Captured DNS timeout behavior in Wireshark
- Restarted Bind9 and verified restored functionality

---

## Observations (Successful Resolution)
- Windows sent a DNS standard query for server.lab.local
- Ubuntu responded with an A record (192.168.146.130)
- AAAA queries were also observed (IPv6 lookup behavior)
- DNS traffic occurred over UDP port 53
- No external DNS servers were contacted
- Resolution confirmed authoritative zone configuration was working correctly

---

## Observations (Failure Simulation)
- After stopping Bind9, Windows sent repeated DNS queries
- No DNS responses were received from Ubuntu
- Wireshark showed multiple retransmissions
- Windows displayed a DNS timeout error
- Behavior confirmed service-level failure rather than firewall blocking
- Restarting Bind9 restored normal DNS query/response behavior

---

## DNS Behavior Analysis
- NXDOMAIN indicates record does not exist in zone
- Server failure indicates server unable to resolve non-authoritative domain
- Timeout indicates no response from DNS service
- Successful resolution confirmed proper zone configuration and authoritative response

---

## Tools Used
- Bind9 (DNS Server)
- Wireshark
- Windows Command Prompt (nslookup)
- dig (DNS validation tool)
- Ubuntu 24.04 VM
- Windows 10 VM
