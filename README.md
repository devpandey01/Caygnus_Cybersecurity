Virtual Machine Setup and Vulnerable Application Installation Report

## **Introduction**
This document outlines the process of setting up a virtual machine (VM) with a Linux-based operating system and installing a vulnerable application Metasploitable2 for penetration testing and security training. 

### **VMware Installation**
1. **Visit the Official Website**: Go to the https://www.vmware.com/products/workstation-pro.html.
2. **Download**: Select the version suitable for your OS.
3. **Install**: Follow the installation steps.

   **Screenshot**: Capture the installation screen (e.g., download page or installation steps).
![image](https://github.com/user-attachments/assets/0179f25a-9ead-40da-9fd8-b82c09107866)

---

## **Step 2: Download a Linux ISO File**
### **Ubuntu Download**
1. **Visit Ubuntu's Download Page**: Go to [Ubuntu Download](https://ubuntu.com/download/desktop).
2. **Choose the Version**: Select the latest stable LTS release.
3. **Download the ISO**: Download the ISO file for installation.

   **Screenshot**: Capture the download page and the selected version.

### **Kali Linux Download**
1. **Visit Kali Linux's Download Page**: Go to [Kali Linux Download](https://www.kali.org/get-kali/).
2. **Choose the Version**: Select a 64-bit ISO image.
3. **Download the ISO**: Download the Kali Linux ISO.

   **Screenshot**: Capture the download page and selected version.

---

## **Step 3: Verify the Integrity of the ISO File**
1. **Obtain the Checksum**: Visit the download page for either Ubuntu or Kali Linux and note the SHA256 checksum.
2. **Verify the ISO File**:
   - On **Linux/macOS**: Use the command `sha256sum /path/to/your.iso`.
   - On **Windows**: Open PowerShell and use `Get-FileHash C:\path\to\your.iso -Algorithm SHA256`.

   **Screenshot**: Capture the checksum verification process (e.g., command output with matching hash).

---

## **Step 4: Create a New Virtual Machine**
### **VirtualBox Setup**
1. **Open VirtualBox** and click **New**.
2. **Select Operating System**: Choose the appropriate OS (e.g., Ubuntu 64-bit or Debian for Kali).
3. **Allocate Resources**:
   - **Memory**: Allocate at least **2GB RAM**.
   - **Disk**: Create a virtual hard disk with at least **20GB** of storage.
4. **Attach ISO**: Go to **Settings** > **Storage** > select **Empty** under **Controller: IDE** and attach the ISO file.

   **Screenshot**: Capture the New VM creation wizard and resource allocation screens.

### **VMware Setup**
1. **Open VMware Workstation** and click **Create a New Virtual Machine**.
2. **Select Operating System**: Choose the appropriate version (e.g., Ubuntu 64-bit or Kali Linux).
3. **Allocate Resources**: 
   - **Memory**: Allocate at least **2GB RAM**.
   - **Disk**: Create a virtual disk with **20GB** storage or more.
4. **Attach ISO**: In **VM Settings**, under **CD/DVD** select the ISO file.

   **Screenshot**: Capture the VM creation wizard in VMware.

---

## **Step 5: Install the Operating System**
1. **Boot the VM**: Start the virtual machine to begin the OS installation process.
2. **Follow Installation Prompts**:
   - Choose language, time zone, keyboard layout.
   - Set up **user accounts** and **root password** (use a strong password for security).
   - Select default disk partitioning for installation.
3. **Complete Installation**: Wait for the installation to finish and reboot.

   **Screenshot**: Capture key steps of the installation process (language selection, partitioning, user setup).

---

## **Step 6: Configure Network Settings**
1. **Configure Network Mode**: Set the network adapter to either **NAT** or **Bridged**:
   - **NAT**: Allows internet access via the host machine.
   - **Bridged**: Connects the VM directly to the local network.

   - **VirtualBox**: Go to **Settings** > **Network** > Adapter 1 > set **Attached to**: NAT or Bridged.
   - **VMware**: Go to **VM Settings** > **Network Adapter** > select **NAT** or **Bridged**.

   **Screenshot**: Capture the network configuration settings (NAT or Bridged mode).

---

## **Step 7: Install a Vulnerable Application (Metasploitable2 or DVWA)**
### **Metasploitable2**
1. **Download**: Obtain the Metasploitable2 ISO from the [official SourceForge page](https://sourceforge.net/projects/metasploitable/).
2. **Create VM**: Create a new VM and mount the Metasploitable2 ISO.
3. **Start the VM**: Boot the VM and log in with the default credentials (`msfadmin`/`msfadmin`).

   **Screenshot**: Capture the Metasploitable2 VM and login screen.

### **DVWA (Damn Vulnerable Web Application)**
1. **Install LAMP Stack** on Ubuntu/Kali:
   ```bash
   sudo apt-get update
   sudo apt-get install apache2 mysql-server php libapache2-mod-php php-mysql
   ```
2. **Download and Install DVWA**:
   ```bash
   cd /var/www/html
   sudo git clone https://github.com/digininja/DVWA.git
   ```
3. **Configure Database**: Set up the DVWA database.
   ```bash
   sudo mysql -u root -p
   CREATE DATABASE dvwa;
   GRANT ALL PRIVILEGES ON dvwa.* TO 'dvwauser'@'localhost' IDENTIFIED BY 'password';
   FLUSH PRIVILEGES;
   ```
4. **Finish Setup**: Access DVWA via your browser at `http://localhost/dvwa/setup.php`.

   **Screenshot**: Capture the DVWA installation and web interface.

Step 8: Take a Snapshot
In VMware: Go to VM > Snapshot > Take Snapshot.

   **Screenshot**: Capture the snapshot interface and the name of the snapshot taken.
