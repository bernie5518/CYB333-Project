# Vulnerability Scanner

## Overview
A Python-based lightweight vulnerability scanner for identifying basic security vulnerabilities in web applications and network infrastructure.

### Features
- **Port Scanning**: Identifies open ports.
- **SQL Injection Testing**: Checks for SQL Injection vulnerabilities.
- **XSS Detection**: Detects Cross-Site Scripting (XSS) vulnerabilities.
- **HTTP Header Analysis**: Checks for missing security headers.
- **Directory Enumeration**: Attempts to locate common directories.
- **SSL/TLS Validation**: Validates or bypasses self-signed certificates.

---

## Prerequisites
- **Python 3.7+**
- **pip** (Python package manager)
- Self-signed certificate for SSL validation (optional)

---

## Setup and Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/yourusername/vulnerability-scanner.git
   cd vulnerability-scanner
   
2. Install dependancies
   ```bash
   pip install requests urllib3

3. (Optional) Export self-signed certificates:
    ```bash
    echo | openssl s_client -connect <TARGET_IP>:443 -showcerts > server_cert.crt
    sudo mv server_cert.crt /etc/ssl/certs/server_cert.crt
    sudo chmod 644 /etc/ssl/certs/server_cert.crt

---
  
How to Run

1. Run the script:
   ```bash
   python3 vulnerability_scanner.py

2. Provide inputs:
  Target IP address or domain
  Full URL of the target web application

3. Results:
  Displayed in the terminal.
  Saved to results.txt in the current directory.

---

Example Output
  
  [2024-06-17 15:00:00] - [+] Scanning Ports...
  [2024-06-17 15:00:01] - Port 443: OPEN
  
  [2024-06-17 15:00:10] - [+] Testing for SQL Injection...
  No SQL Injection vulnerabilities detected.
  
  [2024-06-17 15:00:15] - [+] Checking HTTP Security Headers...
  Missing headers: Content-Security-Policy, X-Frame-Options

---

Customization

  Ports: Update DEFAULT_PORTS in the script.
  Payloads: Modify test_sql_injection() or test_xss() functions.
  Directories: Add paths to COMMON_DIRS.


