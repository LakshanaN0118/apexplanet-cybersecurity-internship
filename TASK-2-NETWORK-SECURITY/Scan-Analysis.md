# Task 2 - Network Scan Analysis

## Target

Target IP Address:

192.168.100.20

The target was a vulnerable test machine used only within the controlled cybersecurity laboratory.

## 1. Host Discovery

Ping Sweep was studied for identifying active hosts in a network range.

Command:

nmap -sn 192.168.100.0/24

Purpose:

The command performs host discovery without conducting a full port scan.

## 2. TCP SYN Scan

A TCP SYN scan was performed using the Nmap -sS option.

Command:

sudo nmap -sS 192.168.100.20

Purpose:

The SYN scan helps identify open TCP ports by analyzing responses to SYN packets.

Typical responses include:

SYN/ACK - Port is likely open

RST - Port is likely closed

No response / filtered response - Port may be filtered

## 3. UDP Scan

UDP scanning was performed using the Nmap -sU option.

Command:

sudo nmap -sU 192.168.100.20

Purpose:

UDP scanning helps identify services operating over UDP.

Examples of UDP services include:

- DNS
- DHCP
- SNMP
- TFTP

## 4. Service Version Detection

Nmap service version detection was performed using the -sV option.

Command:

sudo nmap -sV 192.168.100.20

This can identify:

- Service name
- Software version
- Product information

Service version information can be compared with known vulnerabilities during security assessment.

## 5. Operating System Detection

Operating system detection was studied using the Nmap -O option.

Command:

sudo nmap -O 192.168.100.20

OS detection analyzes network responses and compares them with known operating-system fingerprints.

## 6. Combined Scan

Multiple Nmap techniques were combined in a single scan.

Command:

sudo nmap -sS -sV -O 192.168.100.20

This combines:

- TCP SYN scanning
- Service/version detection
- Operating system detection

## 7. Scan Findings

The controlled target system was found to be active.

Multiple exposed services were identified.

Important services identified included:

- FTP - Port 21
- SSH - Port 22
- Telnet - Port 23
- SMTP - Port 25
- DNS - Port 53
- HTTP - Port 80
- SMB/NetBIOS - Ports 139/445
- RPC-related services - Various ports

The scan also showed that a large number of ports were closed, while several services were accessible.

## 8. Security Impact

Multiple exposed services can increase the attack surface of a system.

Each exposed service should be reviewed to determine:

- Whether the service is necessary
- Whether it is securely configured
- Whether it is properly patched
- Whether access should be restricted

## 9. Recommended Actions

- Disable unnecessary services
- Replace insecure protocols with secure alternatives
- Apply regular security updates
- Restrict access to required services
- Use firewall rules to reduce unnecessary exposure
- Perform regular vulnerability assessments

## 10. Ethical Consideration

All scanning activities were performed only against the authorized controlled laboratory target.

The techniques documented here are intended for authorized cybersecurity assessment and educational laboratory use.
