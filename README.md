# nmap‑cybersecurity‑portofolio

## 🎯 Project Description
This portfolio documents my self‑study journey in cybersecurity and ethical network scanning using Nmap / Zenmap. This project is built to strengthen my portfolio for IT‑major university applications (Ritsumeikan University / Kyoto University) and the MEXT scholarship selection. All scanning activities will be performed only on my own local‑host lab (127.0.0.1) to follow ethical‑hacking principles. I will never scan external IP‑addresses or servers without written permission.

## 🛠️ Tools Used
‑ Nmap (Zenmap GUI) – Network port scanner
‑ Windows Command Prompt / Zenmap terminal output

## 🔍 Scan Information
✅ Scan Target: 127.0.0.1 (Own Lab Environment)
✅ Scan Command: nmap ‑sV 127.0.0.1
✅ Scan Goal: Identify open ports, detect running services & service versions, analyze basic network‑security status

## 📊 Scan Result Summary
✅ Host Status: Host is Up
✅ Open Ports & Services:
1. 135/tcp open ‑ msrpc (Microsoft RPC)
2. 445/tcp open ‑ microsoft‑ds (SMB File Sharing)
3. 5357/tcp open ‑ wsdapi (Windows Web‑Services‑on‑Devices)
✅ Scan Duration: 12,50 seconds

## 🖼️ Screenshot of Nmap Scan
![Nmap Localhost Scan Result]
(https://github.com/pertofolionmap/nmap-cybersecurity-portofolio/raw/main/Cuplikan%20layar%202026-11-17%20205630.png)

## 📚 Learning Outcomes
1. Understand the basic concept of port scanning
2. Learn how to interpret Nmap output, open ports, and service‑version data
3. Understand ethical‑hacking boundaries and cybersecurity legal rules
4. Build analytical thinking required for university‑level IT‑engineering studies

## 🎓 Portfolio Goal
Develop fundamental cybersecurity knowledge to prepare for IT‑major admission and MEXT scholarship requirements
Nmap Scan Phases Lab: Target Enumeration to Version Detection
📌 Project Overview
This repository documents my practical lab on understanding the fundamental phases of an Nmap scan, as part of my self-study journey in cybersecurity. The objective of this lab is to demonstrate the step-by-step workflow of Nmap, starting from discovering targets to identifying open ports and running services.

⚠️ Ethical Disclaimer: All scanning activities in this lab were strictly performed on my own local machine (127.0.0.1). No external IP addresses or unauthorized networks were scanned, adhering to ethical hacking principles.
---
# 📑 Phase 2 & Phase 3 ‑ Detailed Port Analysis & Security‑Risk Assessment                                                                                                                                                                                                                       
🛠️ Tools Used
Nmap (Network Mapper) version 7.993
Windows PowerShell (Command-line interface)
🔬 Lab Execution & Results
Phase 1: Target Enumeration
In this phase, the goal is to identify the target without sending aggressive packets. I used the list scan method to enumerate the localhost IP.

Command executed: nmap -sL -n 127.0.0.1
Explanation: The -sL flag performs a list scan (simply listing targets), and -n disables reverse DNS resolution to speed up the process. This is the most stealthy phase.
(Insert your Phase 1 Screenshot Here)

Phase 2: Host Discovery
Before scanning ports, Nmap checks if the target is actually online.

Command executed: nmap -sn 127.0.0.1
Explanation: The -sn flag tells Nmap to perform a ping scan (host discovery) only, without doing a port scan. The output confirmed that the host is "up" with a latency of 0.00032s.
(Insert your Phase 2 Screenshot Here)

Phase 3: Port Scanning & Version Detection
This is the core phase. I performed a SYN scan to find open ports and combined it with version detection to identify the software running on those ports.

Command executed: nmap -sS -sV 127.0.0.1
Explanation:
-sS: Executes a TCP SYN (half-open) scan for speed and stealth.
-sV: Probes the open ports to determine the application name and version.
Findings:
Port 135/tcp (msrpc): Microsoft Windows RPC.
Port 445/tcp (microsoft-ds): SMB File Sharing (this is a critical port often targeted by attackers, e.g., EternalBlue exploit).
Port 5357/tcp (wsdapi): Web Services on Devices API.
Other open ports: 5906/tcp, 5907/tcp.
Service Info: Nmap accurately detected the OS as Microsoft Windows based on the TCP/IP fingerprints.
*(Insert your Phase 3 Screenshot Here)*https://github.com/pertofolionmap/nmap-cybersecurity-portofolio/blob/main/phases-lab/Cuplikan%20layar%202026-11-18%20110618.png?raw=true

🧠 Learning Outcomes
Understanding the Workflow: I now understand that an Nmap scan is not just a single action, but a sequence of logical phases (Enumeration -> Discovery -> Port Scan -> Version Detection).
Reading the Output: Learned how to interpret the Nmap output, specifically understanding the difference between "open", "closed", and "filtered" states, and identifying high-risk ports like 445 (SMB).
Command Proficiency: Gained practical experience in using essential Nmap flags (-sL, -n, -sn, -sS, -sV) and understanding their impact on the scan results.
Ethical Boundaries: Reinforced the importance of conducting scans only on authorized environments (localhost) to avoid legal consequences.
