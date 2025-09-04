<p align="center">
<img width="697" height="246" alt="image" src="https://github.com/user-attachments/assets/b35a901d-2383-4841-9b49-1c2080b9ed8d" />
</p>

# osTicket - Prerequisites and Installation

This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system **osTicket**.

---

## Environments and Technologies Used
- Microsoft Azure Virtual Machine  
- Remote Desktop Connection  
- Internet Information Services (IIS)

---

## Operating Systems Used
- Windows 10 Pro

---

## List of Prerequisites

1. **Download Install Files**
   - Within the virtual machine, download `osTicket-Installation-Files.zip` and unzip it to the desktop.  
   - The folder should be named `osTicket-Installation-Files`.  
   - These files contain osTicket and its dependencies.

2. **Enable IIS + CGI**
   - Control Panel → Programs → *Turn Windows features on or off*  
   - Check **Internet Information Services** → Application Development Features → **CGI**

3. **Install PHP Manager & Rewrite Module**
   - From `osTicket-Installation-Files`, install:
     - `PHPManagerForIIS_V1.5.0.msi`
     - `rewrite_amd64_en-US.msi`
   - Create `C:\PHP` and extract all PHP files there.

4. **Install MySQL & HeidiSQL**
   - Install `mysql-5.5.62-win32.msi`  
   - Typical Setup → Launch Configuration Wizard → Standard Configuration → Set credentials  
   - Install **HeidiSQL** to manage the database.  
   - Create database and name it `osTicket`.

5. **Register PHP in IIS**
   - Run IIS as Administrator  
   - PHP Manager → register `C:\PHP\php-cgi.exe`  
   - Restart IIS (Stop/Start server).

6. **Install osTicket**
   - From `osTicket-Installation-Files`, unzip `osTicket-v1.15.8.zip`  
   - Copy the **upload** folder into `C:\inetpub\wwwroot`  
   - Rename `upload` → `osTicket`

---

## Installation Steps

### Step 1: Enable IIS Features
From Start Menu → Control Panel → *Uninstall or change a program* → *Turn Windows features on or off* → Check **Internet Information Services** + **CGI**.  
<img width="412" height="743" alt="Capture 2" src="https://github.com/user-attachments/assets/1f711505-8733-4737-adbe-e5aa7eb2a6f0" />


---

### Step 2: Install PHP Manager & Rewrite Module
PHP Manager helps configure PHP in IIS. The Rewrite Module is a required dependency.  
- Create `C:\PHP` and extract PHP files there.  
<img width="496" height="407" alt="Capture 4" src="https://github.com/user-attachments/assets/42f30171-4c6c-4905-b7f5-852faba7d2bb" />


---

### Step 3: Install MySQL
MySQL is the database used by osTicket to store data.  
<img width="491" height="384" alt="image" src="https://github.com/user-attachments/assets/ca58ccf8-4255-4605-8e6e-ed74eacd99e4" />


---

### Step 4: Register PHP in IIS
Register PHP Manager in IIS → restart IIS.  
<img width="1183" height="620" alt="Capture 10" src="https://github.com/user-attachments/assets/b7c69565-ea8a-4dec-96de-688a43c33656" />


---

### Step 5: Deploy osTicket
Unzip `osTicket-v1.15.8.zip` → copy `upload` to `C:\inetpub\wwwroot` → rename to `osTicket`.  
<img width="1093" height="560" alt="Capture 13" src="https://github.com/user-attachments/assets/8502c13f-afb1-4aec-acbb-cfbb2e192ff8" />


---

### Step 6: Enable PHP Extensions
In PHP Manager (IIS), enable:
- `php_imap.dll`
- `php_intl.dll`
- `php_opcache.dll`  
<img width="1600" height="860" alt="Capture 16" src="https://github.com/user-attachments/assets/f2a9009e-007d-4f0b-96d4-393535382847" />

---

### Step 7: Configure Database
HeidiSQL allows database configuration.  
- Start a new session → right-click *Unnamed* → Create new → Database → name: `osTicket`.  
<img width="933" height="592" alt="Capture 38" src="https://github.com/user-attachments/assets/e05fb1f5-0fae-4a65-ab05-8fb15f9f1649" />


---

## Completion
✅ **osTicket has been successfully installed!**
<img width="1600" height="859" alt="Capture 41" src="https://github.com/user-attachments/assets/6858c063-7e82-430c-8cf1-369d35d9f0ba" />

