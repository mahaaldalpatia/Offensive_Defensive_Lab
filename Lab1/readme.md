# Simulated Ethical Hacking with Metasploit

## Aim

Perform a safe exploitation and vulnerability assessment of a virtual
machine using Metasploit and security scanning tools to understand
ethical hacking procedures.

## Objective

-   Identify the target virtual machine on the lab network.
-   Check connectivity between Kali Linux and the target.
-   Scan the target for open ports and running services.
-   Perform vulnerability assessment using Nessus.
-   Understand the basic workflow of ethical hacking in an isolated lab.

## Lab Environment

-   **Attacker:** Kali Linux
-   **Target:** Metasploitable 2
-   **Tools:** Nmap, Nessus, Metasploit Framework
-   **Network:** Isolated virtual machine/lab network

## Methodology

### 1. Check Network Configuration

The `ifconfig` command was used to identify the network interfaces and
IP addresses of the Kali Linux machine.

### 2. Check Target Connectivity

The `ping` command was used to verify that the target machine was
reachable.

### 3. Scan Open Ports and Services

Nmap service detection was used to identify open ports and running
services on the target.

### 4. Perform OS and Service Detection

Nmap was also used with OS detection to gather additional information
about the target.

### 5. Vulnerability Assessment

Nessus was used to scan the target and identify security vulnerabilities
along with their severity levels.

## Screenshots

### 1. Nmap Service Scan

![Nmap Service Scan](screenshots/01-nmap-scan.png)

### 2. Network Configuration

![Network Configuration](screenshots/02-ifconfig.png)

### 3. Ping Connectivity Test

![Ping Connectivity Test](screenshots/03-ping.png)

### 4. Nmap OS and Service Detection

![Nmap OS Scan](screenshots/04-nmap-os-scan.png)

### 5. Nessus Vulnerability Scan Results

![Nessus Results](screenshots/05-nessus-results.png)

## Result

The target virtual machine was identified and scanned successfully.
Multiple open services were detected by Nmap, and Nessus reported
vulnerabilities with different severity levels.

## Key Learning

-   Nmap can identify open ports and services.
-   Ping can be used to test basic network connectivity.
-   Nessus helps identify and classify vulnerabilities.
-   Ethical hacking should be performed only on authorized systems.
-   Vulnerability assessment is an important step before controlled
    exploitation.

## Conclusion

The experiment demonstrated a basic ethical hacking workflow using
network discovery, service enumeration, and vulnerability assessment in
a controlled virtual lab environment.

## Safety Note

This experiment is intended only for an isolated and authorized
cybersecurity lab environment such as Metasploitable 2. Do not scan or
exploit systems without explicit permission.
