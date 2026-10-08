# Linux Cheat Sheet

## 1. Navigation Commands

### Show current directory
pwd

### List files
ls

### List files with details
ls -l

### Show hidden files
ls -la

### Change directory
cd directory_name

### Go to parent directory
cd ..


## 2. File and Directory Commands

### Create a directory
mkdir folder_name

### Create a file
touch file.txt

### Copy a file
cp file.txt backup.txt

### Move or rename a file
mv old.txt new.txt

### Delete a file
rm file.txt


## 3. File Permissions

### View permissions
ls -l

### Change permissions
chmod 755 file.sh

### Change ownership
chown user:user file.txt


## 4. Package Management

### Update packages
sudo apt update

### Upgrade packages
sudo apt upgrade

### Install a package
sudo apt install package-name

### Remove a package
sudo apt remove package-name


## 5. Networking Commands

### Show IP address
ip addr

### Test connectivity
ping 192.168.100.20

### Show routing information
ip route

### Show network connections
ss -tuln

### Trace network path
traceroute 192.168.100.20


## 6. File Reading Commands

### Display file contents
cat file.txt

### View file page by page
less file.txt

### Show first lines
head file.txt

### Show last lines
tail file.txt


## 7. Searching Commands

### Search text in a file
grep "text" file.txt

### Find a file
find /path -name "filename"


## 8. System Commands

### Show current user
whoami

### Show system information
uname -a

### Show running processes
ps aux

### Show command history
history

### Clear terminal
clear

### Open manual/help
man command


## 9. Cybersecurity Lab Commands

### Check Kali Linux IP configuration
ip addr

### Test connection to Metasploitable2
ping -c 4 192.168.100.20

### Nmap scan
nmap 192.168.100.20

### Check SSH service with Netcat
nc -zv 192.168.100.20 22

### Check OpenSSL version
openssl version


## 10. Lab Network

Kali Linux:
IP Address: 192.168.100.10
Interface: eth1
Network: cyberlab

Metasploitable2:
IP Address: 192.168.100.20
Interface: eth0
Network: cyberlab


## 11. Security Tools

Nmap - Network scanning
Wireshark - Packet capture and analysis
Burp Suite - Web security testing
Netcat - Network/service testing
OpenSSL - Cryptographic operations


## Important Note

These commands were practiced as part of the controlled cybersecurity
laboratory environment for educational and authorized security testing.
