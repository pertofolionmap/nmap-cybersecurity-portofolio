# Nmap Scan Phases Lab: Target Enumeration to Version Detection

## 📌 Project Overview
This repository documents my practical lab on understanding the fundamental phases of an Nmap scan, as part of my self-study journey in cybersecurity. The objective of this lab is to demonstrate the step-by-step workflow of Nmap, starting from discovering targets to identifying open ports and running services.

**⚠️ Ethical Disclaimer:** All scanning activities in this lab were strictly performed on my own local machine (`127.0.0.1`). No external IP addresses or unauthorized networks were scanned, adhering to ethical hacking principles.

## 🛠️ Tools Used
*   **Nmap** (Network Mapper) version 7.993
*   **Windows PowerShell** (Command-line interface)

---

## 🔬 Lab Execution & Results

### Phase 1: Target Enumeration
In this phase, the goal is to identify the target without sending aggressive packets. I used the list scan method to enumerate the localhost IP.

*   **Command executed:** `nmap -sL -n 127.0.0.1`
*   **Explanation:** The `-sL` flag performs a list scan (simply listing targets), and `-n` disables reverse DNS resolution to speed up the process. This is the most stealthy phase.

*(Insert your Phase 1 Screenshot Here)*

### Phase 2: Host Discovery
Before scanning ports, Nmap checks if the target is actually online. 

*   **Command executed:** `nmap -sn 127.0.0.1`
*   **Explanation:** The `-sn` flag tells Nmap to perform a ping scan (host discovery) only, without doing a port scan. The output confirmed that the host is "up" with a latency of 0.00032s.

*(Insert your Phase 2 Screenshot Here)*

### Phase 3: Port Scanning & Version Detection
This is the core phase. I performed a SYN scan to find open ports and combined it with version detection to identify the software running on those ports.

*   **Command executed:** `nmap -sS -sV 127.0.0.1`
*   **Explanation:** 
    *   `-sS`: Executes a TCP SYN (half-open) scan for speed and stealth.
    *   `-sV`: Probes the open ports to determine the application name and version.
*   **Findings:**
    *   **Port 135/tcp (msrpc):** Microsoft Windows RPC.
    *   **Port 445/tcp (microsoft-ds):** SMB File Sharing (this is a critical port often targeted by attackers, e.g., EternalBlue exploit).
    *   **Port 5357/tcp (wsdapi):** Web Services on Devices API.
    *   *Other open ports:* 5906/tcp, 5907/tcp.
    *   **Service Info:** Nmap accurately detected the OS as Microsoft Windows based on the TCP/IP fingerprints.

*(Insert your Phase 3 Screenshot Here)*

---

## 🧠 Learning Outcomes
1.  **Understanding the Workflow:** I now understand that an Nmap scan is not just a single action, but a sequence of logical phases (Enumeration -> Discovery -> Port Scan -> Version Detection).
2.  **Reading the Output:** Learned how to interpret the Nmap output, specifically understanding the difference between "open", "closed", and "filtered" states, and identifying high-risk ports like 445 (SMB).
3.  **Command Proficiency:** Gained practical experience in using essential Nmap flags (`-sL`, `-n`, `-sn`, `-sS`, `-sV`) and understanding their impact on the scan results.
4.  **Ethical Boundaries:** Reinforced the importance of conducting scans only on authorized environments (localhost) to avoid legal consequences.
