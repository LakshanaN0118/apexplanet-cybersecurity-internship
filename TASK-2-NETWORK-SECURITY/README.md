# Task 2 - Network Security and Scanning

## Overview

Task 2 focused on network security, reconnaissance, network scanning, vulnerability assessment, packet analysis, and basic firewall configuration in a controlled virtual laboratory environment.

All security testing was performed only against controlled laboratory systems.

## Lab Environment

Attacker / Security Testing Machine:
- Kali Linux

Target System:
- Vulnerable test machine
- Target IP: 192.168.100.20

## Objectives

The main objectives of Task 2 were:

- Understand passive and active reconnaissance
- Practice WHOIS and NSLookup
- Understand Google Dorking and Shodan
- Perform Ping Sweep and Banner Grabbing
- Perform TCP and UDP scans using Nmap
- Perform service version detection
- Perform operating system detection
- Create network scan reports
- Perform vulnerability assessment using OpenVAS / Greenbone
- Analyze vulnerability reports based on severity
- Analyze HTTP, FTP and DNS traffic using Wireshark
- Study SYN flood behavior in a controlled environment
- Configure basic iptables firewall rules
- Understand how firewall rules can reduce network exposure

## Reconnaissance

### Passive Reconnaissance

The following passive reconnaissance techniques were studied:

- WHOIS
- NSLookup
- Google Dorking
- Shodan

### Active Reconnaissance

The following active reconnaissance techniques were studied:

- Ping Sweep
- Banner Grabbing

## Nmap Scanning

Nmap was used for network discovery and security assessment.

The following scanning techniques were covered:

- TCP SYN Scan
- UDP Scan
- Service Version Detection
- Operating System Detection
- Combined Nmap Scan

Target:

192.168.100.20

## Vulnerability Assessment

OpenVAS / Greenbone Vulnerability Scanner was configured in the Kali Linux laboratory environment.

The vulnerability assessment process included:

1. Configure the target
2. Create a scan task
3. Start the scan
4. Wait for the assessment to complete
5. Open the generated report
6. Analyze vulnerabilities based on severity

Vulnerability severity categories studied:

- Critical
- High
- Medium
- Low

## Wireshark Packet Analysis

Wireshark was used to capture and analyze network traffic.

The following traffic types were studied:

- HTTP
- FTP
- DNS
- TCP
- UDP
- ARP
- ICMP

HTTP, FTP and DNS traffic were analyzed using appropriate display filters.

## SYN Flood Study

SYN flood behavior was studied using hping3 in the controlled laboratory environment.

The activity focused on understanding:

- TCP SYN packets
- Half-open connections
- Network traffic patterns
- Effects on a target
- Detection through packet analysis

Wireshark was used to analyze SYN traffic.

## Firewall Configuration

Basic Linux firewall rules were studied using iptables.

The task covered:

- Allowing required ports
- Blocking unnecessary ports
- Restricting access to services
- Reducing attack surface

Example firewall rule:

sudo iptables -A INPUT -p tcp --dport 23 -j DROP

This rule demonstrates how unwanted access to a service port can be blocked.

## Security Findings

The assessment highlighted several network-security concerns:

- Multiple open ports increase attack surface
- FTP may transmit credentials and data without encryption
- Telnet provides unencrypted remote access
- SMB exposure may increase security risk
- HTTP provides unencrypted web communication
- Outdated services may contain known vulnerabilities
- Unrestricted network access increases exposure
- Weak monitoring may allow attacks to go unnoticed

## Recommendations

- Disable unnecessary services
- Replace Telnet with SSH
- Replace unsecured FTP with SFTP or FTPS
- Apply regular security patches
- Configure firewalls
- Use encrypted communication
- Monitor network traffic
- Perform regular vulnerability scans
- Prioritize Critical and High severity vulnerabilities

## Ethical Considerations

All reconnaissance, scanning and vulnerability-assessment activities were performed only against authorized laboratory systems.

The techniques were practiced in a controlled environment to avoid affecting real organizations or unauthorized systems.

## Conclusion

Task 2 provided practical experience in network security assessment, including reconnaissance, scanning, vulnerability analysis, packet inspection and basic defensive controls.

The activities demonstrated how exposed services can increase attack surface and how vulnerability assessment, traffic analysis and firewall rules can help improve network security.
