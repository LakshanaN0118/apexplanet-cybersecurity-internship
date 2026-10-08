# Task 1 Lab Notes

## Objective

The objective of Task 1 was to establish a basic cybersecurity laboratory environment and practice fundamental cybersecurity concepts and tools in a controlled and isolated environment.

## Lab Environment

The laboratory was created using Oracle VirtualBox.

The environment consisted of:

- Kali Linux - Attacker and security-testing machine
- Metasploitable2 - Intentionally vulnerable target machine
- cyberlab - Isolated internal network

## Network Configuration

Kali Linux:
IP Address: 192.168.100.10
Interface: eth1
Network: cyberlab

Metasploitable2:
IP Address: 192.168.100.20
Interface: eth0
Network: cyberlab

## Kali Linux Setup

Kali Linux was configured in VirtualBox.

The first network adapter was configured using NAT.

The second network adapter was connected to the isolated cyberlab internal network.

## Metasploitable2 Setup

Metasploitable2 was configured as the intentionally vulnerable target machine.

Its network adapter was connected only to the cyberlab internal network.

## Connectivity Testing

Connectivity between Kali Linux and Metasploitable2 was tested using the ping command.

Command used:

ping -c 4 192.168.100.20

The ping test successfully confirmed communication between the two machines.

## Nmap Scanning

Nmap was used to perform a network scan of the Metasploitable2 target.

Command used:

nmap 192.168.100.20

The scan identified several services, including:

- FTP
- SSH
- Telnet
- HTTP
- MySQL
- PostgreSQL
- VNC

## Wireshark

Wireshark was used for packet capture and network traffic analysis.

ICMP traffic generated during the connectivity test was observed using the ICMP display filter.

Filter used:

icmp

## Burp Suite

Burp Suite was launched and explored as part of the security testing activities.

It was used for understanding HTTP/HTTPS request and response analysis.

## Netcat

Netcat was used to check the SSH service on the Metasploitable2 machine.

Command used:

nc -zv 192.168.100.20 22

The test confirmed that SSH port 22 was open.

## Tools Practiced

- Nmap
- Wireshark
- Burp Suite
- Netcat
- OpenSSL

## Results

The cybersecurity laboratory environment was successfully configured.

Communication between Kali Linux and Metasploitable2 was verified.

Basic network scanning, packet capture, web security tool familiarization, and network service testing were completed in the controlled laboratory environment.

## Conclusion

Task 1 provided practical experience with cybersecurity fundamentals, Linux, networking, cryptography, and commonly used security tools in an isolated laboratory environment.
