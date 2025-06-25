# localNetworkScan

````markdown
Nmap Network Scan Report – Task 1

Scan Date: June 23, 2025  
Target: `192.168.1.143/24`  
Command Used:
```bash
nmap -sS -sV -oN Task1_scan.txt 192.168.1.143/24

Summary of Results (Host: 192.168.1.1)

| Port     | State | Service | Version                                      |
| -------- | ----- | ------- | -------------------------------------------- |
| 22/tcp   | open  | SSH     | Dropbear sshd 2020.80 (protocol 2.0)         |
| 23/tcp   | open  | Telnet  | BusyBox telnetd 1.14.0 or later              |
| 53/tcp   | open  | DNS     | dnsmasq 2.85                                 |
| 80/tcp   | open  | HTTP    | No version info detected                     |
| 1900/tcp | open  | UPNP    | Portable SDK for UPnP devices 1.6.19 (Linux) |



Security Analysis

Port 22 – SSH (Dropbear 2020.80)

Usage: Secure shell access, likely for remote admin.
Security Note:Dropbear is common on embedded devices.
Action: Ensure strong passwords or key-based authentication. Regularly update.

Port 23 – Telnet (BusyBox 1.14.0+)

Usage: Legacy remote access protocol.
Risk: Highly insecure. Transmits credentials in plaintext.
Action:'Disable Telnet.' Use SSH instead.

 Port 53 – DNS (dnsmasq 2.85)

Usage:  Local DNS and possibly DHCP.
Security Note:Older versions of dnsmasq have vulnerabilities including cache poisoning.
Action: Update to latest version. Disable external DNS access if not required.


Port 80 – HTTP (Unknown Version)

Usage: Likely web interface for device configuration.
Action: Visit 'http://192.168.1.1' to check for login panels. Use HTTPS if available. Disable if unused.

 Port 1900 – UPNP (v1.6.19)

Usage: Device discovery and control (mostly IoT).
Risk: Known for 'DDoS amplification' and 'internal device exposure'.
Action: Disable UPnP if not needed. Block this port on external firewalls.

Recommendations

'Disable' unnecessary services (especially Telnet and UPnP).
'Update' all services to their latest versions.
'Restrict access' to admin interfaces (e.g., SSH, HTTP).
'Use a firewall' to segment IoT or embedded devices from sensitive networks.

Output File

 Scan results saved to: 'Task1_scan.txt'

Notes

 This scan was conducted in a controlled internal network for educational/cybersecurity analysis.
 No unauthorized access or disruption was performed.                 
