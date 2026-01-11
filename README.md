# Penetration Testing Labs (Challenges 1–4)

## Course: Network Security / Ethical Hacking  
## Lab Type: Practical Penetration Testing Assessment  
## Tools Used: DVWA, Wireshark, smbclient, Linux CLI  
## Environment: Kali Linux  

---

## Overview

This repository documents a series of controlled penetration testing labs conducted in an isolated environment.  
The objective of the labs was to identify, exploit, and document common security vulnerabilities across web applications, file services, and network traffic, and to propose appropriate remediation strategies.

All testing was performed **strictly within scope** and **for educational purposes only**.

---

## Scope of Assessment

### Networks
- `10.5.5.0/24`
- `192.168.0.0/24`

### Target Systems
- `10.5.5.12` — Web Application Server (DVWA)
- `192.168.0.10` — Linux Host
- `10.5.5.14` — SMB File Server
- `10.5.5.11` — Web Server identified via PCAP analysis

---

## Lab Challenges Summary

### Challenge 1: SQL Injection
**Objective:**  
Exploit a SQL injection vulnerability to retrieve user credentials and access a protected file.

**Key Findings:**
- Unsanitized SQL input allowed credential extraction
- Bob Smith’s account was compromised
- Unauthorized access to a protected system was achieved

**Flag Code: 8748wf8J**  


---

### Challenge 2: Web Server Directory Listing
**Objective:**  
Identify misconfigured web directories allowing file enumeration.

**Key Findings:**
- Directory indexing enabled on Apache server
- Sensitive files accessible via browser

**Discovered Directories:**
- `/config`
- `/docs`

**Flag Code: aWe-4975**  


---

### Challenge 3: Open SMB Server Shares
**Objective:**  
Identify unsecured SMB shares accessible to anonymous users.

**Key Findings:**
- SMB server allowed anonymous authentication
- Sensitive files exposed via public share

**Accessible Share:**
- `print$`

**Flag Code: NWs39691**  


---

### Challenge 4: PCAP Analysis and Clear-Text Exposure
**Objective:**  
Analyze captured network traffic to identify sensitive information transmitted in clear text.

**Key Findings:**
- HTTP traffic transmitted without encryption
- Directory listing enabled
- Sensitive XML file exposed

**Target Directory:**
- `/data`

**Flag Code: 21z-1478K**  


---

## Documentation

This repository includes the following documents:

- **Technical Penetration Test Report**  
  Detailed step-by-step findings, challenges faced, and remediation recommendations.

- **Executive Summary Report**  
  High-level overview of risks and business impact.

---

## Remediation Highlights

- Use prepared statements to prevent SQL injection
- Disable directory listing on web servers
- Restrict SMB access and disable anonymous shares
- Enforce HTTPS and encrypted communication protocols

---

## Ethical Notice

All activities documented in this repository were conducted:
- In a controlled lab environment
- Within defined scope
- For academic and educational purposes only

Unauthorized testing of systems without permission is illegal and unethical.

---

## Author

Student: *Jude Stephen Oyiborhoro*  
Course: *Ethical Hacker*  
Institution: *ParoCyber in Conjuction with Cisco Networking Academy *  

---

## License

This project is provided for **educational use only**.
