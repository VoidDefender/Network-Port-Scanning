# Task 1 - Network Port Scanning | Cyber Security Internship

## Objective:
Perform a network scan on the local subnet to identify active devices and check for open TCP ports using Nmap. This helps in understanding the exposure level of devices in a network.

## Tool Used:
- **Nmap v7.95**
- Command used:
  ```bash
  sudo nmap -sS 192.168.255.28/24
- wireshark 

Scan Output Summary:

Nmap scan report for 192.168.255.96
Host is up (0.044s latency).
All 1000 scanned ports on 192.168.255.96 are in ignored states.
Not shown: 1000 closed tcp ports (reset)
MAC Address: 12:54:9D:33:76:B4 (Unknown)

Nmap scan report for 192.168.255.108
Host is up (0.0062s latency).
Not shown: 999 closed tcp ports (reset)
PORT     STATE  SERVICE
53/tcp   open   domain
MAC Address: B2:32:8D:79:44:AE (Unknown)

Nmap scan report for 192.168.255.28
Host is up (0.0000010s latency).
All 1000 scanned ports on 192.168.255.28 are in ignored states.
Not shown: 1000 closed tcp ports (reset)

Nmap done: 256 IP addresses (3 hosts up) scanned in 6.31 seconds

Live Hosts and Port Status:

1. 192.168.255.96

Status: Host is up

Open Ports: None

All 1000 ports were closed (reset)



2. 192.168.255.108

Status: Host is up

Open Port:

53/tcp open domain (DNS service)


MAC Address: B2:32:8D:79:44:AE



3. 192.168.255.28 (my own machine)

Status: Host is up

Open Ports: None

All 1000 ports were closed (reset)




Observations:

Only one open port was found on the entire subnet (Port 53 on 192.168.255.108).

Port 53 is typically used for DNS services. If this device is not meant to act as a DNS server, this could be a potential security risk.

All other devices either had no open ports or had firewalls blocking port responses.


Security Insights:

Open ports can be exploited by attackers to gain unauthorized access.

Regular scanning helps detect unnecessary services running on devices.

It's good practice to close unused ports and run firewalls to reduce attack surface.


Files Included:

nmap_scan_results.txt: Raw output from Nmap scan.

README.md: Documentation and analysis of the scan.


Learning Outcomes:

Learned how to use Nmap for TCP SYN scanning.

Gained basic network reconnaissance skills.

Understood how to identify open ports and assess service exposure risks.
