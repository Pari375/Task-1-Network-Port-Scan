# Task 1: Scan Your Local Network for Open Ports

## Objective
The objective of this task was to perform a TCP SYN scan on the local network using Nmap to identify active hosts and open ports. Additionally, Wireshark was used to observe the network traffic generated during the scan.

---

## Tools Used

- Kali Linux
- Nmap
- Wireshark

---

## Procedure

1. Configured the Kali Linux virtual machine in Bridged Adapter mode.
2. Identified the local network range.
3. Performed a TCP SYN scan using Nmap.
4. Saved the scan results.
5. Captured network traffic using Wireshark.
6. Analyzed discovered services and potential security risks.

---

## Scan Command

```bash
sudo nmap -sS <network>/24 -oN scan_results.txt