# FUTURE_CS_01
---
# WEB APPLICATION SECURITY TESTING (TASK 01)
---
## Step by step with guidelines and procedures 
Task: Conducting a security test on a sample web application to identify vunerabilities like SQL Injection, XSS and authentication flaws.
Skills Gained: Web application security, ethical hacking, penetration testing.
Tools: OWASP ZAP, Burp suite, SQL Map.

**Prerequisites**
- Ubuntu VM (already set up)
- Internet connection to download tools
- Basic terminal knowledge

Since i already have Ubuntu VM, lets update my packages

## Step 1: Install Required Tools
Open a terminal and run these commands:

Code(terminal) - `sudo apt update && sudo apt upgrade -y`

If you already have python, theres not need for this step (down imogi)
Install Python and pip (required for many tools) - `sudo apt install python3 python3-pip -y`

Install Git (for cloning repositories) - `sudo apt install git -y`

Install OWASP ZAP - `sudo apt install zaproxy -y`

Install sqlmap - `sudo apt install sqlmap -y`

Install Burp Suite Community Edition - `wget "https://portswigger.net/burp/releases/download?product=community&version=2023.12.4&type=Linux" -O burpsuite.sh`

`chmod +x burpsuite.sh`

`./burpsuite.sh`
