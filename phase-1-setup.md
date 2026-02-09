![osTicket Logo File](screenshots/osTicket-Logo.png)

# Phase 1: Platform Setup & System Requirements
This section explains the required prerequisites and installation process for setting up the open-source helpdesk ticketing system, osTicket.
## Environments & Technologies
- Oracle VirtualBox
- Internet Information Services (IIS)
## Operating System
- Windows Server 2022 (21H2) | Build 20348.587
## List of Prerequisites
- Win Server Virtual Machine Setup.
- Install IIS.
- Install CGI (Common Gateway Interface) so IIS can communicate effectively with PHP.
- Install PHP v8.3.39 and PHP Manager for IIS.
- Install Visual C++ Redistributable for PHP compilation and runtime environment.
- Install MariaDB v12.1.2 and HeidiSQL(x64)
- Install Rewrite for URL customization and redirection.
  
## 1. Virtual Machine Creation & Win Server Installation

Created a virtual machine using Oracle VirtualBox.

![Virtual Machine Creation](screenshots/1%20Creating%20a%20VM.png)

Installed Windows Server 2022 (21H2) | Build 20348.587

![Win Server Install](screenshots/2%20Win%20Server%202022%20Installation.png)

## 2. Prerequisite Program Installations

### 2.1 IIS Installation
Installed IIS using the Server Manager to set the Server Roles. Web Server (IIS), IIS Management Console, and CGI were enabled.

![Enable IIS CGI](screenshots/IIS%20and%20CGI%20install.png)

![IIS Installation on Server](screenshots/3%20IIS%20Installation%20on%20the%20Server.png)

![IIS Install Completed](screenshots/4%20IIS%20Installation%20Completed.png)

IIS was tested to confirm that it works using Edge > http://localhost

![IIS Install Confirmed](screenshots/5%20IIS%20Test%20Complete.png)

### 2.2 PHP, PHP Manager & Visual C++ Installation
PHP folder was created, and files were extracted to C:\PHP. 

![PHP Folder](screenshots/PHP%20Folder.png)

The PHP Manager for IIS was installed, and PHP was registered on the manager.

![PHP Manager Install](screenshots/PHP%20manager%20installed.png)

![PHP Manager on IIS](screenshots/PHP%20Manager%20for%20IIS.png)

The PHP installation was tested using Edge > localhost/info.php to ensure that PHP and IIS are working correctly.

![PHP Functional](screenshots/8%20PHP-Working.png)

Visual C++ Redistributable was installed next.

![VisualC++ Installed](screenshots/6%20Visual%20C%2B%2B%20Installation.png)

### 2.3 MariaDB and HeidiSQL Installation
MariaDB and HeidiSQL were extracted from the same package and installed.

![Maria and Heidi](screenshots/Maria%20and%20Heidi.png)

### 2.4 Rewrite Installation

![Rewrite](screenshots/Rewrite%20installation.png)

## 3. osTicket Database Creation & Installation

### 3.1 The osTicket database was created in MariaDB with a New User

- New database created in MariaDB named 'osticket':  CREATE DATABASE osticket;
- Confirmed that the new database is present: SHOW DATABASES;

![osticket DB creation](screenshots/10%20osticket%20database%20created%20in%20MariaDB.png)

- A new admin user for osTicket was created:
  - CREATE USER 'osticketuser'@'localhost' IDENTIFIED BY 'A Very Strong Password';
  - Username: osticketuser
  - Password: (********************)
- All privileges were granted to this admin user:
  - GRANT ALL PRIVILEGES ON osticket.* TO 'osticketuser'@'localhost';
  - FLUSH PRIVILEGES;
- Confirmed that the new user exists: SELECT User, Host FROM mysql.user;

![new admin user](screenshots/11%20New%20OS%20Ticket%20User%20Created.png)

### 3.2 Extract Files & Set Permissions for osTicket

osTicket v1.18.2 was downloaded, and the files were extracted and copied to the install folder on the C:\ drive: C:\inetpub\wwwroot\osticket
- Permissions were set on the folder C:\inetpub\wwwroot\osticket\include

![osTicket permissions set](screenshots/12%20%20Set%20Permissions%20for%20OS%20Ticket.png)

### 3.3 Load osTicket Setup Page and Complete Installation

The osTicket setup page (http://localhost/osticket) loaded successfully, indicating that the platform meets all the requirements to complete the installation.

![osTicket setup page](screenshots/12%20OS%20Ticket%20Ready%20to%20install.png)

The admin user was registered on osTicket to complete the installation:
- Email: admin@localhost
- Username: kadmin01
- Password: (********************)

![osTicket install completed](screenshots/13%20OS%20Ticket%20Installation%20Completed.png)

## 4. Test Links for osTicket Login

The Agent login was tested using the link http://localhost/osTicket/scp/login.php - Once the page loaded, the login was successful.

![osTicket agent page](screenshots/14%20OS%20Ticket%20Login%20Screen.png)

![osTicket agent login](screenshots/15%20OS%20Ticket%20Successful%20Login.png)

