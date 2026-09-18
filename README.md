# Cybersecurity Incident Response & Vulnerability Assessment Lab

A practical cybersecurity lab documenting threat analysis, log examination, vulnerability scanning workflows, and incident response procedures. Designed to demonstrate defensive security (Blue Team) methodologies, threat identification, and remediation strategies.

---

## Lab Scenarios & Analysis

### 1. Security Log & Authentication Analysis
* **Objective:** Detect unauthorized access attempts and potential brute-force attacks within system logs.
* **Methodology:** Filtered Linux authentication logs (`/var/log/auth.log`) to identify repeated failed SSH login attempts from unrecognized IP addresses.
* **Findings:** Identified a targeted brute-force pattern targeting port 22 originating from an external host.
* **Mitigation:** Recommended implementing IP rate limiting via `fail2ban`, enforcing SSH key-based authentication, and disabling root remote login.

### 2. Network Traffic & Port Scanning Assessment
* **Objective:** Identify active network services and potential entry vectors using host discovery tools.
* **Methodology:** Conducted port scanning and service enumeration using Nmap parameters (`-sV -sC -T4`).
* **Findings:** Discovered unencrypted legacy protocols (HTTP on port 80 and FTP on port 21) exposing credentials in plain text.
* **Mitigation:** Advised enforcing HTTPS via TLS certificates and replacing FTP with SFTP/SSH.

### 3. Vulnerability Management & Risk Remediation
* **Objective:** Evaluate system misconfigurations and prioritize patch management based on Common Vulnerability Scoring System (CVSS) metrics.
* **Deliverable:** Created a structured Incident Response Report outlining threat vectors, impact analysis, and remediation steps aligned with NIST SP 800-61 frameworks.

---

## Tools & Technical Competencies

* **Analysis Tools:** Wireshark, Nmap, Linux CLI utilities (`grep`, `awk`, `tail`, `sed`).
* **Core Concepts:** Incident Response Lifecycle, Log Parsing, TCP/IP Security, Port Scanning, CVSS Scoring.
* **Frameworks & Standards:** NIST Incident Handling Guide (SP 800-61), OWASP Top 10, MITRE ATT&CK.

---

## Sample Incident Log Analysis

Example of isolated malicious log entry parsed during threat investigation:

```text
Sep 18 00:14:22 sec-srv sshd[4012]: Failed password for invalid user admin from 192.168.1.105 port 44821 ssh2
Sep 18 00:14:25 sec-srv sshd[4015]: Failed password for invalid user admin from 192.168.1.105 port 44825 ssh2
Sep 18 00:14:28 sec-srv sshd[4018]: Failed password for invalid user root from 192.168.1.105 port 44830 ssh2
