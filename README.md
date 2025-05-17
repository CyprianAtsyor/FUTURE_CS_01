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

Install OWASP ZAP - `sudo snap install zaproxy --classic`

**Note**: I am running snap intall zaproxy because i am using UBUNTU and --classic beacuse i need the access

Install sqlmap - `sudo apt install sqlmap -y`

Install Burp Suite Community Edition - `wget "https://portswigger.net/burp/releases/download?product=community&version=2023.12.4&type=Linux" -O burpsuite.sh`

`chmod +x burpsuite.sh`

`./burpsuite.sh`


## Step 2: Set Up a Sample Vulnerable Web App
For testing purposes, we'll use DVWA (Damn Vulnerable Web Application):

- Install LAMP stack (Linux, Apache, MySQL, PHP)
`sudo apt install apache2 mysql-server php libapache2-mod-php php-mysql -y`

- Download DVWA

`cd /var/www/html`

`sudo git clone https://github.com/digininja/DVWA.git`

`sudo chown -R www-data:www-data DVWA`

`sudo chmod -R 755 DVWA`

- Configure MySQL

`sudo mysql_secure_installation` (Follow prompts to set root password and secure installation)

- Create DVWA database
`sudo mysql -u root -p`


- In MySQL prompt:
  
CREATE DATABASE dvwa;

CREATE USER 'dvwa'@'localhost' IDENTIFIED BY 'p@ssw0rd';

GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwa'@'localhost';

FLUSH PRIVILEGES;

exit


- Configure DVWA

`cd DVWA/config`

`sudo cp config.inc.php.dist config.inc.php`

`sudo nano config.inc.php`

Update these values:

`$_DVWA['db_user'] = 'dvwa';`

`$_DVWA['db_password'] = 'p@ssw0rd';`

`$_DVWA['db_database'] = 'dvwa';`

- Now lets restart Apache
`sudo systemctl restart apache2`

**we now access DVWA at `http://localhost/DVWA` in our browser. Login with admin/password.**
