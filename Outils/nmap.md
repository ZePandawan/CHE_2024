# NMAP Cheat-Sheet

## Target specification

| Command | Description |
|:---------|:--------|
| ```nmap -h```| NMAP help menu |
| ```nmap 192.168.1.1```| Scan a single IP |
| ```nmap 192.168.1.1 192.168.2.1```| Scan specifics IP |
| ```nmap 192.168.1.1-255```| Scan a range of IP |
| ```nmap google.fr```| Scan a domain |
| ```nmap 192.168.1.0/24```| Scan using CIDR notation |
| ```nmap -iL targets.txt```| Scan targets from a file |
| ```nmap -iR 100```| Scan 100 random hosts |
| ```nmap 192.168.1.0/24 -exclude 192.168.1.1```| Scan the range except 192.168.1.1 |

## NMAP scan techniques

| Command | Description |
|:---------|:--------|
| ```nmap 192.168.1.1 -sS```| TCP SYN port scan (Default) |
| ```nmap 192.168.1.1 -sT```| TCP connect port scan (Default without root privilege) |
| ```nmap 192.168.1.1 -sU```| UDP port scan |
| ```nmap 192.168.1.1 -sA```| TCP ACK port scan |
| ```nmap 192.168.1.1 -sW```| TCP Window port scan |
| ```nmap 192.168.1.1 -sM```| TCP Mainon port scan |

## Host Discovery

| Command | Description |
|:---------|:--------|
| ```nmap 192.168.1.1-3 -sL```| No scan. List targets only |
| ```nmap 192.168.1.1/24 -sn```| Disable port scanning. Host discorvey only |
| ```nmap 192.168.1.1-5 -Pn```| Disable host discovery.Port scan only |
| ```nmap 192.168.1.1-5 -PS22-25,80```| TCP SYN discovery on port x. Port 80 by default |
| ```nmap 192.168.1.1-5 -PA22,25-80```| TCP ACK discovery on port x. Port 80 by default |
| ```nmap 192.168.1.1-5 -PU53```| UDP discovery on port x. Port 40125 by default |
| ```nmap 192.168.1.1-1/24 -PR```| ARP discovery on local network |
| ```nmap 192.168.1.1 -n```| Never do DNS resolution |

## Port Specification

| Command | Description |
|:---------|:--------|
| ```nmap 192.168.1.1 -p 21```| Port scan for port x |
| ```nmap 192.168.1.1 -p 21-100```| Port range |
| ```nmap 192.168.1.1 -p U:53,T:21-25,80```| Port scan multiple TCP and UDP ports |
| ```nmap 192.168.1.1 -p-```| Port scan all ports |
| ```nmap 192.168.1.1 -p http,https```| Port scan from service name |
| ```nmap 192.168.1.1 -F```| Fast port scan (100 ports) |
| ```nmap 192.168.1.1 -top-ports 2000```| Port scan the top x ports |
| ```nmap 192.168.1.1 -p-65535```| Leaving off initial port in range makes the scan start at port 1 |
| ```nmap 192.168.1.1 -p0-```| Leaving off ending port in range makes the scan go through to port 65535 |

## Service and Version Detection

| Command | Description |
|:---------|:--------|
| ```nmap 192.168.1.1 -sV```| Attempts to determine the version of the service running on port |
| ```nmap 192.168.1.1 -sV -version-intensity 8```| Intensity level from 0 to 9. Higher number increases possibility of correctness |
| ```nmap 192.168.1.1 -sV -version-light```| Enable light mode. Lower possibility of correctness. Faster |
| ```nmap 192.168.1.1 -sV -version-all```| Enable intensity level 9. Higher possibility of correctness. Slower |
| ```nmap 192.168.1.1 -A```| Enables OS detection, version detection, script scanning, and traceroute |

## Timing and Performance

| Command | Description |
|:---------|:--------|
| ```nmap 192.168.1.1 -T0```| Paranoid (0) Intrusion Detection System evasion |
| ```nmap 192.168.1.1 -T1```| Sneaky (1) Intrusion Detection System evasion |
| ```nmap 192.168.1.1 -T2```| Polite (2) slows down the scan to use less bandwidth and use less target machine resources |
| ```nmap 192.168.1.1 -T3```| Normal (3) which is default speed |
| ```nmap 192.168.1.1 -T4```| Aggressive (4) speeds scans; assumes you are on a reasonably fast and reliable network |
| ```nmap 192.168.1.1 -T5```| Insane (5) speeds scan; assumes you are on an extraordinarily fast network |