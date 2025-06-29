# 🔍 Task 1: Basic Network Scanning with Nmap

## 🎯 Objective

To perform a network scan to identify open ports and services using Nmap on both a remote machine and the local system.

---

## 🛠 Tools Used

- **Operating System**: Kali Linux (running on VMware)
- **Tool**: Nmap v7.94SVN
- **Target**: 
  - Remote IP on same network (using `ifconfig` to find target)
  - Localhost (127.0.0.1)

---

## 🧪 Steps Performed

### ✅ Step 1: Check Network IP
Used `ifconfig` to find available IP addresses on the network.

### ✅ Step 2: Scan a Remote Target
Command used:
```bash
nmap -sV <target-ip>
```
- `-sV` enables version detection of services running on open ports.
- Result showed 5 open ports including Microsoft RPC and VMware authentication services.

### ✅ Step 3: Scan Localhost
Command used:
```bash
nmap -sV localhost
```
- Result showed all 1000 TCP ports on localhost were closed/reset.

### ✅ Step 4: Save Output
```bash
nmap -sV <target-ip> > nmap_scan_results.txt
```
- This saves the result of the remote scan to a `.txt` file.

---

## 📄 Output Summary

### 📌 Remote IP Scan Findings:
| Port | State | Service       | Version                            |
|------|-------|----------------|-------------------------------------|
| 135  | open  | msrpc          | Microsoft Windows RPC              |
| 139  | open  | netbios-ssn    | Microsoft Windows netbios-ssn     |
| 445  | open  | microsoft-ds   | ?                                  |
| 902  | open  | ssl/vmware-auth| VMware Authentication Daemon      |
| 912  | open  | vmware-auth    | VMware Authentication Daemon      |

### 🔍 Analysis:
- Ports like 135, 139, 445 indicate Windows services, often targeted by malware.
- VMware-auth services reveal the host is likely a virtualized environment.
- Open ports provide insight into possible vulnerabilities and system roles.

---

## 🖼️ Screenshots

### 🔸 Remote IP Scan
![Remote Nmap Scan](./screenshots/nmap_output1.png)

### 🔸 Localhost Scan
![Localhost Nmap Scan](./screenshots/nmap_output2.png)

---

## 📂 Files Included

- `nmap_scan_results.txt` – Text output of Nmap scan on the remote target
- `screenshots/` – Contains:
  - `nmap_output1.png` (Remote IP scan)
  - `nmap_output2.png` (Localhost scan)
- `README.md` – This report

---

## 📚 References

- [Nmap Official Website](https://nmap.org)
- [Nmap Cheat Sheet](https://nmap.org/book/man-briefoptions.html)

---

## ✅ Internship Task Completion Status
✔️ Task 1: Completed  
