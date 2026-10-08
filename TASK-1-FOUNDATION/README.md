# Task 1 - Foundation & Environment Setup

## Overview

This task focused on establishing a basic cybersecurity laboratory
environment and building fundamentals in cybersecurity, Linux,
networking, cryptography and security tools.

## Lab Environment

- VirtualBox
- Kali Linux
- Metasploitable2
- Isolated `cyberlab` network

## Network Configuration

| Machine | Interface | IP Address |
|---|---|---|
| Kali Linux | eth1 | 192.168.100.10 |
| Metasploitable2 | eth0 | 192.168.100.20 |

## Activities Completed

- Cybersecurity fundamentals
- CIA Triad
- Threat types and attack vectors
- Linux fundamentals
- Networking fundamentals
- Cryptography basics
- OpenSSL
- Nmap
- Wireshark
- Burp Suite
- Netcat

## Testing

### Connectivity

```bash
ping -c 4 192.168.100.20
