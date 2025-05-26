# Wireshark Packet Capture Notes – Task 1 (Nmap Scan)

### Interface: wlan0 (Wi-Fi)

## Steps Taken:

1. Launched Wireshark and selected the 'wlan0' interface to begin packet capture.
2. Started the capture before initiating the Nmap scan.
3. Ran the following command in the terminal to perform a TCP SYN scan on the subnet:
   sudo nmap -sS 192.168.255.28/24
4. Let the scan run for about 6.3 seconds until it completed.
5. Stopped the capture and applied a display filter to analyze the scan traffic.

## Filter Used:

To focus on DNS-related traffic, I applied the following display filter:
tcp.port == 53

## What I Observed:

- Wireshark captured a total of 4539 packets during the scan.
- After applying the filter, I found that Nmap sent a SYN packet to port 53 on 192.168.255.108.
- That host responded with a SYN-ACK, which confirms that port 53 is open.
- A reset (RST) was sent back from the scanner, which is expected behavior in a stealth scan (Nmap -sS).
- Other IPs in the subnet replied with RST packets, meaning their ports were closed.
- No unexpected or suspicious traffic appeared in the filtered results.

## Conclusion:

The capture clearly showed how Nmap performs a SYN scan. Using the filter 'tcp.port == 53'. 
I was able to confirm that port 53 on 192.168.255.108 is open based on the classic SYN → SYN-ACK → RST sequence.
Wireshark helped verify that the scan worked correctly and showed expected responses from other hosts with closed ports.
